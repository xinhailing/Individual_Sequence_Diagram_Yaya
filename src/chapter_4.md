# Chapter 4 : Sequence diagram for Calling the checkDistance Function
```plantuml
@startuml
participant lightControl
participant checkDistance

lightControl -> checkDistance : checkDistance(distance_in_function := GVL.distance)
checkDistance --> lightControl : userNearMirror (TRUE/FALSE)

lightControl -> lightControl : Update GVL.lightStatus and GVL.timerActive

@enduml


```

