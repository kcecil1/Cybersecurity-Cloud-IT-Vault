
- **`user-1` password**: `3Kk6!AY36^5h1rolJYb@C`
- **`user-2` password**: `3Kk6!AY36^5h1rolJYb@C`
- **`user-3` password**: `3Kk6!AY36^5h1rolJYb@C`
#### Sign In as **user-1**

1. In the IAM sidebar menu, select **Dashboard**.
    
2. In the **AWS Account** section on the right, copy the sign-in URL.
    
3. In a new browser tab, navigate to the URL.
    
4. Log in to the AWS Management Console as **user-1** using the password provided in the lab's resources.
    
    Remember that this user only has read-only access to S3.
    
5. Navigate to **S3**.
    
6. On the right, click **Create bucket**.
    
7. In the **Bucket name** field, enter a globally unique bucket name (e.g., _mycoolS3bucket393874_).
    
8. Leave all other default settings and click **Create bucket**.
    
    You should receive an **Access Denied** error, indicating that your group policy is in effect.
    
9. Navigate to **EC2**.
    
    You should see a number of API errors, indicating that you do not have access to EC2.
    
10. In the top right corner of the page, expand the **user-1** dropdown menu.
    
11. Copy the **Account ID** and then click **Sign out**.
    
![[Pasted image 20241015020245.png]]

![[Pasted image 20241015020649.png]]

![[Pasted image 20241015020755.png]]



#### Sign In as **user-2**

1. Click **Log back in** and then paste your copied account ID in the **Account ID** field.
    
2. Log in to the AWS Management Console as **user-2** using the password provided in the lab's resources.
    
    Remember that this user only has read-only access to EC2.
    
3. Navigate to **EC2**.
    
4. From the **Resources** section in the main pane, select **Instances (running)**.
    
5. Check the checkbox to the left of the running instance and review the instance details.
    
6. Along the top of the page, use the **Instance state** dropdown to select **Stop instance**, and then click **Stop**.
    
    You should see an error message, since this user doesn't have the permissions to stop instances.
    
7. Navigate to **S3**.
    
    You should see that S3 is unavailable for **user-2** because this user doesn't have any permissions outside of EC2.
    
8. In the top-right corner of the page, expand the **user-2** dropdown menu.
    
9. Copy the **Account ID** and then click **Sign out**.
    
![[Pasted image 20241015021123.png]]

![[Pasted image 20241015021032.png]]

![[Pasted image 20241015021309.png]]

![[Pasted image 20241015021335.png]]

![[Pasted image 20241015021401.png]]

![[Pasted image 20241015021552.png]]


#### Sign In as user-3

1. Click **Log back in** and then paste your copied account ID in the **Account ID** field.
    
2. Log in to the AWS Management Console as **user-3** using the password provided in the lab's resources.
    
    Remember that this user can view, start, and stop EC2 instances.
    
3. Navigate to **EC2**.
    
4. From the **Resources** section in the main pane, select **Instances (running)**.
    
5. Check the checkbox to the left of the running instance.
    
6. Use the **Instance state** dropdown to select **Stop instance**, and then click **Stop**.
    
7. After a minute, refresh the instances page to verify the instance is now in a **Stopped** state.


![[Pasted image 20241015021737.png]]

![[Pasted image 20241015021813.png]]

![[Pasted image 20241015021902.png]]



