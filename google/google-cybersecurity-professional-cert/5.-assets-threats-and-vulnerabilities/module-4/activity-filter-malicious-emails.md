# Activity: Filter malicious emails

### Activity Overview

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/kj4xszpkRQa5g3KYb7sd6w_8deb28ffbef2423ba810c53d29d585f1_8L02ERLTcJPTfI2ZnnyOUUClaCGVVNLw6ZWTF6lKrskyjfesT7kal5Fhjae5ujbHdHwSZh1ZkzBh5PzxgEvqXTWKgGMdmM6zph4PILSKNxUpKcCuRtik3D5ECEGAWeOap0cKWAQPMoOTMzZkvrzCpyx9oWXh2vWPECGQYQofWN74fPKNZv8mKuzBgJmOUA?expiry=1734825600000&#x26;hmac=Ho-74roEQmABMjD4jHB8sW4CIj40dsb0W0GKKVKruAY" alt=""><figcaption></figcaption></figure>

In this activity, you will analyze a suspicious email and identify signs of a phishing attack. Then, you will determine whether the email should be allowed or quarantined.

Phishing is one of the most common and dangerous forms of social engineering that you’ll encounter in the field. Identifying phishing attempts will help you prevent threats and find ways to improve security procedures.

### Scenario

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/aC3r11M-TbGC4DoHHhEkCw_37d634f315cd476b869d9d0ab30992f1_ofhQ-af_ewtKCs02HnjdpsTjMAvJ2kfgClUzoG6WZHJcwbu7_O55PXYf24zi5a1-LKm03aCLbxueYbh8V0LU-QH6EwXSic37C8Qf4oy1gYi39HuiJWN4j9TcAwAPS_E7K0tLnLAgER_yAAoISdcwk4jeoyuxFydQWop8BIm49MkzXW11TEZ9NC0dwEvgPw?expiry=1734825600000&#x26;hmac=HnsE74VCQzMP0qvAfBUboZDTfm1dZEHjF5jW7vwy_D8" alt=""><figcaption></figcaption></figure>

Review the scenario below. Then complete the step-by-step instructions.

You’re a security analyst at an investment firm called Imaginary Bank. An executive at the firm recently received a spear phishing email that appears to come from the board of Imaginary Bank. **Spear phishing** is a malicious email attack targeting a specific user or group of users, appearing to originate from a trusted source. In this case, the executive is being asked to install new collaboration software, ExecuTalk.

The executive suspects this email might be a phishing attempt because ExecuTalk was never mentioned during the last board meeting. They've forwarded the message to your team to verify if it’s legitimate. Your supervisor has tasked you with investigating the message and determining whether it should be quarantined.

### Step-By-Step Instructions

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/PoQYq3xXRxadHWc4DHSq9A_318b85f1b2864b868e9989238e5edef1_ofhQ-af_ewtKCs02HnjdpsTjMAvJ2kfgClUzoG6WZHJcwbu7_O55PXYf24zi5a1-LKm03aCLbxueYbh8V0LU-QH6EwXSic37C8Qf4oy1gYi39HuiJWN4j9TcAwAPS_E7K0tLnLAgER_yAAoISdcwk4jeoyuxFydQWop8BIm49MkzXW11TEZ9NC0dwEvgPw?expiry=1734825600000&#x26;hmac=3B6SukdfYoNLYaCcRaJQcNLeUwpNy-HB8jQABMXb8yM" alt=""><figcaption></figcaption></figure>

Follow the instructions and answer the questions below to complete the activity.

#### Step 1: Analyze the suspicious email

Previously, you learned that phishing is a type of social engineering. Threat actors who send malicious emails rely on deception and manipulation techniques to trick their targets. When investigating suspicious emails like this, it's a good idea to note the threat actor's tactics. You can use that information to alert others at your organization about similar messages they might receive and what to watch out for.

Start your investigation by analyzing the suspicious message. Try to identify clues that this is a phishing attack against this executive at Imaginary Bank:

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/v1AMaO1aRlq6cMKZWMfNdQ_1bd488ff267e4a6eb19694503b8b84f1_4g2KPQMeYYc8TLKvRz2BTFq_ULjJXr61clkTGxzmM3_U4AkaQcEFjxmr6QNh9zIIX6jYLfuXHkkTDomI-rKtQo4mqK_QHW_97XotVAeTxP4S8M-b8EQkNYk8f0EVQZiqtK25tvT2jH8DIdDvF8uCong?expiry=1734825600000&#x26;hmac=z-w4YdxZ-fGIFkrQzbEFBK0IbIYX9dZkYjzfDMTJyAY" alt=""><figcaption></figcaption></figure>

_**From:** imaginarybank@gmail.org_

_**Sent:** Saturday, December 21, 2019  15:05:05_

_**To:** cfo@imaginarybank.com_

_**Subject:**  RE: You are been added to an ecsecutiv's groups_

