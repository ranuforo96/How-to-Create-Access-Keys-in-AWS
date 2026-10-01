# How-to-Create-Access-Keys-in-AWS
The process of creating access keys for using the AWS Command Line Interface (CLI)

To begin, search IAM in the management console and click IAM users in the left navigation pane

<img width="1920" height="1079" alt="image" src="https://github.com/user-attachments/assets/91fd28d6-802c-4a48-895d-5760a7442918" />

On the users page, click on the user requiring programmatic access. For this example, I will be using Robert

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f26e2881-98c9-47e8-8054-605085874c5a" />

On the user's summary page, under the Security credentials tab scroll down and select Create access key

<img width="1919" height="522" alt="image" src="https://github.com/user-attachments/assets/e1103858-1f22-4716-a4bc-6683a06750c2" />

You should then be given six options for the access key use case. Select Command Line Interface (CLI), check the recommendation acknowledgment box, and click Next

<img width="802" height="635" alt="image" src="https://github.com/user-attachments/assets/04e53c1a-b580-479e-a6ca-5c40a8e5eab6" />

<img width="1177" height="280" alt="image" src="https://github.com/user-attachments/assets/cff99577-8949-42ae-aba6-fd405de1fdbf" />

Enter an optional description tag to track usage, then click Create access key

<img width="1920" height="833" alt="image" src="https://github.com/user-attachments/assets/a56e7c05-a824-409a-97a8-0c8958671442" />

Your Access key and your Secret access key should now be displayed. Copy both the Access key ID and Secret access key, or click Download .csv file. Store them in a secure password manager or secrets vault—once you exit this screen, AWS will never show the secret key again

<img width="1920" height="558" alt="image" src="https://github.com/user-attachments/assets/71172009-00f8-4474-ba8a-e1e7b5542474" />

Open your Command Prompt, enter aws configure, and execute the command

<img width="927" height="639" alt="image" src="https://github.com/user-attachments/assets/519090ed-32af-445d-910e-ebb0c5f30e4c" />

You will then need to provide the access key you previously saved and then press Enter

<img width="922" height="637" alt="image" src="https://github.com/user-attachments/assets/fcdfdf67-efec-4fd6-9c45-3e3d568d5df3" />

Once that has been executed, you must provide your Secret access key and press Enter

<img width="719" height="194" alt="image" src="https://github.com/user-attachments/assets/05c0516c-edfd-4899-baef-a258429a79aa" />

Next, enter your Default region name and press Enter

Select the AWS region closest to your user. You can find the available regions in the screenshot below

<img width="975" height="1080" alt="image" src="https://github.com/user-attachments/assets/c87f0158-d9de-4050-825f-224147b33209" />

<img width="920" height="246" alt="image" src="https://github.com/user-attachments/assets/31ee17da-7572-4d2b-9cf9-4c79b3281510" />

As for the Default output format, you can just hit Enter to skip, and your AWS CLI is now configured

<img width="929" height="305" alt="image" src="https://github.com/user-attachments/assets/8b7d9ad0-dc0d-4557-99f2-a4ff02aa4df5" />

This can be tested by typing in this command: aws iam list-users

<img width="1103" height="100" alt="image" src="https://github.com/user-attachments/assets/f94bef46-358a-4428-9bef-e2bd7c219e54" />

Your output should list all the users in your account

<img width="723" height="332" alt="image" src="https://github.com/user-attachments/assets/21ba6f5e-3e29-4ed0-8c52-a81241cbdeeb" />

The screenshot above displays information for the AWS IAM user named Robert, including his user ID, Amazon Resource Name (ARN), account creation date, and the date his password was last used. This information is similar to what you would see in the AWS Management Console

Now, if I were to remove Robert from the admin group and run the same command, the output I would now receive would throw an error due to a lack of permissions

<img width="1109" height="283" alt="image" src="https://github.com/user-attachments/assets/e65cbb70-0de9-4386-b036-7c810eda2efc" />

This further confirms that the permissions configured through the AWS CLI are the same permissions that can be managed through the IAM console

SECURITY NOTE: IAM Access Keys are static long-term credentials used for external tools (like AWS CLI on Windows). If you only need to run AWS CLI commands without storing keys on your PC, use AWS CloudShell directly in the browser; it requires zero access key management

The AWS CloudShell icon is located on the top dark navigation bar, immediately to the right of the Search bar

However, AWS CloudShell is not available in all regions, but you can check which regions it is available in by searching for CloudShell availability regions on Google

<img width="689" height="105" alt="image" src="https://github.com/user-attachments/assets/c8de18a5-706b-42b7-93a4-a624b50bfe93" />

Clicking it opens an interactive terminal to run commands

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c0fbbec6-59fc-4bc1-8ba0-16604f67eaca" />

In the image below, I tested aws iam list-users to contrast CloudShell and local CLI functionality

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/705f207a-f5f4-4139-8cff-1c9e20926405" />

As seen above, we get the same results as the AWS CLI

CloudShell FEATURES:

CREATE AND MANAGE FILES. Currently, there are no files in CloudShell. We can verfiy by executing the ls comand

<img width="954" height="1067" alt="image" src="https://github.com/user-attachments/assets/6892cd52-ac81-46c0-810d-2975dc2856ae" />

However, running (echo "test" > demo.txt) creates a file named demo.txt and writes the word test into it

<img width="956" height="1067" alt="image" src="https://github.com/user-attachments/assets/dd93b929-e202-402f-a605-9e56147311a7" />

The cat command displays the contents of a file directly in the terminal. In this case, test will be displayed as seen in the image below

<img width="957" height="1078" alt="image" src="https://github.com/user-attachments/assets/bafd5dbc-747a-479a-bf08-fa64a52a82b1" />

Files created in your Cloud Shell environment, such as demo.txt, will persist even if you restart your session

<img width="968" height="1080" alt="image" src="https://github.com/user-attachments/assets/d9a0583c-397a-4a74-9c41-a62d7dcd4b7b" />

<img width="958" height="1073" alt="image" src="https://github.com/user-attachments/assets/f016a705-3a63-4036-8569-43477006c2cf" />

You can also upload and download files within CloudShell. For example if I want to get the full path to my file I would type the pwd command

<img width="594" height="673" alt="image" src="https://github.com/user-attachments/assets/8451232b-efa0-4ea7-b145-c8714ccde4ce" />

