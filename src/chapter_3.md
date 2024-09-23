# Chapter 3 : Sequence diagram for Commincation
```plantuml
@startuml
participant User
participant MirrorSystem
participant Light
participant Timer

User -> MirrorSystem: Walk towards mirror
MirrorSystem -> Light: Detect user within 1 meter, turn light ON
activate Light
Light -> User: Light is ON
MirrorSystem -> Timer: Start 15-minute timer
activate Timer

User -> MirrorSystem: User stays near mirror
Timer -> Timer: Count down (15 minutes)

User -> MirrorSystem: User moves away (before 15 minutes)
MirrorSystem -> Light: Turn light OFF
deactivate Light
MirrorSystem -> Timer: Stop timer
deactivate Timer
MirrorSystem -> User: Light is OFF, user far

alt User stays near mirror for 15 minutes
    Timer -> MirrorSystem: Timer expires (15 minutes)
    MirrorSystem -> Light: Turn light OFF
    deactivate Light
end

@enduml

```
[Actor list:
1. User: The person approaching and interacting with the mirror.
2. MirrorSystem: The control system that detects the user’s presence and controls the light and timer.
3. Light: The system that turns on and off based on the user’s proximity.
4. Timer: Tracks the 15-minute interval after the light is turned on]