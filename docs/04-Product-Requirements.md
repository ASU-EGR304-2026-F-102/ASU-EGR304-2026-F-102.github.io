# Product Requirements

## Objectives

Project Aurora is to design and develop a smart medication storage device that will help the user safely manage their daily medications. The target is to create a reliable, easy-to-use medication storage system that will assist in maintaining medication routines while providing feedback on storage conditions.

The system will monitor medication removal and container access, provide visual, audible, and electronic reminders for scheduled doses, and monitor environmental conditions. The system will detect when medication is removed using a weight sensor, monitor bottle access using a cap sensor, use an LED and audible alert system to provide medication reminders, and use temperature and light sensors to monitor the storage environment.

Project Aurora will improve medication awareness by tracking interactions with the medication container and identifying when medication should be taken and when it is removed from the container.

---

## Stakeholders

**Target User:** Adults, often older, who take several scheduled medications a day and sometimes forget or double up. They value independence: they want the dispenser to remind them and to hand them exactly the right dose, without having to manage a complicated device.

**Target Purchaser:** An adult child or family caregiver, roughly in their 30s–60s, buying and setting up the device for an aging or memory-impaired parent. They are not usually the one taking the medication, so they care most about easy setup, quick schedule changes, and a reliable record of what was taken, not day-to-day use.

**Customer Service:** The team or person fielding setup and troubleshooting calls after purchase, likely the caregiver calling in on behalf of the patient. They need clear error states such as a jam, missed dose, or lid fault that a user can describe over the phone, and a device that is simple enough that most issues can be solved without a technician visit.

**Marketing & Sales Division:** Looks for unique selling points around independence, safety, and peace of mind for caregivers and family members.

**Retailers:** Prefer compact, shelf-stable packaging that withstands handling and storage, with tamper-evident and theft-resistant design.

---

## Use Cases

### User Story #1: Ruth and Elena - Daily Use With a Caregiver

Ruth is a 78-year-old who lives alone and takes pills at 8:00, 12:00, 18:00, and 21:00. She sometimes forgets whether she has already taken one. Her daughter Elena visits on Sundays. She fills the 28 compartments for the week, sets the schedule with the buttons, and closes the lid, which locks automatically.

At 8:00 on Monday, the carousel turns one compartment to the dispensing cup and the alarm starts, with a flashing light for when Ruth is not in earshot. The alarm is set to a mid volume that Ruth can hear from the kitchen. She picks up the pills, and within two seconds the optical sensor sees the cup is empty and the alarm stops. The log records the time.

On Wednesday she is out at her neighbor's at noon and misses the dose window. After 30 minutes the dispenser locks the cup, logs the dose as missed, and does not present the next compartment early.

### User Story #2: Marcus and His Father - Setup, Schedule Change, and Safety

Marcus is 34 and sets up a dispenser for his father, who is hard of hearing and has been prescribed a new schedule. Marcus opens the box and finishes setting the clock and four daily doses in under five minutes using the two-page quick-start guide, without calling anyone.

A week later the doctor changes the dose times, and Marcus updates them in about a minute. His father, curious at 3:00 in the afternoon, tries to get the next dose early. The lid is locked and the cup is empty. His grandson tries to pry the lid with a screwdriver, and it holds.

Later, an oversized capsule lodges in the carousel. The motor current rises, the firmware detects the stall, backs off, and retries. If it cannot clear the jam, the unit shows an error and logs the event instead of silently failing, and no other compartment is presented.

---

# Design Aspects

## 1. Product Design

The hardware should make medication easy to store, refill, and collect while keeping medication secure.

Our benchmarking showed problems with pills getting stuck, difficult-to-open compartments, weak locks, and users having trouble reaching medication.

Project Aurora should:

- Keep medication doses separated.
- Keep medication that is not currently available secured.
- Make dispensed medication easy to remove.
- Reduce areas where pills could become stuck.
- Make the medication tray easy to remove and refill.
- Use simple buttons and openings that are easy to operate.

