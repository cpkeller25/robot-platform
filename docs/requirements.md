# robot-platform Requirements

| ID | REQUIREMENT | WHY | HOW WE'LL CHECK IT | TYPE |
|---|---|---|---|---|
| R1 | Footprint no larger than 220 x 220 mm; height under 150 mm | Fits under furniture and on a desk; one-piece chassis on a 256 mm print bed | Measure | Requirement |
| R2 | Total mass no more than 1.5 kg | Keeps the motors and battery small, and the robot easy to carry | Kitchen scale | Requirement |
| R3 | Top speed at least 0.5 m/s on a hard floor | Crosses a room in a few seconds | Time 3 m on tile | Requirement |
| R4 | Drives on low-pile carpet and climbs a 10 mm threshold | Indoor use in a real house | Drive over a doorway threshold | Requirement |
| R5 | Runs at least 90 minutes of mixed driving with the Linux computer running | A useful session between charges | Run a scripted loop until low-battery cutoff | Requirement |
| R6 | Each wheel's speed is closed-loop controlled, updated at least 100 times a second | Drives straight regardless of battery level or floor | Log commanded vs measured speed | Requirement |
| R7 | Runs a Linux image built from source with Yocto, and drives the robot from a Linux program | Learning goal: room for vision and mapping later | Boot your image; drive from a Linux program | Requirement |
| R8 | Turning the robot off never corrupts the Linux storage | A corrupted SD card is the classic Pi failure | 50 power-off cycles during activity, no corruption | Requirement |
| R9 | Can be monitored and tuned over Wi-Fi | Tune while it drives, without chasing it with a cable | Change a control gain from a laptop while driving | Requirement |
| R10 | At least 4 plug-in I2C sensor ports, 2 servo outputs and a spare GPIO header | Platform for future projects | Inspect; connect one sensor to each port | Requirement |
| R11 | Survives: a reversed battery, a shorted output, motor stall, and a flat battery, without damage | Mistakes will happen | Bench test each fault with a current-limited supply | Requirement |
| R12 | Warns before any cell drops below 3.3V and stops the motors at 3.0V | Lithium cell safety and life | Run down on a bench supply; watch the thresholds | Requirement |
| R13 | Cells are removable and charged off the robot | Simple, safe charging without a charger circuit on v1 | Inspect | Constraint |
| R14 | Every part can be hand-assembled with an iron and hot air: no BGA, passives 0603 or larger; IC lead pitch no finer than 0.5 mm; thermal pads allowed (hot air) | So we can assemble on the bench | BOM review | Constraint |
| R15 | Total spend no more than $3000, tools and printer included | budget | Spreadsheet of actual spend | Constraint |
| R16 | Indoor only; no weatherproofing | Scope | - | Constraint |
| R17 | Anyone can clone the repo and rebuild the board files, firmware and Linux image | Public project; also protects you from your own forgotten setup | Clean clone on another machine | Requirement |
| R18 | Can carry a camera and a distance sensor ring later | Future autonomy | Mechanical check in FreeCAD | Goal |
| R19 | The robot can always be switched off, even if the software has crashed | If the ESP32 firmware crashes, we need a way to shut things down | load firmware with bad code and show we can still shut it down | Requirement |
