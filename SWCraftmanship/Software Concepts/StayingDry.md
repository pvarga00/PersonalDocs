# Staying Dry

Content Taken From:
http://enterprisecraftsmanship.com/2015/09/11/dry-revisited/
By Vladimir Khorikov

 

Another principle we should follow when building a software project is the DRY principle. The abbreviation stands for Don’t Repeat Yourself. While it seems pretty straightforward and intuitive, this principle is more than meets the eye. Let’s see how it is so.

 

The DRY principle
The DRY principle states that every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

The implication from this principle is often deemed to be avoiding code duplication. While it’s true that in most cases following DRY means the elimination of repeatable code, the principle itself is not about code duplication.

 

Let’s take an example:

public class Product

{

    /* Other members */

    public string Name { get; set; }

 

    public override string ToString()

    {

        return Name;

    }

}

 

public class Customer

{

    /* Other members */

    public string Name { get; set; }

 

    public override string ToString()

    {

        return Name;

    }

}

 

Here, the Product and the Customer classes have two members in common. We could refactor them and extract those members, like this:

 

public class NamedEntity

{

    public string Name { get; set; }

 

    public override string ToString()

    {

        return Name;

    }

}

 

public class Product : NamedEntity

{

    /* Other members */

}

 

public class Customer : NamedEntity

{

    /* Other members */

}

 

This version now complies with the DRY principle. Or does it not? Was there really a single piece of knowledge spread across these entities?

Can it be that two classes have identical parts yet still don’t break DRY?

Yes. The DRY principle restricts the presence of domain knowledge, it doesn’t put any bounds on the actual code which is required to express that knowledge.

The fact the two entities have the same functionality doesn’t mean they violate DRY. In fact, both the Product and the Customer classes hold their own semantics. It just happened that they do it using the identical code in this particular case.

From the domain’s point of view, these entities develop separately from each other. They both represent different parts of the domain and thus don’t violate the DRY principle.

Introducing a base class purely because two or more entities have some members in common is generally a bad practice. I call it utility inheritance.

DRY and utility methods
If the DRY principle forces us to keep every piece of domain knowledge in a single place, what about the code that doesn’t contain any? Would the duplication of such code be a violation of DRY?

No, because, again, the DRY principle is about the knowledge that is essential to your domain. Utility methods don’t contain such knowledge.

It doesn’t mean we should introduce unnecessary duplication all over the helper methods, though. It just means that if we can’t avoid it, it’s not such a big deal.

Eric Lippert gives a great example in his article:

static Func<A, R> Memoize<A, R>(this Func<A, R> function)

{

    var cache = new Dictionary<A, R>();

    return argument =>

    {

        R result;

        if (!cache.TryGetValue(argument, out result))

        {

            result = function(argument);

            cache[argument] = result;

        }

        return result;

    };

}

Here, we have a pretty simple utility method for memorizing a function output. The problem is that if we want to introduce a memorizer for a function with 2, 3, or more parameters, we would need to write methods that almost fully duplicate each other.

There’s no way to avoid this duplication. At the same time, such methods don’t contain any knowledge about the application domain, so it’s perfectly fine to have multiple similar versions of them.

DRY and bounded contexts
One of the most controversial examples in terms of the DRY principle is code in differentbounded contexts.

For example, we could have two contexts – Sales and Manufacture – with Product entity in each of them:

namespace Sales

{

    public class Product

    {

        public string Name { get; set; }

        public int Number { get; set; }

        public string Description { get; set; }

 

        public void AttachToManager(SalesManager manager)

        {

            /* … */

        }

    }

}

 

namespace Manufacture

{

    public class Product

    {

        public string Name { get; set; }

        public int Number { get; set; }

        public string Description { get; set; }

 

        public Product[] Disassemble()

        {

            /* … */

        }

    }

}

Note that the two classes have a lot of members in common. A natural tendency in such situation is to merge them into a single entity. However, combining them together wouldn’t be the best design decision.

From the domain point of view, these two classes have completely different semantics. While Sales.Product entity carries the knowledge that regards to how the products are sold, Manufacture.Product is all about their manufacturing.

They do have similar physical representation, but it wouldn’t make a lot of sense to have a joint “all-in-one” version of the Product class. We are better off keeping these pieces of knowledge apart. That would make them more focused and less prone to semantics mismatch. That is, when a property or a method means one thing in one context, and totally different thing in the other.

Summary
The DRY principle is about domain knowledge.
Don’t confuse adhering to DRY with getting rid of code repetition.
There are cases where code duplication is perfectly fine.