The final outside appearance of the product may be completed by an external designer, but the engineering team will define the important dimensions and functions that the enclosure must support.

---

## 2. Software / Functionality

The software should make sure medication is available at the correct time and should prevent simple medication errors.

Our benchmarking showed problems with incorrect time information, limited scheduling options, connection problems, and incorrect medication records.

Project Aurora should:

- Keep the correct date and time.
- Allow several medication times to be programmed during the day.
- Activate the correct medication event at the programmed time.
- Prevent the same scheduled dose from being accidentally dispensed twice.
- Keep the medication schedule stored if power is temporarily removed.
- Clearly show when an error occurs.

The main medication functions should work directly from the device instead of depending completely on an internet connection.

---

## 3. Interactivity & User Experience

The benchmarking showed that some medication dispensers were difficult to set up or confusing to operate, especially for older users.

Project Aurora should therefore have a simple interface.

The device should:

- Use large and simple controls.
- Clearly show when medication is ready.
- Use both sound and light for medication reminders.
- Show the current time and medication status clearly.
- Require only a small number of actions to receive medication.
- Give simple error messages when something goes wrong.

The goal is for a user to understand the basic operation of the device without needing to search through several menus.

---

## 4. Customization

Different users can have different medication schedules, so some basic customization is necessary.

Project Aurora should allow the user or caregiver to:

- Change medication times.
- Program multiple medication times during one day.
- Change reminder volume.
- Turn optional reminder sounds on or off.

More advanced customization can be considered later, but the prototype will focus on the settings that directly affect normal medication use.

---

## 5. Manufacturing

The benchmarking showed that some products had poor build quality or stopped working after limited use.

Project Aurora should therefore be designed so that it can be assembled and tested consistently.

The design should:

- Use secure electrical connections.
- Use durable buttons, covers, and moving parts.
- Make the medication tray difficult to install incorrectly.
- Allow important parts to be accessed for maintenance.
- Allow medication-contact areas to be cleaned.
- Include a basic functional test after assembly.

The goal is not to create a full commercial manufacturing process during this project. The goal is to make sure the prototype is built in a repeatable and reliable way.

---

## 6. Safety

Safety is important because a failure could cause a user to miss medication or receive medication at the wrong time.

Project Aurora should:

- Prevent access to medication that is not currently available.
- Prevent accidental repeated dispensing of the same scheduled dose.
- Prevent dispensing when an important part such as the medication tray is missing.
- Stop the dispensing process and warn the user if a dispensing error is detected.
- Avoid exposed electrical connections.
- Avoid exposed moving parts that could pinch the user's fingers.

These requirements focus on the safety problems that can realistically be addressed and tested with the Project Aurora prototype.

---

# Requirement Criteria Specifications

The design aspects above describe the main goals of Project Aurora. The following criteria turn those goals into requirements that can be checked using inspection, testing, or demonstration.

Each requirement is given a priority:

- **Must:** Required for the prototype to meet its main purpose.
- **Should:** Important to the design, but the prototype can still meet its main purpose if the requirement cannot be fully completed.

## Product Design Requirements

| ID | Priority | Requirement Criteria Specification | Verification |
| --- | --- | --- | --- |
| PD1 | Must | The device shall keep different scheduled medication doses physically separated and prevent normal access to medication that is not currently available. | Inspection / Demonstration |
| PD2 | Must | After dispensing, the complete intended dose shall be accessible without the user reaching into the internal dispensing mechanism. | Demonstration |
| PD3 | Should | The medication tray shall be removable, refillable, and reinstallable by hand without requiring special tools. | Demonstration |
| PD4 | Should | The dispensing mechanism shall complete **20 consecutive dispensing cycles without a pill or test object becoming stuck**. | Test |

## Software / Functionality Requirements

