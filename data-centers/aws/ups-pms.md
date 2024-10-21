# UPS PMs

Alright, let’s go on a fun journey to maintain the mighty UPS (Uninterruptible Power Supply) at an Amazon AWS datacenter! Think of the UPS as the superhero that saves the day when power fails. It’s got to be in tip-top shape, so here’s how we give it the royal treatment in a friendly and action-packed way.

#### Step 1: **"Suit up the hero" (Prep Time!)**

* **Checklist in hand**: Before jumping in, gather your tools, safety gear, and trusty clipboard (or tablet). You don’t want to be like Batman without his utility belt.
* **Safety first**: Gloves, glasses, and maybe a hard hat—it’s time to become a power supply superhero yourself!

Every superhero needs the right tools to get the job done. When prepping for a UPS preventative maintenance (PM) in a data center, you’ll need a **power-packed toolkit** that ensures you’re ready for any situation. Here’s a breakdown of the tools you should gather for Step 1 in your UPS PM adventure:

#### **1. Multimeter (Digital or Analog)**

* This is your **energy scanner** for checking voltages, currents, and continuity. You'll use this to measure battery voltage levels and verify electrical connections.

#### **2. Insulated Screwdrivers**

* For safely removing panels, tightening or loosening battery terminals, or accessing components inside the UPS. Insulated tools help protect you from accidental contact with live circuits.

#### **3. Clamp Meter**

* This is the **Thor’s hammer** of meters, allowing you to measure current without breaking the circuit. It’s great for checking how much current the UPS is drawing or supplying.

#### **4. Battery Load Tester**

* To test how the UPS batteries hold up under load, making sure they’re still capable of powering systems during an outage.

#### **5. Torque Wrench**

* For **tightening down connections** to the manufacturer-specified torque values. You don’t want loose connections—those can cause heat buildup or electrical failure.

#### **6. Infrared Thermometer (Thermal Imager Optional)**

* Use this to spot any **overheating components** or connections, which could indicate a problem. It’s like a thermal vision mode for your superhero mission.

#### **7. Insulation Resistance Tester (Megger)**

* If you need to check the **insulation integrity** of cables and components, the Megger is your best friend. This helps detect if any cables are breaking down and could cause faults later on.

#### **8. PPE (Personal Protective Equipment)**

* Safety first! You’ll need your:
  * **Insulated gloves** for electrical work.
  * **Safety glasses** to protect your eyes.
  * **FR-rated clothing** (fire-resistant), especially when working around electrical equipment.
  * **Ear protection** (sometimes data centers can get noisy).

#### **9. Cable Ties and Electrical Tape**

* Always have these on hand for **tidying up cables** and securing connections. Batman might not need cable ties, but you definitely do!

#### **10. Cleaning Supplies**

* Dust and debris are a UPS’s worst enemies. Have some:
  * **Antistatic wipes** for cleaning sensitive electronic parts.
  * **Compressed air** for blowing out dust from vents and fans.

#### **11. UPS Software/Diagnostics Tools**

* Some UPS units come with proprietary software or require a **laptop or tablet** with diagnostics software to check the system status, logs, and any hidden error messages.

#### **12. Flashlight/Headlamp**

* Sometimes, your mission takes you into **dark corners** of the datacenter or cramped UPS enclosures, so a good light is crucial!

#### **13. Arc Flash Suit (for High Voltage Tasks)**

* If your maintenance involves any live electrical work on **high-voltage systems**, have your **arc flash suit** ready. This might not be needed for regular PM but should be close by for tasks that do involve live electrical circuits.

***

#### **Bonus Hero Gadgets (If Needed):**

* **Laptop/Tablet**: For checking manuals, inputting data, or running diagnostics.
* **Label Maker**: Helps with organization if you need to tag connections, cables, or components after checking them.

With this mighty arsenal of tools, you’ll be prepared for just about anything the UPS can throw at you during the PM. Now that you're "suited up," you’re ready to step into action and ensure the UPS can keep AWS's servers running no matter what!

#### Step 2: **"Power Nap for the UPS" (Switch to Bypass)**

* We can’t poke around in a live superhero’s circuits! First, we tell the UPS to take a break by putting it in **bypass mode**. This is like setting our hero on standby while the power still flows through the backup.

#### Step 3: **"Check the Heartbeat" (Visual Inspection)**

* **Look around like a detective**: Walk around the UPS and look for signs of trouble. Does anything smell weird? Any blinking lights or error messages on the display? You’re on the lookout for sneaky problems!
* **Inspect the batteries**: Are the batteries clean and in good shape? Like making sure Iron Man’s suit isn’t dented, you want no leaks, corrosion, or bloated batteries.

#### Step 4: **"Recharge the Hero’s Armor" (Battery Checks)**

* **Voltage check!** Using your trusty multimeter (think of it as your energy scanner), check that each battery is at the right voltage. If not, you may need to call for reinforcements (battery replacement)!
* **Battery discharge test**: You let the UPS flex its muscles by briefly running off the batteries to see if they can handle the load. Like training before a big fight, you want to ensure the UPS can perform when the main power goes down.

#### Step 5: **"System Scan" (Check UPS Logs)**

* **Dive into the logs**: It’s like checking a superhero’s past missions. Review the event logs on the UPS for any warnings or errors. You’re looking for anything unusual that happened since the last check-up.

#### Step 6: **"Cool and Collected" (Cooling System Check)**

* **Fan check**: The UPS can’t overheat during battle! Make sure the fans are spinning freely, and there’s no dust buildup. Clean those bad boys out if needed—just like keeping your hero cool under pressure.

#### Step 7: **"Gear up!" (Switch Out of Bypass)**

* After giving the UPS a clean bill of health, it’s time to bring it back to action. Switch it out of bypass mode and let it take its place as the silent defender once again.

#### Step 8: **"Final Test" (Run Diagnostics)**

* **Run a system self-test**: This is like a superhero’s final check before heading into battle. Most UPS units have a built-in self-test that checks the batteries, load, and other internal systems to make sure everything’s good to go.

#### Step 9: **"Log the Adventure" (Document Everything)**

* No superhero mission is complete without documentation! Make sure to note all the checks, tests, and any issues that were fixed. This way, you’ll know the next time your UPS needs a tune-up.

And there you have it! The UPS is back in action, standing by like a true superhero, ready to keep Amazon’s servers powered through any storm. You’re now the hero behind the hero, making sure the AWS cloud stays up and running! 🦸‍♂️🔋