_Conglaturations! You have been added to a collaboration group ‘Execs.’_

_Downlode ExecuTalk to your computer._

_**Mac®** | **Windows®** | **Android™**_&#x20;

_You're team needs you! This invitation will expire in 48 hours so act quickly._

_Sincerely,_

_**ExecuTalk©**_

_All rights reserved._&#x20;

#### Step 2: Examine the sender's information

####

Next, examine the major parts of this message in closer detail starting with the email header. You can often find clues in the message header that indicate you are dealing with a phishing attack.

Examine the email header of this suspicious message:

_**From:** imaginarybank@gmail.org_

_**Sent:** Saturday, December 21, 2019  15:05:05_

_**To:** cfo@imaginarybank.com_

_**Subject:**  RE: You are been added to an ecsecutiv's groups_

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/v1AMaO1aRlq6cMKZWMfNdQ_1bd488ff267e4a6eb19694503b8b84f1_4g2KPQMeYYc8TLKvRz2BTFq_ULjJXr61clkTGxzmM3_U4AkaQcEFjxmr6QNh9zIIX6jYLfuXHkkTDomI-rKtQo4mqK_QHW_97XotVAeTxP4S8M-b8EQkNYk8f0EVQZiqtK25tvT2jH8DIdDvF8uCong?expiry=1734825600000&#x26;hmac=z-w4YdxZ-fGIFkrQzbEFBK0IbIYX9dZkYjzfDMTJyAY" alt=""><figcaption></figcaption></figure>

**Pro tip:** Always check the domain name that comes after the @ symbol. Requests for sensitive information or asking you to download files should not come from personal accounts, like _@gmail.com, @icloud, @yahoo.com_ or others.

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/v1AMaO1aRlq6cMKZWMfNdQ_1bd488ff267e4a6eb19694503b8b84f1_4g2KPQMeYYc8TLKvRz2BTFq_ULjJXr61clkTGxzmM3_U4AkaQcEFjxmr6QNh9zIIX6jYLfuXHkkTDomI-rKtQo4mqK_QHW_97XotVAeTxP4S8M-b8EQkNYk8f0EVQZiqtK25tvT2jH8DIdDvF8uCong?expiry=1734825600000&#x26;hmac=z-w4YdxZ-fGIFkrQzbEFBK0IbIYX9dZkYjzfDMTJyAY" alt=""><figcaption></figcaption></figure>

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/v1AMaO1aRlq6cMKZWMfNdQ_1bd488ff267e4a6eb19694503b8b84f1_4g2KPQMeYYc8TLKvRz2BTFq_ULjJXr61clkTGxzmM3_U4AkaQcEFjxmr6QNh9zIIX6jYLfuXHkkTDomI-rKtQo4mqK_QHW_97XotVAeTxP4S8M-b8EQkNYk8f0EVQZiqtK25tvT2jH8DIdDvF8uCong?expiry=1734825600000&#x26;hmac=z-w4YdxZ-fGIFkrQzbEFBK0IbIYX9dZkYjzfDMTJyAY" alt=""><figcaption></figcaption></figure>

**Question 1:**\
&#xNAN;_&#x57;hich two clues in the message header indicate to you that this is a phishing attempt?_

* **The sender is using a different domain.**\
  Legitimate emails from Imaginary Bank’s board would likely come from an official company domain (e.g., @imaginarybank.com), not a free email service like @gmail.org.
* **There is a misspelling in the subject line.**\
  The subject line “RE: You are been added to an ecsecutiv’s groups” contains noticeable spelling and grammatical errors. Phishing emails often contain such errors.

**Correct Answers:**

* The sender is using a different domain.
* There is a misspelling in the subject line.

***

**Question 2:**\
&#xNAN;_&#x57;hat details make this message appear legitimate?_

* **The invitation time limit:** Creating a sense of urgency (“This invitation will expire in 48 hours”) often makes a message seem more legitimate and prompts the recipient to act quickly.
* **The brand labeling:** Including a brand name and copyright symbol “ExecuTalk©” gives the email an official appearance.
* **The download options for major operating systems:** Providing links for Mac®, Windows®, and Android™ seems like a professional and user-friendly detail.

**Correct Answers:**

* The invitation time limit
* The brand labeling
* The download options for major operating systems

***

**Question 3:**\
&#xNAN;_&#x54;he download options open a webpage that contains a login form. What is the main clue that indicates this form is malicious?_

* **The URL:** A suspicious or mismatched URL that doesn’t align with the company’s official domain is a major red flag. Even if the page looks authentic, an off-brand or unrelated URL signals that this is a phishing site.

**Correct Answer:**

* The URL

***

**Question 4:**\
&#xNAN;_&#x41;fter completing your investigation, should this email be quarantined?_\
Since you’ve identified multiple phishing indicators—from the suspicious sender domain, poor spelling, and an untrustworthy URL—this email is almost certainly a malicious phishing attempt.

**Correct Answer:**

* Yes
