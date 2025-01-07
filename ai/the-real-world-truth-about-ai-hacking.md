---
description: Video by David Bombal, optimized for text by me.
---

# The real world truth about AI Hacking

[https://www.youtube.com/watch?v=YZqiWFyq-OE\&t=20s](https://www.youtube.com/watch?v=YZqiWFyq-OE\&t=20s)

Below is a **fun**, **ADHD-friendly**, **conversational recap** of the interview between David Bombal and Omar Santos on **AI in cybersecurity**—including how attackers are exploiting it, how defenders are responding, and where there’s still hope!

***

### 1. **AI Attacks Are Already Here**

* **Yes, Attackers Use AI**: It’s not just sci-fi or deepfake Tom Cruise videos. Hackers are increasingly leveraging AI to **automate reconnaissance**, **generate exploits**, and **evade defenses**.
* **OSINT on Steroids**: Tools like LangChain and vector databases let attackers do mass data scraping and analysis while they sleep. They basically create an “AI agent army” doing recon 24/7.
* **Off-the-Shelf Models**: Even if ChatGPT has guardrails, attackers use uncensored open-source models (like some fine-tuned Llama derivatives) with zero constraints to craft malicious code.

***

### 2. **Why It’s a Wild West**

* **Data Leaks Everywhere**: Many big platforms (e.g., Slack) have used customer data to train their own AIs without explicit permission. Add in supply chain issues (like malicious models on Hugging Face), and it’s chaos.
* **Fast Tech Growth**: AI is evolving so quickly that **new vulnerabilities** pop up faster than we can define them. By the time a book or standard is published, the technology might have already shifted.
* **Prompt Injection Mayhem**: Attackers hide malicious prompts inside PDFs or chat messages (invisible to the human eye) to trick AI agents. This can bypass normal safety checks.

***

### 3. **Defensive AI: Where’s the Hope?**

* **Yes, There’s Hope**: Security-minded orgs (Cisco, Microsoft, NVIDIA, etc.) are banding together to **develop new frameworks** and **best practices** for securing AI.
* **Securing the Whole Pipeline**: It’s not just about locking down the model itself; you’ve also got:
  * **Training environments** (who’s tampering with your data?).
  * **Supply chain** (which models/libraries are you pulling from Hugging Face?).
  * **Access control** for AI agents (these “agents” can’t just run as root!).
* **Regulations & Standards**: Groups like Oasis, NIST, and the Linux Foundation are cranking out guidelines on how to **inventory** AI models (AI “bill of materials”), detect tampering, and handle vulnerabilities.

***

### 4. **Career Opportunities & Getting Started**

* **AI Will Need Cyber Pros**: AI isn’t replacing jobs; it’s changing them. Tier 1 SOC analysts might now need to handle more advanced tasks, but they’ll have AI to help them.
* **Core Skills Still Matter**: Networking fundamentals (e.g., CCNA) + some programming basics (Python!) are crucial. You need to know how the underlying technology works before you can secure it or break it (ethically!).
* **Ethical Hacking**: Start with a blueprint (like **PenTest+**), then move to advanced certs (like **OSCP**). Many existing cyber certs are **updating** their blueprints to include AI-related content.
* **Focus on “How AI Helps/Harms”**: Think beyond ChatGPT. Learn how vector databases, retrieval augmented generation, and deep learning frameworks actually fit into real systems—so you know where the bad guys can slip in.

***

### 5. **Key Takeaways**

1. **AI Is Everywhere**: Attackers are using it to automate and scale. Defenders are racing to adapt.
2. **“Abstraction on Abstraction”**: Non-technical folks can spin up advanced AI to do OSINT/hacking in minutes. That’s terrifying (and also kind of impressive).
3. **Securing AI = Holistic**: Don’t just guard the model. Guard the training data, the environment, the APIs, the supply chain… basically everything.
4. **People Will Still Matter**: Human expertise, creativity, and oversight remain critical. AI might write your code or do your recon, but you still need to interpret results, respond to anomalies, and ensure ethical use.
5. **Keep Learning**: The best strategy is constant upskilling. Understand fundamentals (networking, coding, security 101) and keep an eye on AI-specific developments so you can ride the wave, not be crushed by it.

***

### 6. **Final Word**

It’s not all doom and gloom! **Industry collaboration** and new standards are emerging every day to tackle the “AI Wild West.” Meanwhile, there’s a huge need for **tech-savvy defenders** who can anticipate new attack vectors and keep AI systems secure. If you’re looking for a cutting-edge cybersecurity career, **AI + Security** is your ticket to never being bored again.

**Stay caffeinated, stay curious, and secure all the things!**
