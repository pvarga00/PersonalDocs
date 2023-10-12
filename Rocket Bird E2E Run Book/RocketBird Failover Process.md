
This document will go over the process of cutting over to the passive RocketBird environment in the event of a failure in the primary environment.

## Requirements

- You will need to have full production deployment permissions in HAL to perform this action. Work with your team leader to obtain these permissions.


## Process

1. Go to the application's page in HAL ([https://hal9000.rockfin.com/applications/1967/dashboard](https://hal9000.rockfin.com/applications/1967/dashboard))
2. Make sure you are in the **Prod** environment. If you are not, click on the **Change Environment** text on the right corner of the dashboard.

<ac:image ac:height="400"><ri:attachment ri:filename="image2019-9-11_21-3-42.png"></ri:attachment></ac:image>
3. You will see one of the boxes has a green ! icon. **This indicates the current active environment**. We will be swapping this to the other environment. Click **Deploy** under the **swap** box to begin this process.


<ac:image ac:height="250"><ri:attachment ri:filename="image2019-9-11_21-6-57.png"></ri:attachment></ac:image>
4. Check the **url swap** option, and click **Deploy Selected Targets**. You will prompted again to check another box, then you will need to click the **Deploy Selected Targets** box again.


<ac:image ac:height="400"><ri:attachment ri:filename="image2019-9-11_21-9-46.png"></ri:attachment></ac:image>
5. This will begin the swap process, which can take a couple minutes. Once the deployment is done, go back to the application dashboard in HAL and verify the green box is now on the other environment.

