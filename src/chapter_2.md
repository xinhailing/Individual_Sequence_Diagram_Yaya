# Chapter 2 : State Diagram for Task 2 : TimerControl
```plantuml
@startuml
state "Timer Running" as TimerRunning
state "Timer Countdown" as TimerCountdown
state "Light Off" as LightOff

TimerRunning --> TimerCountdown : GVL.timerActive := FALSE
TimerCountdown --> LightOff : timer.Q = FALSE

@enduml
```
