# Identify system vulnerabilities

**Contextualized Scenario:**

Imagine you’ve just joined a small e-commerce startup called “ShopSmart.” The company sells unique, handmade products sourced from around the globe. They rely heavily on a remote database server that stores sensitive customer and vendor information, including personal details and transaction histories. For the last three years, this database has been left fully accessible to the public internet, since remote employees and partners needed quick access. No one has thoroughly assessed its security posture before.

Recently, you’ve discovered this open access is a serious vulnerability. If attackers find it, they could steal or alter sensitive data, disrupt customer orders, or erode the trust customers place in the brand. The leadership team at ShopSmart has asked you to perform a vulnerability assessment and propose a plan to fix any identified issues. You need to determine likely threat sources, possible threat events, assign risk scores, and then suggest a remediation strategy.

***

**Interactive Exercises:**

1. **Identification of Threat Sources & Threat Events:**\
   Consider who or what might want to exploit this vulnerable database. Then think about what kind of events those threats could initiate to harm ShopSmart.
   * **Exercise:** List three potential **threat sources** (e.g., outsider hackers, competitors, disgruntled former employees, etc.) that could target the publicly accessible database. For each threat source, identify one **threat event** (e.g., exfiltration of sensitive information, denial-of-service attacks, etc.) that source might carry out.
2. **Risk Scoring:** Using a scale from 1 to 3 for both likelihood and severity (with 3 being high), estimate how likely and severe each of the three threat events you’ve identified would be.
   * **Exercise:** For each threat event, provide a likelihood score and a severity score, then multiply them to get a risk score (likelihood x severity = risk).\
     Example: Competitor wants to steal customer data. Likelihood = 2 (somewhat likely), Severity = 3 (catastrophic if it happens), Risk = 6.
3. **Approach & Rationale:** You’ve chosen these particular threats and events. Now explain your reasoning.
   * **Exercise:** Write a short rationale (3-5 sentences) explaining why you chose these three specific threats and why you consider them significant. Mention how you estimated the likelihood and severity.
4. **Remediation Strategy:** Now that you’ve identified and scored the risks, you need to propose ways to reduce them. Think about techniques like restricting database access, implementing the principle of least privilege, or adding multi-factor authentication.
   * **Exercise:** Recommend at least two security controls or solutions (e.g., network firewalls, regular patching, MFA, role-based access controls) that could help mitigate or remediate these vulnerabilities. Explain how these controls would reduce either the likelihood or the severity (or both) of the identified threats.

***

**Instructions for Your Response:**

Please respond with the following:

* Your three chosen threat sources and their corresponding threat events.
* The likelihood, severity, and overall risk score (1–9) for each threat event.
* A short rationale (3-5 sentences) explaining your reasoning for selecting these threats and how you arrived at the scores.
* Two remediation steps and a brief explanation of how they help reduce the identified risks.

Once you respond, I’ll provide detailed feedback on your choices, scores, approach, and remediation plan.

***

***



***

***

Below is a step-by-step walkthrough showing how you might answer the interactive exercises. I’ll not only give you the final answers, but I’ll also explain the reasoning behind each step. This way, you’ll learn how to think like a cybersecurity analyst performing a vulnerability assessment.

***

#### 1. Identification of Threat Sources & Threat Events

**How to Think About It:**\
A “threat source” is someone or something that can cause harm to your organization’s information system. Since the database is publicly accessible, consider who might want to take advantage of that situation. Internal employees, competitors, or outside hackers are common examples. A “threat event” is the specific harmful action they might carry out, like stealing data or crashing the server.

**Chosen Threat Sources & Events:**

1. **Threat Source:** External Hackers (Outsiders)\
   **Threat Event:** Obtain sensitive information via exfiltration.\
   &#xNAN;_&#x52;easoning:_ An outsider who discovers the open database might try to steal customer data (names, addresses, payment info) to sell on the dark web.
2. **Threat Source:** Competitors\
   **Threat Event:** Alter/Delete critical information.\
   &#xNAN;_&#x52;easoning:_ A competitor might want to disrupt your operations by corrupting or deleting key data, harming your reputation and business processes.
3. **Threat Source:** Malicious Insider (A disgruntled employee)\
   **Threat Event:** Conduct a Denial of Service (DoS) attack.\
   &#xNAN;_&#x52;easoning:_ An unhappy employee with some internal knowledge could bombard the system to make it unavailable to authorized users, halting business operations.

***

#### 2. Risk Scoring

**How to Think About It:**\
We use a 1–3 scale for both likelihood and severity:

