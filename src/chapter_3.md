# Chapter 3 : Sequence diagram for Commincation Between Task 1 and 2
```plantuml
@startuml
actor User
participant LightControl
participant TimerControl
participant GVL

User -> LightControl: Moves towards mirror
LightControl -> GVL: Set lightStatus = TRUE
GVL -> TimerControl: Read lightStatus
TimerControl -> TimerControl: Timer is not active

User -> LightControl: Moves away from mirror
LightControl -> GVL: Set lightStatus = TRUE
GVL -> TimerControl: Start 5s timer
TimerControl -> TimerControl: Timer runs for 5 seconds

TimerControl -> LightControl: Light off after 5s
LightControl -> GVL: Set lightStatus = FALSE
@enduml



```