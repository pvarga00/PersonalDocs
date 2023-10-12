


For properly setting up your environment refer to →



General guidelines about commits and merges for a VS project/solution(until a new branching and code promotion strategy is established):

## **Setup branches/repositories:**

1) Create your fork(origin) from main repository(upstream).
2) Clone your fork(origin) to create local repository(local) on your machine using sourcetree/git or any other UI/command tool.
3) Make sure you have dev and master branches on your local after the clone.

## **Development phase:**

3) Checkout **&lt;local/master&gt;** branch, pull latest code from upstream/master.
4) Make your changes on **&lt;local/master&gt;**branch.
5) While you are making changes on **&lt;local/master&gt;**, periodically commit your changes and also pull from **&lt;upstream/master&gt;** to avoid major conflicts when you are done.
6) Once you are done with all changes(before you do the final commit):
         a. Pull latest code from from **&lt;upstream/master&gt;** again.
         b. Resolve any conflicts.
         c. Build the solution, make sure there are no compilation errors.
         d. Run all unit tests, make sure all the tests pass.
         e. Run code coverage, make sure the code changes made are not bringing the code coverage % down
         f. Run the solution, hit the API and double check to make sure your feature/bug fix works as expected.
7) Once everything is good on (6), commit the changes.
8) Push all your changes from **&lt;local/master&gt;** to **&lt;origin/master&gt;**.

## **Testing/Release phase:**



9) Next, create a pull request(PR) from **&lt;origin/master&gt;** to **&lt;upstream/master&gt;.** 
10) Once your PR is reviewed it will be merged into **&lt;upstream/master&gt;** which will then be deployed to test. If there are additional changes suggested repeat steps 4 through 8 and your existing PR from 9 will be updated with the latest commits.

11) Repeat steps 3 through 12 for any bugs/issues with your changes. upstream/master will eventually go to beta and prod.


