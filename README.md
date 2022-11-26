# Resilience of Cloud Architecture

## Resience 란

####  Resiliency is Critical
It affects the quality of service your users experience

#### Resiliency is Complex

Like security, it is an end-to-end discipline that must be built in 

Cannot be bolted on later as an after thought

#### Resiliency is a key Cost driver

How many sites, how many data copies - drives cost in multiples (2x, 3x,…)

#### Resiliency in the cloud need not be the same as traditional IT

Need to meet the same business objectives of availability and recovery

There are better ways to provide continuity in the cloud – Use them!

## Reliability를 증가시키는 Design Principles

- Automaticallyrecoverfromfailure

- Testrecoveryprocedures

- Scalehorizontallytoincreaseaggregateworkloadavailability

- Stopguessingcapacity

- Manage change in automation

## Availability 

Availability(가용성)이란 워크로드(Workload)가 사용할수 있는 상태인 시간의 퍼센트입니다. 


<img src="https://user-images.githubusercontent.com/52392004/204070697-ddb1e4a1-ba6d-40fe-83d4-3a56fde8887a.png" width="300">

아래에서 Maximum unavailability는  maximum duration of outages 입니다. 

<img src="https://user-images.githubusercontent.com/52392004/204070831-ebfcf504-153d-4a86-9e50-3fe9a07b9154.png" width="800">


## Disaster Recovery (DR)

### Business continuity

- 얼마나 많은 데이터가 새로 생성되거나 일어버렸나? (How much data can you afford to recreate or lose?)

- 얼마나 빨리 복구되었나? (How quickly must you recover?)

- 다운타임 동안에 발생한 비용이 무엇인가? (What is the cost of downtime?)

### RTO와 RPO
 
- RTO (Recovery time): 최대로 받아들일수 있는 지연 시간 (the maximum acceptable delay between the interruption of service and restoration of service)

- RPO (Recovery Point Objective): 최대로 받아들일수 있는 복구 시간 (the maximum acceptable amount of time since the last data recovery point)


<img src="https://user-images.githubusercontent.com/52392004/204071167-16e3354e-c3e1-4c94-be12-67ecb0db32f3.png" width="600">



