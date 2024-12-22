# The OSI Model

#### 🎮 ADHD-Friendly OSI Model Notes! 🚀

#### 🌐 **What's the OSI Model?**

* **OSI** stands for **Open Systems Interconnection**. It’s like a **7-level** tower where each floor has its own job to keep the internet running smoothly! 🏢
* Helps network pros understand how **devices communicate** across networks and **where issues happen**!

***

#### 🏛️ **OSI vs. TCP/IP Models:**

* **OSI** = 7 layers (more detail) 🍰
* **TCP/IP** = 4 layers (more streamlined) 🎯
* **Both**: Guide to how data moves around, and security pros use them to **troubleshoot attacks**!

### !\[\[Pasted image 20240911194813.png]]

#### 🎢 **The 7 Layers of OSI Model** 🎢

Let’s travel from **Layer 7** (up high!) down to **Layer 1** (ground level)!

***

**🌐 Layer 7: Application Layer**

* Where you interact with the **internet** (yay, web browsers!) 🖥️
* **Examples**:
  * Using HTTP/HTTPS for web pages 🌍
  * Email with SMTP ✉️
  * Translating domain names (like google.com) into IP addresses using DNS 🔍

**🔐 Layer 6: Presentation Layer**

* This is the **translator** 🗣️. It converts data into formats both sender and receiver can understand.
* Handles **encryption** & **compression**.
  * **Example**: SSL for safe websites (look for HTTPS!) 🔒

**🔗 Layer 5: Session Layer**

* Think of this layer as managing **conversations** between devices 📞.
  * It keeps the connection going while data is being transferred, **restarts** if something goes wrong, and **ends** when done.

***

**🚚 Layer 4: Transport Layer**

* Breaks data into **smaller pieces** and manages **speed** for smooth delivery 🎯.
* **Key Protocols**:
  * **TCP**: Reliable delivery! 📬
  * **UDP**: Quick but less reliable, great for fast stuff like video streaming! 🎥

**📦 Layer 3: Network Layer**

* Finds the **best route** for data to travel 🛤️. Uses **IP addresses** to send packets between networks.
  * **Routers** and **IP** live here! 🗺️

***

**🖧 Layer 2: Data Link Layer**

* Focuses on **local networks**. Deals with how data is sent inside your home/work network 🏡.
* Think of it as organizing traffic on your local street! 🚦
  * **Devices** like **switches** and **network interface cards** live here 🛠️.

**🛠️ Layer 1: Physical Layer**

* This is the **ground floor** where all the **hardware** lives!
  * Wires, cables, modems, and **1s and 0s** zooming through them 🧑‍🔧.

***

#### 🧠 **Key Takeaways:**

* **OSI Model** = 7 layers from user interactions (Layer 7) to physical hardware (Layer 1) 🏗️.
* Network pros use **both OSI and TCP/IP models** to talk about **issues and security threats**.

📊 **Remember**: It’s like a layered cake 🎂. Data goes up and down, and each layer has its own job to keep the internet connected!
