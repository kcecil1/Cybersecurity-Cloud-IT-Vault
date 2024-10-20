# Engineering Operations Rounds

Imagine you're a **Data Center Detective** on a mission to keep Amazon's data fortress running smoothly. You’re about to embark on your daily rounds, but don’t worry—it’s like a quest full of clues, weird noises, and mysterious blinking lights! Here’s how your rounds could play out, complete with fun “what to look for” tips.

***

#### 1. **Check the Gear: The Machines Are Talking**

#### **Visual Inspection of Equipment and Systems**

* **Mission**: Is your equipment chatting in a normal tone or screaming for help? (Detect any physical issues, such as equipment damage, unusual vibrations, or abnormal noise.)
* **Look for**:
  * Are the machines purring like happy cats, or making strange noises?
  * Any lights flashing like a disco party? Could be trouble!
  * Check for leaks or puddles. No one invited water to this party!
  * Look for unusual sounds in generators, chillers, UPS systems, or HVAC units.
  * Ensure there is no physical damage, leaks, or debris around the equipment.
  * Verify that all equipment is properly labeled and accessible.
  * Check for any warning lights, alarm signals, or abnormal readings on equipment panels.

***

#### 2. **Power Patrol: Keep the Lights On (**Checking Power Systems)

* **Mission**: The power's gotta stay strong, like the heartbeat of the fortress. (Ensure reliable power supply to the data center.)
* **Look for**:
  * UPS batteries—are they feeling juiced up or exhausted? (Inspect **UPS (Uninterruptible Power Supply)** units for proper operation and battery levels.)
  * Generators ready for action or snoozing when they should be alert? (Ensure **generators** are in standby mode and ready to activate in case of a power failure.)
  * Verify that automatic transfer switches (**ATS**) are functional.
  * Circuit breakers—are they all chill, or have they thrown a tantrum? (Check electrical **circuit breakers** and fuses for any signs of overload or malfunction.)
  * Monitor **PDU (Power Distribution Units)** and power meters for consistent power delivery.

***

#### 3. **Cool It Down: Air Conditioner Superheroes (**Monitoring Cooling Systems)

* **Mission**: Keep the data fortress cool, no overheating allowed! (Maintain optimal temperatures for servers and equipment.)
* **Look for**:
  * Are the chillers and air conditioners working like ice ninjas? (Inspect **chillers** and **cooling towers** for proper operation.)
  * Any weird temperature spikes or areas feeling like a desert? Not good! (Look for any fluctuations in room temperatures, especially hot spots that could indicate cooling issues.)
  * Airflow blockage—imagine a fan blocked by a blanket. Not very helpful, right? (Ensure air handlers are operating without blockages and maintaining proper airflow.)
  * Check refrigerant levels and pump performance.
  * Verify that **CRAC (Computer Room Air Conditioning)** units are cooling efficiently.

***

#### 4. **Safety First: Fire-Busters on Patrol (**Fire Suppression and Safety Systems)

