# Subnetting and CIDR

Alright, let’s imagine **Subnetting and CIDR** as a **giant pizza party** with different rooms and zones to keep everything organized. We’re going to make this as fun and ADHD-friendly as possible!

#### **Subnetting: The Pizza Party Planner**

Think of a **network** as one huge pizza party. Everyone at the party is on the **same network** (pizza place), but it’s chaotic if everyone is just running around trying to grab pizza at the same time.

What if we broke the pizza party into **smaller groups**? We could have:

* A **group for cheese lovers** in one room.
* A **group for pepperoni fans** in another room.
* And a **group for veggie pizza** in a third room.

This is **subnetting**! We’re dividing the party (network) into smaller, more organized **subnets**. Each room is its own little world of pizza, so things move smoother, and everyone gets their slice faster. 🌍🍕

#### **Classless Inter-Domain Routing (CIDR): The Room Number**

Now, let’s get to **CIDR**, which tells us exactly **how big each room is** and how many people can fit inside.

Every room at the pizza party has a specific **room number**, like **198.51.100.0/24**. The first part (**198.51.100.0**) is like the **main address** of the pizza party, but the **/24** part? That’s the **magic number** that tells us how many people can party in this room.

* **/24** means you can invite **256 people** (or 256 IP addresses).
* **/28** would be a smaller room, where only **16 people** can fit.

The lower the number, the bigger the room (subnet) and the more pizza fans you can invite. The higher the number, the smaller and more exclusive the party gets. 🎉🍕

#### **Zones for Extra Security: Who’s Invited Where?**

Just like in a real party, you might not want everyone having access to everything:

* **Cheese Lovers Room**: Only cheese fans are allowed in.
* **Veggie Room**: Only veggie eaters get access here.
* **Restricted Zone**: Super-secret VIP room where only special guests can go.

These **zones** are like the different parts of your network, some are more protected than others. The **uncontrolled zone** might be where random guests (like the internet) hang out, while the **restricted zone** is for trusted friends only (important internal servers). 🏰🔐

#### **Security Benefits of Subnetting: Keep the Party Under Control**

By **subnetting**, you’re making sure everyone stays in their own room, enjoying their pizza without chaos. If someone tries to sneak into the **VIP room**, subnetting makes it harder for them to crash the party. Plus, it makes the whole event run smoother and faster because no one is wandering around lost.

#### **Key Takeaway: Subnetting Makes the Party Better!**

* **Subnetting** divides a big chaotic network into smaller, more manageable groups (just like our pizza rooms).
* **CIDR** tells us how many people can fit in each room.
* By keeping things organized, we make sure the party (network) is **efficient** and **secure**!

It’s all about keeping the fun going and protecting the pizza! 🍕🎉 Now, go grab your slice, and let’s keep the party going!

***

Let’s dive into how **subnetting** and **CIDR** are like your **ultimate defense strategy** and **sneaky attack plan** in a cyber battle! Get ready to gear up as a defender and a hacker in this fun and ADHD-friendly way.

#### **Defending Against Cyber Attacks: Subnetting as Your Castle’s Defense!**

Imagine you’re the king/queen of a castle (your network) trying to protect your kingdom from **invading cyber attackers**. Your kingdom is **subnetted** into smaller sections, each with a specific purpose—just like your network.

**1. Dividing the Castle (Network) for Better Defense**

Instead of having **one big kingdom** (one big network) where attackers could waltz right in, you’ve split it up into smaller sections (subnets), like:

* **The outer courtyard** (your public-facing servers).
* **The inner keep** (sensitive data).
* **The dungeon** (restricted areas).

These sections help contain the damage if an attacker gets in. If they breach one section (subnet), they can’t roam freely around your entire castle—they’re stuck in that section until you can stop them. This is **network segmentation** in action!

**2. CIDR: How Big Is Your Castle Wall?**

Now, you’ve built walls around each section of your kingdom with CIDR. The **CIDR notation** tells you **how big each wall is** and how many IP addresses (people) are allowed into that subnet.

For example:

* **/24** is a big wall with lots of guards—protecting a large area, like a network with **256 IPs**.
* **/28** is a smaller wall, maybe protecting a few key servers with only **16 IPs**.

You can strategically **limit access** to sensitive sections of your network (like your “dungeon”) by giving them smaller subnets with fewer IP addresses, so attackers can’t find many weak spots to exploit.

**3. Blocking Attackers: Subnet Firewalls**

Each subnet (zone) has its own firewall, so if someone breaches the **outer courtyard**, they still have to face more firewalls to get deeper into the castle. The more layers of defense, the harder it is for attackers to move around.

If an attacker tries to break into your **keep** (your valuable data), subnetting ensures they’re limited to just one area and can’t get to the whole kingdom. It’s like giving them **a single locked room** to deal with instead of your entire castle!

***

#### **Penetration Testing: Subnetting as Your Hacker’s Toolkit**

Now, let’s flip the script. You’re a **penetration tester**, sneaking into someone else’s network (with permission, of course!). How do you use subnetting and CIDR in **offensive hacking**?

**1. Recon: Mapping the Network (Castle Layout)**

Your first task as a hacker is to figure out the **layout of the castle** (the network). By **scanning the network**, you’ll see how it’s divided into subnets. Each subnet tells you where the **valuable data** might be hiding.

For example:

* A **/24 subnet** might be protecting public-facing services—**less valuable** but a good starting point.
* A **/28 subnet** might be where **critical data** is stored. Since it’s smaller, you know it’s more protected and likely worth attacking.

By identifying the different **CIDR notations** used on the network, you can figure out where the important stuff is!

**2. Bypassing Defenses: Finding Open Doors**

Subnetting may divide the network, but every **wall has a door** (open port or service). As a penetration tester, your job is to find those doors.

* You use tools like **Nmap** to scan the subnets and find **open ports**.
* Once you’ve found an open door, you try to **sneak through** using exploits (think of it as picking the lock).

By understanding how the network is segmented, you can prioritize which **rooms** (subnets) to target and find the best route to sneak through the network.

**3. Pivoting: Moving from One Subnet to Another**

Once you’ve broken into one subnet, you don’t stop there! Hackers want to **pivot**—move from the compromised subnet to the next one, like hopping from one section of the castle to another.

But remember, **subnetting** makes this hard! There are firewalls and other defenses between subnets. You’ll need to:

* **Find vulnerabilities** that allow you to jump between subnets.
* **Use lateral movement** tactics to exploit services between different subnets.

If you successfully pivot, you’re getting closer to the most sensitive data, just like making your way through different castle layers!

**4. CIDR: Limit the Scope of Your Attack**

As a **pen tester**, you don’t want to waste time attacking the entire network. You focus on specific **CIDR blocks** to limit your attacks.

For example, if you see a **/28 subnet**, it’s a smaller target, meaning there are fewer IPs to test, but it likely contains **important assets**. Focusing on smaller CIDR subnets is a more **efficient** way to hack because you target what’s valuable, not just what’s big.

***

#### **Key Takeaways for Cyber Defense and Pen Testing**

* **Defending**: Subnetting creates **layers of defense** in your network, making it harder for attackers to move freely. CIDR lets you control the size of each subnet, limiting exposure.
* **Attacking**: As a hacker, subnetting gives you clues on where to strike and what’s worth targeting. CIDR helps you **scope** your attack to focus on the most valuable parts of the network.

Whether you’re defending your network or breaking into one, **subnetting and CIDR** are powerful tools that help you **control the battlefield**!

Now go forth, defender of castles and master of sneaky attacks!
