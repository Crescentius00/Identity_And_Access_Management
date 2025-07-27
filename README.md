# Identity_And_Access_Management

## Introduction
This project focuses on setting up IAM user for Zappy E-Bank.

The goal is to set up IAM user for Backend developer, John, and Data analyst, Mary.

As a developer, John requires acces to servers (EC2), to run his codes, neccessitating IAM user with policies granting access to EC2.

As a data analyst, Mary requires access to data storage (S3 services), which means her IAM user policies should give her access to S3 services.

## Project Details

1. ### Create Policy for Development Team

    1. Logged into AWS, and in the IAM console, I clicked on create policy.
    ![](./img/1.Create_Policy.PNG)

    2. In the select a service section, I searched for and selected EC2.
    ![](./img/2.Select_EC2.PNG)

    3. Selected "All EC2 actions"
    ![](./img/3.All_EC2_Actions.PNG)

    4. Selected "All" in the resource section
    ![](./img/4.All_Resources.PNG)

    5. Clicked "Next" and prodided the name of the policy "Developers". Then I clicked "Create Policy".
    ![](./img/5.Name_Developers.PNG)

    This was how the Developers policy was created.

2. ### Create Policy for Data Analyst

This same process for Developers policy was used, but instead of EC2, S3 was selected and the name "Analyst" was used instead of "Developers".
![](./img/6.Select_S3.PNG)
![](./img/7.All_S3_Actions.PNG)
![](./img/8.Name_Analyst.PNG)
![](./img/9.Create_Group.PNG)

3. ### Create Group for the Development Team

    1. In the IAM console navigation, I selected "User group" and clicked "Create group"

    2. Provided a name for the group "Development-Team"
    ![](./img/10.Developmet-Team.PNG)

    3. Attached the "Developers" policy to the group.
    ![](./img/11.Attach_Developers_Policy.PNG)

    Development-Team group is created.

4. ### Create Group for Data Analyst Team

The same process for the Development-Team was used. The name of the group is "Analyst-Team" and the "Analyst-Policy" was attached.
![](./img/12.Analyts-Team.PNG)
![](./img/13.Attatch_Analyst_Policy.PNG)

5. ### Creating IAM User for John

    1. Navigated to the IAM dashboard, selected "Users" and clicked "Create"
    ![](./img/14.Create_User.PNG)

    2. Provided the name of the user, "John"; and granted access to AWS management console.
    ![](./img/15.User_John.PNG)

    3. Added John to "Development-Team" group
    ![](./img/16.Added_John_To_Develpment-Team_Group.PNG)

    4. Clicked "Create User"; and downloaded John's login credentials
    ![](./img/17.Download_John's_Login_Credentials.PNG)

6. ### Creating IAM User for Mary

The same process as for John, but Mary is added to Analyst-Team group
![](./img/18.Mary.PNG)
![](./img/19.Added_Mary_To_Analyst-Team_Group.PNG)
![](./img/20.Download_Mary's_Login_Credentials.PNG)

7. ### Setting MFA

    1. Clicked on "User", clicked on "John"

    2. Clicked on "Enable MFA"
    ![](./img/21.John's_MFA.PNG)

    3. Entered a device name for John's MFA and selected Passkeys and security keys to complete the setup.
    ![](./img/22.John_MFA_Device.PNG)

    The same process was used to setup Mary's MFA too.