* **Mission**: Make sure the fire-safety squad is ready for action! (Ensure the facility's fire safety systems are operational.)
* **Look for**:
  * Smoke detectors—they should be silent, not beeping like crazy. (Verify that **smoke detectors** are functioning.)
  * Verify that **fire alarms** are functioning.
  * Inspect the status of the **VESDA (Very Early Smoke Detection Apparatus)** systems.
  * Fire suppression systems—ready to save the day, not leaking! (Check **fire suppression systems** (e.g., sprinkler systems, gas systems) for leaks or readiness issues.)
  * Emergency exits—clear for a quick getaway (in case of dragons... or fire). (Ensure emergency exits are clear, and **emergency lighting** is functional.)

***

#### 5. **Network Ninjas: Keep the Wi-Fi Woes Away (**Network and Connectivity Monitoring)

* **Mission**: Keep that sweet internet flowing smoothly through the veins of the fortress. (Maintain continuous network connectivity.)
* **Look for**:
  * Are cables connected, or are they loose like spaghetti? (Inspect **network cables** and **switches** for any disconnections or faults.)
  * Any network ghosts (a.k.a., connection dropouts)? Spooky! (Check for **latency or connectivity issues** in the network infrastructure.)
  * Blinking lights on network switches—are they talking, or throwing a silent tantrum? (Monitor **network status** via software tools and physical checks of routers and switches.)

***

#### 6. **Write it Down: The Data Detective’s Logbook (Logging and Documentation)**

* **Mission**: Record your findings like a real-life Sherlock. (Document all findings, escalate potential issues, and ensure operational transparency.)
* **Look for**:
  * Anything weird, wonky, or about to go boom—write it down.
    * Document any repairs, alarms, or maintenance needed for future reference.
    * Log any abnormal readings or issues into the data center’s management system (e.g., via BMS/BAS software).
    * Record the status of critical equipment.
  * If something needs fixing, leave clues for the next detective! ()

***

#### 7. **Safety Dance: Keep Everyone Safe! (Safety Procedures)**

* **Mission**: Prevent accidents before they happen! (Ensure compliance with safety regulations.)
* **Look for**:
  * Are lockout/tagout (LOTO) procedures in place? No sneaky shortcuts allowed!
    * Check that **LOTO (Lockout/Tagout)** procedures are followed during maintenance work.
  * PPE (Personal Protective Equipment) checks—safety shoes, glasses and gloves on, heroes!
    * Ensure all personnel in restricted areas are using the proper **personal protective equipment (PPE)**.
  * Safety interlocks and e-stop buttons—make sure they’re ready for action. (Verify safety interlocks and e-stop buttons on critical systems.)

***

#### 8. **Backup Power: Ready for an Emergency Showdown (**Battery and Backup Systems**)**

* **Mission**: Make sure backup power is ready to save the day! (Ensure emergency backup power systems are ready to engage if needed.)
* **Look for**:
  * Battery banks—are they strong like superheroes, or running out of juice?
    * Inspect **battery banks** associated with the UPS for correct voltage and charge levels.
  * Generators—ready to jump into action if the main power takes a nap?
    * Test **backup generators** by running them periodically to confirm they engage and work as expected.
    * Fuel levels—are the tanks full, or is it time for a refill?
      * Check fuel levels and ensure that there are no blockages in fuel lines for generators.

***

#### 9. **Environmental Systems Check: No Sweat Allowed**

* **Mission**: Keep things cool, dry, and disaster-free! (Maintain optimal environmental conditions in the data center.)
* **Look for**:
  * Humidity sensors—keep the air nice and dry like a desert, not sticky like a swamp.
    * Ensure that **humidity** and **temperature sensors** are working and in safe ranges.
  * Water detection systems—leaks are NOT welcome here.
    * Monitor any water detection systems for leaks or condensation.
  * Dust or debris blocking the airflow? Time to sweep it away like a cleaning ninja!
    * Check that **air filtration systems** are working effectively to remove dust and contaminants.

***

#### 10. **Redundancy Ready: Backup Heroes On Standby (**Redundancy and Resiliency Checks**)**

* **Mission**: Make sure all backup systems are ready to swoop in!
* **Look for**:
  * Are redundant systems good to go, like a superhero sidekick ready to jump in?
    * Verify that there are redundant systems (e.g., UPS units, generators, cooling systems) for each critical piece of infrastructure.
  * Can everything switch to backup mode without you lifting a finger?
    * Ensure backup systems are configured correctly to take over automatically in the event of a primary system failure.
  * Test that failover plan—make sure it doesn’t let you down!
    * Test failover mechanisms to ensure they engage without manual intervention.

***

#### **The Most Common Things to Watch for on Your Quest**:

* **Abnormal Readings**: Like a villain plotting chaos—watch for weird voltage, temperature, current, pressure or airflow readings outside normal ranges!
* **Warning Lights & Alarms**: Flashing red lights? It’s like the Bat-Signal calling for your help!
  * On any equipment, indicating an impending failure or maintenance issue.
* **Leaks**: Water trying to sneak into the fortress—catch it before it causes a mess.
  * Can also come from chillers, pipes, or coolant systems.
* **Humidity and Temperature Deviations**: High humidity or temperatures in the server room may indicate cooling failures.
* **Airflow Issues**: Reduced airflow can indicate a failing CRAC unit or blocked airways.
* **Loose Cables**: Don't let your network trip over a loose cable. Tighten things up! (Cable disconnections **- l**oose or disconnected power or network cables can cause downtime.)
* **Battery Issues**: Drained UPS? That’s a power disaster waiting to happen.
  * Deteriorating UPS or generator batteries may lead to a critical power loss.
* **Electrical Anomalies**: Overloaded circuits, improper grounding, or failed fuses can be a source of concern.

***

You’ve completed your round, Detective! Keep those eyes peeled for anything suspicious, and stay ready to swoop in and save the day at Amazon’s data fortress!
