# Activity: Apply the PASTA threat model framework

Activity Overview

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/iLZ1b-HySWibkcPYGvstEQ_8455fac4745d4d6d8b0144afdc1211f1_OR7CVyyVmtUgcage9q2KlGn32VKgqg56qYV0aoRC3WdAYbg9FlR40jB8rmCfNdGaQHKsGp3QTyoMZzmrTFT9cvnWLTYXulXNwyb0fTB8chWMQGF24Lg31tVR-JzIVA90RKx9-iSCQe-XeHy1u3BE2gk73oAXap1Lfemj3HteYDFVy4YrnfSuYwVSWeWvDw?expiry=1734825600000&#x26;hmac=zzaO30TI7o_CBj-0UW-rkXPbApAPz2FB2dtSWCxt9xY" alt=""><figcaption></figcaption></figure>

In this activity, you will practice using the Process of Attack Simulation and Threat Analysis (PASTA) threat model framework. You will determine whether a new shopping app is safe to launch.

Threat modeling is an important part of secure software development. Security teams typically perform threat models to identify vulnerabilities before malicious actors do. PASTA is a commonly used framework for assessing the risk profile of new applications.

### Scenario

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/lghMCJFpSSyOxSTHwRg5pw_d34dceb616cf429dad9c1cf198c3e1f1_SB1PvipapwvJ0VbkfIihqDZTEsJ8-krVq23zOOfM3JU7guHc5mLOuXBeM1xBOBKwamT-KtqAGqYLcYoeu_UL-rJAu5rp8aTmjeMkX4Xy9ysK745g7GNugBTdZ7ufmi_Jw0aYQbVXC06kRpMuti_nOImcgYqUa7HWgVL7wLrnVGVuqMPfKjtD7bSfae0yXQ?expiry=1734825600000&#x26;hmac=_BF5wnP3NIEDF45TZ3p7IA1842PjTC8V88x_LKa-uYU" alt=""><figcaption></figcaption></figure>

Review the following scenario. Then complete the step-by-step instructions.

You’re part of the growing security team at a company for sneaker enthusiasts and collectors. The business is preparing to launch a mobile app that makes it easy for their customers to buy and sell shoes.&#x20;

You are performing a threat model of the application using the PASTA framework. You will go through each of the seven stages of the framework to identify security requirements for the new sneaker company app.

### Step-By-Step Instructions

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/JB_wYgNrQ2eHOoWyK7is7g_502afdd06e83421194ca9b6e0bf38bf1_SB1PvipapwvJ0VbkfIihqDZTEsJ8-krVq23zOOfM3JU7guHc5mLOuXBeM1xBOBKwamT-KtqAGqYLcYoeu_UL-rJAu5rp8aTmjeMkX4Xy9ysK745g7GNugBTdZ7ufmi_Jw0aYQbVXC06kRpMuti_nOImcgYqUa7HWgVL7wLrnVGVuqMPfKjtD7bSfae0yXQ?expiry=1734825600000&#x26;hmac=cfNYr9EsPc7WaVlqSomDAWGFAzTdAGZegHmjGI1wSDE" alt=""><figcaption></figcaption></figure>

Follow the instructions and answer the included questions to complete the activity.

### Part 1 - Access the resources

#### Step 1: Access the template

To use the template for this course item, click the following link and select _Use Template_.&#x20;

