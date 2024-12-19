# Cyber attacker mindset

**Scenario: “The Castle in the Cloud”**

You’ve just been hired as a junior security analyst at a mid-sized tech company called **CloudKeep Systems**. The company specializes in financial-data management for several smaller businesses. Much like the old castle analogy you learned about, CloudKeep has strong outer walls (firewalls), watchtowers (intrusion detection systems), and gates with guards (login credentials). But as the company’s services have moved to the cloud, its digital “castle” now faces new challenges. It has more “entrances” to defend, and you’ve been tasked to help.

**Your Role:**\
You’re working on the security team that needs to apply an “attacker mindset.” This means you’ll be looking at the company’s environment as if you were a threat actor. By doing so, you hope to identify weaknesses before the bad guys do.

**The Setup:**\
CloudKeep’s network isn’t just a single fortress anymore. Employees access resources from various locations, sometimes using personal devices. Sensitive financial data is stored and accessed through multiple cloud-based applications. The CEO has asked your team to verify that current security measures are sufficient—especially given a recent rise in brute force attacks and rumors of disgruntled employees in the ranks. Your first task is to analyze the attack surface and consider various threat actors and attack vectors.

***

#### Part 1: Identifying the Attack Surface

**Situation:**\
You know that the company’s physical attack surface includes on-site employees, their laptops, and even personal devices used off-site (like a salesperson’s tablet). The digital attack surface spans cloud services, remote workers logging in from around the world, and new collaboration tools that connect directly to client networks. All of these are potential entry points.

**Your Exercise:**

1. Identify **three distinct entry points (attack vectors)** at CloudKeep that a threat actor might try to exploit. For each entry point, note if it’s physical or digital and why it could be appealing to an attacker.
2. Considering **threat actor types** (competitors, state actors, criminal syndicates, insider threats, shadow IT), choose one threat actor type and explain:
   * Their likely motivation for attacking CloudKeep.
   * Which entry point they’d be most likely to focus on.
   * How that chosen threat actor might differ from another type of threat actor (e.g., how a criminal syndicate’s goals differ from an insider threat’s).

***

#### Part 2: Thinking Like an Attacker

**Situation:**\
Your team is preparing to run a simulation (just like a red team exercise) to see how attackers might try to break into CloudKeep’s primary accounting application—a cloud-based financial dashboard. The dashboard requires usernames, passwords, and, in some cases, a second factor (MFA token). However, the company just discovered that one of its service partners had a credential leak last month. Those credentials might be in the hands of malicious hackers, enabling them to attempt brute force attacks (especially credential stuffing) against CloudKeep’s login portal.

**Your Exercise:** 3. Imagine you’re planning a **proactive simulation (red team exercise)** against the CloudKeep financial dashboard. Describe the steps you would take to approach this attack if you were the adversary:

* What information would you look for first?
* Which brute force method(s) would you consider using (e.g., dictionary attacks, credential stuffing, etc.) and why?
* What tools might you use to speed up the brute forcing process?

4. Now, switching back to the defender’s mindset, propose **three preventative measures** CloudKeep could implement to reduce the risk of a successful brute force attack. For each measure, explain:
   * How it raises the difficulty level for attackers.
   * Which part of the brute force “chain” it breaks or slows down.

***

#### Part 3: Decision-Making Under Pressure

**Situation:**\
News just came in: a suspicious IP address has made thousands of login attempts overnight against the financial dashboard. You’re alerted to this pattern. As a security analyst, you have to make a quick call. The login attempts haven’t been successful yet, but the attempts keep coming.

**Your Exercise:**\
5\. You have three immediate options:

* **Option A:** Immediately lock every account with repeated failed login attempts.
* **Option B:** Implement a CAPTCHA challenge for every login attempt from suspicious IPs.
* **Option C:** Rapidly deploy MFA across all user accounts, even though it’s going to be an organizational headache in the short term.

Choose one option and justify your selection. Consider immediate vs. long-term impact and the user experience trade-offs.

***

***

