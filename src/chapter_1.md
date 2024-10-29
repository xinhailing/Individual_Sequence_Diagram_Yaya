# Chapter 1 : State Diagram for Task 1 : LightControl
```plantuml
@startuml
[*] --> Light_Off

state Light_Off {
    [*] --> Checking_Distance
    Checking_Distance --> Light_On : User is within 1 meter
}

state Light_On {
    [*] --> Checking_Distance
    Checking_Distance --> Light_On : User remains within 1 meter
    Checking_Distance --> Timer_Start : User moves away (distance > 1 meter)
}

Light_On --> Light_Off : Timer elapsed
Timer_Start --> Light_On : User returns within 1 meter
@enduml

```
Sequence of Events://
1.User Moves Towards Mirror//
2.Timer Check//
3.User Moves Away from Mirror//
4.Turning Off the Light (After 5 seconds)//