Link to template: [PASTA worksheet](https://docs.google.com/document/d/1u3aU6ZnWfcjzwZt79OdIwJ27dcyCZYDtmEEMivey3Os/template/preview?resourcekey=0-TAMA_2t0BCj5-BL9wG23Ng)

OR

If you don’t have a Google account, you can download the template directly from the following attachment.

[PASTA worksheetDOCX File](https://d3c33hcgiwev3.cloudfront.net/_e7QdCvpT1GdBQWKm4J5WQ_84596f5e70564964a5a27271d3c8fdf1_PASTA-worksheet.docx?Expires=1734825600\&Signature=RfH8Mob4maF2BuKHvJVOM40wUqvFWLlfX1EEf5JyoUuLfmCfvnoInZtmPdIFYd8zHwrCdh0J0tsa6RXZw0ZVLPfhX6RdODdokLMyotkmGy~Q~9efdHcUmrVOiqNNPzqk~zHuCkJmZPH5g3jXABFp4FkdpqyX9UF0-HZnYHVTUdU_\&Key-Pair-Id=APKAJLTNE6QMUY6HBC5A)

#### Step 2: Access supporting materials

The following supporting materials will help you complete this activity. Keep them open as you proceed to the next steps.&#x20;

To use the supporting materials for this course item, click the following link and select _Use Template_.&#x20;

Link to supporting materials:

* [PASTA data flow diagram](https://docs.google.com/presentation/d/1ol7y79popTFfNHM-90ES-H-i1Lpd0YNvPShxBlXozjg/template/preview?resourcekey=0-DZAkf7Vzh2PXsP-j3oXV-g)
* [PASTA attack tree](https://docs.google.com/presentation/d/1FmWLyHgmq9XQoVuMxOym2PHO8IuedCkan4moYnI-EJ0/template/preview?resourcekey=0-zYPY7AhPJdcClXamlAfOag#slide=id.p)

OR

If you don’t have a Google account, you can download the supporting materials directly from the following attachment.

[PASTA data flow diagramPPTX File](https://d3c33hcgiwev3.cloudfront.net/_DuZH5sWRbar2MG_OtwnrQ_af70c56702bd4ec3bb79f5ebb16a05f1_PASTA-data-flow-diagram.pptx?Expires=1734825600\&Signature=Vzc4aoCqN3CL5ruEkhs1~GJJRuPMUMbigydTDK44nVo0QpSB8HgV7~mkES1NRj0JT18R4KfXm6x63vRA3e8uv32oUolECoAffANuQm0MnvuyZCeBp3PDrd34MtuD4fF7Ei-NLNj42QdZ4XhzaQwrr1BmIM5AmvLkGLAaI3aO9ew_\&Key-Pair-Id=APKAJLTNE6QMUY6HBC5A)[PASTA attack treePPTX File](https://d3c33hcgiwev3.cloudfront.net/tcb13n8dSkO-aMxA81RtZw_48ab62b34e1e4139959030e71fbd3bf1_PASTA-attack-tree.pptx?Expires=1734825600\&Signature=j5qR-N6n7u9nnzztX6CPL6m0UJYAVwYfhXNnrj4FsONbxBclbVuca5lqfXkWc6FNvqK7PMoZxYwpHPNjeBLN8x4MbmOpq4v8mJ71KtLGFrCFA0zrSScztg4j7IqXnEnXtp3fYpf6JcYcZVOTJICt4G4BB6EeWVtKZTuXFKlJMac_\&Key-Pair-Id=APKAJLTNE6QMUY6HBC5A)

### Part 2 - Complete the PASTA stages

#### Step 1: Identify the mobile app’s business objectives

The main goal of Stage I of the PASTA framework is to understand why the application was developed and what it is expected to do.

_**Note:** Stage I typically requires gathering input from many individuals at a business._

First, review the following description of why the sneaker company decided to develop this new app:

**Description:** Our application should seamlessly connect sellers and shoppers. It should be easy for users to sign-up, log in, and manage their accounts. Data privacy is a big concern for us. We want users to feel confident that we’re being responsible with their information.

Buyers should be able to directly message sellers with questions. They should also have the ability to rate sellers to encourage good service. Sales should be clear and quick to process. Users should have several payment options for a smooth checkout process. Proper payment handling is really important because we want to avoid legal issues.

In the **Stage 1** row of the **PASTA worksheet,** make **2-3 notes** of business objectives that you’ve identified from the description.

#### Step 2: Evaluate the apps components

In Stage II, the technological scope of the project is defined. Normally, the application development team is involved in this stage because they have the most knowledge about the code base and application logic. Your responsibility as a security professional would be to evaluate the application's architecture for security risks.

For example, the app will be exchanging and storing a lot of user data. These are some of the technologies that it uses:

* **Application programming interface (API):** An API is a set of rules that define how software components interact with each other. In application development, third-party APIs are commonly used to add functionality without having to program it from scratch.
* **Public key infrastructure (PKI):** PKI is an encryption framework that secures the exchange of online information. The mobile app uses a combination of symmetric and asymmetric encryption algorithms: AES and RSA. AES encryption is used to encrypt sensitive data, such as credit card information. RSA encryption is used to exchange keys between the app and a user's device.
* **SHA-256:** SHA-256 is a commonly used hash function that takes an input of any length and produces a digest of 256 bits. The sneaker app will use SHA-256 to protect sensitive user data, like passwords and credit card numbers.
* **Structured query language (SQL):** SQL is a programming language used to create, interact with, and request information from a database. For example, the mobile app uses SQL to store information about the sneakers that are for sale, as well as the sellers who are selling them. It also  uses SQL to access that data during a purchase.

Consider what you've learned about these technologies:&#x20;

* _Which of these technologies would you evaluate first? How might they present risks from a security perspective?_

In the **Stage II** row of the **PASTA worksheet**, write **2-3 sentences** (40-60 words) that describe why you choose to prioritize that technology over the others.

#### Step 3: Review a data flow diagram

During Stage III of PASTA, the objective is to analyze how the application is handling information. Here, each process is broken down.

For example, one of the app's processes might be to allow buyers to search the database for shoes that are for sale.&#x20;

Open the **PASTA data flow diagram** resource. Review the diagram and consider how the technologies you evaluated relate to protecting user data in this process.

_**Note:** Software developers usually have detailed data flow diagrams available for security teams to use and verify that information is being processed securely._

#### Step 4: Use an attacker mindset to analyze potential threats

Stage IV is about identifying potential threats to the application. This includes threats to the technologies you listed in Stage II. It also concerns the processes of your data flow diagram from Stage III.

For example, the apps authentication system could be attacked with a virus. Authentication could also be attacked if a threat actor social engineers an employee.

In the **Stage IV** row of the PASTA worksheet, list **2 types** of threats that are risks to the information being handled by the sneaker company's app.&#x20;

_**Pro tip:** Internal system logs that you will use as a security analyst are good sources of threat intel_

#### Step 5: List vulnerabilities that can be exploited by those threats

Stage V of PASTA is the vulnerability analysis. Here, you need to consider the attack surface of the technologies listed in Stage II.

For example, the app will use a payment system. The form used to collect credit card information might be vulnerable if it fails to encrypt data.

In **Stage V** of the **PASTA worksheet**, list **2 types** of vulnerabilities that could be exploited.

_**Pro tip:** Resources like the_ [_CVE® list_](https://cve.mitre.org/cve/search_cve_list.html) _and_ [_OWASP_](https://owasp.org/www-community/vulnerabilities/) _are useful for finding common software vulnerabilities._

#### Step 6: Map assets, threats, and vulnerabilities to an attack tree

In Stage VI of PASTA, the information gathered in the previous two steps are used to build an attack tree.

Open the **PASTA attack tree** resource. Review the diagram and consider how threat actors can potentially exploit these attack vectors.

**Note:** Applications like this normally have large, complex attack trees with many branches.

#### Step 7: Identify new security controls that can reduce risk

PASTA threat modeling is commonly used to reduce the likelihood of security risks. In Stage VII, the final goal is to implement defenses and safeguards that mitigate threats.

In **Stage VII** of the **PASTA worksheet**, list **4 security controls** that you have learned about that can reduce the chances of a security incident, like a data breach.

### What to Include in Your Response

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/KYJwq2UMSXmacAE7O98-jQ_c608a5a0e22e4f16838a5a1c044e7cf1_plm_lYxT2yhIm-YslimdR6JQrS1zPKnviQczHpw0lG4YyfjH2wi2F9XNw1YNHS-rcrjanh-lvzbhxgTQssjT-KO-EuTODRWaw1iRC3K5xy14okp3grBVoB-7xD87EbAL8z7EmJnByXm_jJJi5_WOAPnwSJw8HALJZdnjGy9AV70BlG2-U6xzNNjI5p7WFA?expiry=1734825600000&#x26;hmac=BAwIQFkKSZYGwxaY4_JP8-BhvEyz1q2HLARFCBFYmFA" alt=""><figcaption></figcaption></figure>

Be sure to address the following elements in your completed activity:&#x20;

* **2-3** business objectives
* **2-3** technology requirements
* **2** potential threats
* **2** system vulnerabilities
*   **4** defenses that limit risk\
    \


    <figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/KYJwq2UMSXmacAE7O98-jQ_c608a5a0e22e4f16838a5a1c044e7cf1_plm_lYxT2yhIm-YslimdR6JQrS1zPKnviQczHpw0lG4YyfjH2wi2F9XNw1YNHS-rcrjanh-lvzbhxgTQssjT-KO-EuTODRWaw1iRC3K5xy14okp3grBVoB-7xD87EbAL8z7EmJnByXm_jJJi5_WOAPnwSJw8HALJZdnjGy9AV70BlG2-U6xzNNjI5p7WFA?expiry=1734825600000&#x26;hmac=BAwIQFkKSZYGwxaY4_JP8-BhvEyz1q2HLARFCBFYmFA" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/KYJwq2UMSXmacAE7O98-jQ_c608a5a0e22e4f16838a5a1c044e7cf1_plm_lYxT2yhIm-YslimdR6JQrS1zPKnviQczHpw0lG4YyfjH2wi2F9XNw1YNHS-rcrjanh-lvzbhxgTQssjT-KO-EuTODRWaw1iRC3K5xy14okp3grBVoB-7xD87EbAL8z7EmJnByXm_jJJi5_WOAPnwSJw8HALJZdnjGy9AV70BlG2-U6xzNNjI5p7WFA?expiry=1734825600000&#x26;hmac=BAwIQFkKSZYGwxaY4_JP8-BhvEyz1q2HLARFCBFYmFA" alt=""><figcaption></figcaption></figure>



    **PASTA Worksheet**

    **I. Define business and security objectives**

    * The app must ensure data privacy and reassure users that their personal and financial information is securely handled.
    * The app should facilitate seamless buying and selling of sneakers, including direct messaging between buyers and sellers, and support rating and review features.
    * The app must support multiple secure payment options that comply with legal and industry regulations.

    **II. Define the technical scope**\
    &#xNAN;_&#x54;echnologies used by the application: API, PKI (AES, RSA), SHA-256, SQL_\
    I would prioritize evaluating the SQL database first because it stores sensitive user and payment information. If SQL queries are not properly secured, attackers could exploit vulnerabilities like SQL injection, leading to unauthorized data access or theft of financial details. Protecting the database is critical to safeguarding user trust and meeting compliance requirements.

    **III. Decompose application**\
    (Referencing the provided data flow diagram)\
    As users search and purchase sneakers, their requests pass through the front-end to the API, which queries the SQL database. User authentication and sensitive information exchanges rely on secure keys and hashing (PKI, SHA-256). Properly protecting these steps is essential for preventing data leaks or unauthorized access.

    **IV. Threat analysis**

    * **External Threat:** Attackers might attempt SQL injection attacks on the database through user input fields (e.g., search bar or checkout process).
    * **Internal Threat:** A malicious insider with database access might try to exfiltrate customer information or tamper with transaction records.

    **V. Vulnerability analysis**

    * **Input Validation Flaw:** User input fields not properly sanitized could allow SQL injection.
    * **Weak Configuration in PKI Setup:** Improper key management or outdated encryption algorithms could lead to compromised encryption keys and data exposure.

    **VI. Attack modeling**\
    (Referencing the provided attack tree)\
    An attacker could start by probing input fields for injection points, escalate to gaining unauthorized DB access, and then extract sensitive user data. Alternatively, if encryption keys are poorly managed, attackers could intercept and decrypt financial information during transactions.

    **VII. Risk analysis and impact**\
    **Four Security Controls to Mitigate Risk:**

    1. **Parameterized Queries / Prepared Statements:** Prevent SQL injection by ensuring user input is never directly concatenated into SQL queries.
    2. **Strict Input Validation and Sanitization:** Validate and sanitize all user-supplied data to block malicious code.
    3. **Robust Encryption and Key Management:** Use strong AES/RSA keys, rotate keys regularly, and securely store them to prevent unauthorized decryption.
    4. **Multi-Factor Authentication (MFA) and Access Controls:** Limit database and admin panel access to authorized personnel with MFA, reducing the risk of insider threats.