* **Likelihood:** How likely is it that this event will happen (High=3, Moderate=2, Low=1)?
* **Severity:** If it happens, how bad would the impact be (High=3, Moderate=2, Low=1)?
* **Risk Score:** Likelihood x Severity (ranges from 1 to 9, with higher numbers being more concerning).

**Assigning Scores:**

1. **External Hackers → Data Exfiltration:**
   * **Likelihood:** 3 (High)\
     &#xNAN;_&#x4A;ustification:_ Publicly accessible databases are commonly targeted by automated scans and malicious scripts on the internet. Attackers frequently look for these targets.
   * **Severity:** 3 (High)\
     &#xNAN;_&#x4A;ustification:_ Losing sensitive customer data can lead to severe financial loss, reputational damage, regulatory penalties, and loss of customer trust.
   * **Risk:** 3 (Likelihood) x 3 (Severity) = 9
2. **Competitors → Alter/Delete Critical Information:**
   * **Likelihood:** 2 (Moderate)\
     &#xNAN;_&#x4A;ustification:_ While a competitor might not always attempt something illegal, the open database significantly lowers their barrier to attack, increasing the possibility.
   * **Severity:** 3 (High)\
     &#xNAN;_&#x4A;ustification:_ Altering or deleting critical data could stop the business from fulfilling orders, harm daily operations, and severely impact trust and revenue.
   * **Risk:** 2 (Likelihood) x 3 (Severity) = 6
3. **Malicious Insider → Denial of Service Attack:**
   * **Likelihood:** 2 (Moderate)\
     &#xNAN;_&#x4A;ustification:_ Not all employees turn malicious, but it’s not uncommon for disgruntled insiders to misuse access. The open nature of the database might make it easier to DoS.
   * **Severity:** 2 (Moderate)\
     &#xNAN;_&#x4A;ustification:_ A DoS attack might temporarily prevent access to the database, disrupting daily operations. This can lead to lost sales and frustrated employees, but it may be recoverable with quick intervention.
   * **Risk:** 2 (Likelihood) x 2 (Severity) = 4

***

#### 3. Approach & Rationale

**How to Think About It:**\
Explain why you picked these threats and how you estimated their impact. This gives stakeholders confidence in your analysis and shows you’re using sound judgment rather than guessing randomly.

**Sample Rationale (3-5 sentences):**

_I chose these three specific threats because they each target different aspects of the company’s operations and data. The external hackers pose a severe risk due to the data’s sensitive nature and high value, making both their likelihood and severity scores high. Competitors may be somewhat less likely to engage in overt sabotage, but if they do, the consequences would be severe. Insiders, while typically more trustworthy, can become threats if they are disgruntled or bribed, and their knowledge of the system might enable a moderately likely and damaging DoS attack. In each case, the scoring of likelihood and severity was guided by considering how motivated or skilled the attackers might be and the extent of damage their actions would cause._

***

#### 4. Remediation Strategy

**How to Think About It:**\
You’ve identified the risks; now suggest how to fix or reduce them. Think of controls that lower the chance (likelihood) or reduce the damage (severity). Consider well-known security best practices, such as reducing public access, enforcing multi-factor authentication, or tightening user permissions.

**Sample Remediation Steps (3-5 sentences):**

_To address these risks, the company should first implement stronger access controls. This can include restricting direct public access to the database and requiring role-based authentication and the principle of least privilege for all internal users. Multi-factor authentication (MFA) should be enabled so that even if passwords are compromised, attackers can’t easily log in. Regular patching and updates, combined with network-level firewalls and intrusion detection systems, will help prevent unauthorized data exfiltration and DoS attempts. By adopting these controls, we reduce both the likelihood and severity of potential attacks, ultimately improving the overall security of the system._

***

#### Key Takeaways:

* **Threat sources** are who or what could harm your system. They can be internal (employees) or external (hackers, competitors).
* **Threat events** are the actions these threat sources might carry out, such as data theft or service disruption.
* **Risk scoring** uses likelihood and severity to prioritize which vulnerabilities to fix first.
* **Approach rationale** helps stakeholders understand the logic behind your decisions and trust your recommendations.
* **Remediation strategies** align with identified risks, lowering the chance of successful attacks and limiting their impact if they do occur.

By understanding and applying these steps, you’ve essentially walked through the process of a real vulnerability assessment. Over time, this approach becomes second nature, and you’ll be able to quickly spot risks and propose solutions in any cybersecurity role.

***

***



***

***



***

***



***

***



***

***



***

***



***

***



***

***
