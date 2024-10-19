1. Navigate to **IAM**.
2. In the IAM sidebar menu, select **User groups**.
3. Add **user-1** to the **S3-Support** group:
    - Select the **S3-Support** group name.
    - Ensure the **Users** tab is selected and then click **Add users** on the right.
    - From the list of available users, check the checkbox next to **user-1**.
    - Click **Add users**.
4. Use the breadcrumb navigation along the top of the page to select **User groups**.
5. Add **user-2** to the **EC2-Support** group:
    - Select the **EC2-Support** group name.
    - Ensure the **Users** tab is selected and then click **Add users** on the right.
    - From the list of available users, check the checkbox next to **user-2**.
    - Click **Add users**.
6. Use the breadcrumb navigation along the top of the page to select **User groups**.
7. Add **user-3** to the **EC2-Admin** group:
    - Select the **EC2-Admin** group name.
    - Ensure the **Users** tab is selected and then click **Add users** on the right.
    - From the list of available users, check the checkbox next to **user-3**.
    - Click **Add users**.
8. In the IAM sidebar menu, select **Users**.
9. Review the permissions for **user-3**:
    - Select the **user-3** user name.
    - Select the **Permissions** tab and then click the plus-sign icon to expand the customer inline policy associated with **user-3**.
    - On the right, click **Edit**.
    - Select the **JSON** tab and review the policy permissions, but do not make any changes.
    - Close this tab.

![[Pasted image 20241015013558.png]]

![[Pasted image 20241015013653.png]]

![[Pasted image 20241015013833.png]]

![[Pasted image 20241015014110.png]]

![[Pasted image 20241015014220.png]]

![[Pasted image 20241015014435.png]]

Permission Policy for ec2-admin User Group

{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Action": [
				"ec2:Describe*",
				"ec2:StartInstances",
				"ec2:StopInstances"
			],
			"Resource": "*",
			"Effect": "Allow"
		},
		{
			"Action": "elasticloadbalancing:Describe*",
			"Resource": "*",
			"Effect": "Allow"
		},
		{
			"Action": [
				"cloudwatch:ListMetrics",
				"cloudwatch:GetMetricStatistics",
				"cloudwatch:Describe*"
			],
			"Resource": "*",
			"Effect": "Allow"
		},
		{
			"Action": "autoscaling:Describe*",
			"Resource": "*",
			"Effect": "Allow"
		}
	]
}

Imagine this JSON code is like a set of magical powers that you're giving to a group of superhero assistants called the "ec2-admin User Group." Let’s break down what these powers are and how they work!

### Overview
This "Permission Policy" is like a *magical scroll* that grants specific powers to the group, telling them what they *can* do (what spells they can cast) and where they can use them (who they can cast them on). 

The policy has a version, which is like saying this is the 2012 edition of the spellbook ("Version": "2012-10-17"). The real action happens inside the `"Statement"` section — it's like a to-do list of different magical powers!

Now, let’s dive into each of these magic spells they get to use:

### Power #1: EC2 Wizardry 🖥✨
- **Action**: `"ec2:Describe*"` 🗺️
  - This is like giving your assistants a magical crystal ball to look at all the EC2 instances and tell you what’s up! They get the power to *see* everything going on with EC2 instances.

- **Action**: `"ec2:StartInstances"` 🚀
  - Boom! They can bring an EC2 instance *to life*, like using a "wake up" spell.

- **Action**: `"ec2:StopInstances"` 🛑
  - If an instance is misbehaving, they can put it to sleep — a "rest spell" to stop it.

- **Resource**: `"*"` 🌍
  - They can do this magic on *any* EC2 instance anywhere in your cloud kingdom.

- **Effect**: `"Allow"` ✅
  - You’re saying *yes*, they can totally do this magic.

### Power #2: Load Balancer Lookout 🏋️‍♂️🔍
- **Action**: `"elasticloadbalancing:Describe*"` 🤓
  - They can *examine* anything related to load balancing, like a watchful guardian keeping tabs on the traffic flow of your cloud.

- **Resource**: `"*"` 🌐
  - They can use this on *any* load balancer.

- **Effect**: `"Allow"` 🟢
  - Again, this is *allowed*. They’ve got the thumbs up!

### Power #3: CloudWatch Fortune Teller 📊🔮
- **Action**: `"cloudwatch:ListMetrics"` 📜
  - They can see *all the metrics*, which is like looking at a big stats board showing how different parts of the system are doing.

- **Action**: `"cloudwatch:GetMetricStatistics"` 📈
  - They can dig deeper and *analyze* those metrics, like checking your speed stats during a race.

- **Action**: `"cloudwatch:Describe*"` 📖
  - This power lets them *describe* all the monitoring stuff, like knowing all the names of the players on the field.

- **Resource**: `"*"` 🌌
  - They can look at all CloudWatch metrics across the whole cloud galaxy.

- **Effect**: `"Allow"` ✅
  - Yup, this is allowed.

### Power #4: Auto Scaling Detective 🔍📦
- **Action**: `"autoscaling:Describe*"` 🚀
  - This power is all about peeking at the *Auto Scaling* details, so your assistants can see how things are scaling up or down in the cloud.

- **Resource**: `"*"` 🌍
  - They can do this for any and all auto-scaling groups.

- **Effect**: `"Allow"` ✅
  - They are totally allowed to investigate and learn all the auto-scaling things!

### Summary
Imagine the "ec2-admin User Group" as your team of adventurers who are equipped with specific spells to help manage the cloud village:

1. **Look and Control EC2 Instances**: They can *watch*, *start*, and *stop* instances.
2. **Monitor Load Balancers**: They can check on how well the load balancers are juggling traffic.
3. **Consult the Metrics Oracle**: They have deep insights into CloudWatch, like a fortune teller who can see all the metrics.
4. **Scale Watcher**: They’re on the lookout for how the kingdom scales its resources automatically.

Every power they have is allowed to be used anywhere, so they are pretty much wizards who can see, manage, and monitor all aspects of EC2, load balancers, CloudWatch, and auto-scaling.

Hopefully, this magical adventure made it fun and easier to understand! 🧙‍♂️✨