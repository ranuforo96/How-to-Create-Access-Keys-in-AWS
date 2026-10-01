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

Select the AWS region closest to your users. You can find the available regions in the screenshot below

<img width="975" height="1080" alt="image" src="https://github.com/user-attachments/assets/c87f0158-d9de-4050-825f-224147b33209" />

<img width="920" height="246" alt="image" src="https://github.com/user-attachments/assets/31ee17da-7572-4d2b-9cf9-4c79b3281510" />

As for the Default output format, you can just hit Enter to skip, and your AWS CLI is now configured

<img width="929" height="305" alt="image" src="https://github.com/user-attachments/assets/8b7d9ad0-dc0d-4557-99f2-a4ff02aa4df5" />

This can be tested by typing in this command: aws iam list-users

<img width="1103" height="100" alt="image" src="https://github.com/user-attachments/assets/f94bef46-358a-4428-9bef-e2bd7c219e54" />

Your output should list all the users in your account

<img width="723" height="332" alt="image" src="https://github.com/user-attachments/assets/21ba6f5e-3e29-4ed0-8c52-a81241cbdeeb" />

The screenshot above displays information for the AWS IAM user named Robert, including his user ID, Amazon Resource Name (ARN), account creation date, and the date his password was last used. This information is similar to what you would see in the AWS Management Console
