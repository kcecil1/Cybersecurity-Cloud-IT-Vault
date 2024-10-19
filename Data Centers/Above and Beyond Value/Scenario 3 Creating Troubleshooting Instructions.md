
---

### **Situation:**
While troubleshooting a lift at one of my previous jobs, the lift was unresponsive despite all safety conditions being fulfilled. This lift was critical for operations, and identifying the root cause quickly was necessary to avoid extended downtime. The system included a 480V motor and pneumatic components, and the issue could have been in either the electrical or pneumatic systems.

### **Task:**
I was tasked with diagnosing the issue and restoring full functionality to the lift. The goal was to ensure the system operated correctly without further disruptions, and I saw an opportunity to improve future troubleshooting efforts by documenting the process.

### **Action:**
I started by methodically checking the PLC for any errors, confirming that the logic was sound and all safety interlocks were engaged. Next, I traced the wiring back to the 480V panel and saw there was no 480V power. After reviewing the electrical drawings, I worked with an electrician to check the power distribution panel. We found that the main power fuse to the lift was the wrong amperage due to a revision in the bulletin, and we replaced it.

However, even after restoring power, the lift still didn’t function. I noticed that the pneumatic system wasn’t supplying air pressure to the regulator, even though it was set to 6 bar. Upon further inspection, I found a screw on top of the dump valve that needed adjustment. Once I adjusted it, the LCD showed the correct pressure, but the lift remained unresponsive.

I continued troubleshooting by reviewing the lift's control panel drawings from the OEM and discovered redlined wiring. The solenoid that controls the lowering of the lift was wired backwards(which lowers by relieving hydraulic pressure), and the 480V motor that controls the raising of the lift was attempting to run in reverse due to incorrect wiring (it can not run in reverse because of the hydraulic pressure not being relieved by the solenoid - it's only for raising the lift). I swapped the wires for both the solenoid and the motor leads (L1 and L2), which resolved the issue. The lift could now raise and lower correctly. 

Going above and beyond, I created detailed work instructions for troubleshooting these lifts in the future, ensuring that others could resolve similar issues more efficiently.

### **Result:**
By methodically diagnosing the problem and correcting both the pneumatic and electrical issues, I was able to restore full functionality to the lift. The downtime was minimized, and the company avoided further disruptions to operations. Additionally, the work instructions I created have become a valuable resource for future troubleshooting, improving overall efficiency and reducing downtime across other lifts. My proactive approach not only solved the immediate issue but also ensured that the team would be better equipped to handle similar problems in the future.

---