| ID | Priority | Requirement Criteria Specification | Verification |
| --- | --- | --- | --- |
| SW1 | Must | The device shall maintain the correct date and time and activate a scheduled medication event within **±1 minute** of the programmed time. | Test |
| SW2 | Must | The system shall support at least **4 independently programmed medication times per day**. | Demonstration |
| SW3 | Must | The system shall prevent the same scheduled dose from being dispensed more than once during normal operation. | Test |
| SW4 | Must | Programmed medication times shall remain stored after the device is powered off and restarted. | Test |
| SW5 | Must | The weight sensor shall detect when medication is removed and allow the system to record the medication interaction. | Test / Demonstration |
| SW6 | Must | The cap sensor shall detect when the medication container is opened or closed. | Test / Demonstration |
| SW7 | Should | The device shall read temperature and light conditions and provide an indication when the measured storage condition is outside the programmed acceptable range. | Test / Demonstration |
| SW8 | Should | Basic scheduled reminders and local medication functions shall continue to operate without an internet connection. | Test |

## Interactivity & User Experience Requirements

| ID | Priority | Requirement Criteria Specification | Verification |
| --- | --- | --- | --- |
| UX1 | Must | The main interface shall clearly display the current time and whether medication is currently ready. | Inspection / Demonstration |
| UX2 | Must | The device shall provide both an audible and visual reminder when a scheduled medication becomes available. | Demonstration |
| UX3 | Should | A normal scheduled dose shall require no more than **2 user actions** to begin dispensing after the reminder starts. | Demonstration |
| UX4 | Must | When a detectable error occurs, the interface shall clearly indicate that an error has occurred. | Test / Demonstration |

## Customization Requirements

| ID | Priority | Requirement Criteria Specification | Verification |
| --- | --- | --- | --- |
| C1 | Must | The user shall be able to change an individual medication time without resetting the other programmed medication times. | Demonstration |
| C2 | Must | The system shall allow multiple medication times to be programmed within the same day. | Demonstration |
| C3 | Should | The user shall be able to adjust the reminder volume and turn optional reminder sounds on or off. | Demonstration |

## Manufacturing Requirements

| ID | Priority | Requirement Criteria Specification | Verification |
| --- | --- | --- | --- |
| M1 | Must | Electrical connections shall remain securely connected during normal operation, refilling, and opening or closing of the device. | Inspection / Test |
| M2 | Should | The medication tray shall either fit only in the correct orientation or clearly show the correct installation orientation. | Inspection / Demonstration |
| M3 | Should | Medication-contact areas and parts requiring normal maintenance shall be accessible without completely disassembling the device. | Inspection / Demonstration |
| M4 | Must | The completed prototype shall pass a functional check of the controls, sensors, reminder system, dispensing mechanism, and power system before the final demonstration. | Test |

## Safety Requirements

| ID | Priority | Requirement Criteria Specification | Verification |
| --- | --- | --- | --- |
| SF1 | Must | The device shall prevent normal access to medication that is not currently available. | Demonstration |
| SF2 | Must | The system shall prevent accidental repeated dispensing of the same scheduled dose. | Test |
| SF3 | Must | The device shall not begin a dispensing cycle when the required medication tray or dispensing component is missing. | Test |
| SF4 | Must | If a dispensing error is detected, the dispensing process shall stop and the user shall receive an error indication. | Test / Demonstration |
| SF5 | Must | Normal user operation shall not expose the user to powered electrical connections or reachable moving parts that could pinch the user's fingers. | Inspection |

### Verification Methods

**Inspection:** The requirement can be verified by looking at the completed prototype or its design.

**Test:** The prototype is operated under a controlled condition and the result is measured or recorded.

**Demonstration:** The required function is shown through normal operation of the prototype.

---

# Open Questions

- How can we create a high-quality, durable device while keeping the cost affordable?
- How can the design be adjusted to add or remove medication from the device?
- How can we make the device easy to refill, clean, and maintain for long-term use?
- What range of pill sizes and shapes can the dispensing mechanism reliably handle without causing jams?
- What temperature and light conditions should be considered unsafe for medication storage, and when should the device warn the user?
- What should the device do if power is lost or one of the important sensors stops working?