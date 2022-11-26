# Resilience of Cloud Architecture

## Resience 개요 

서비스의 품질은 사용자의 경험에 중요하므로 Resilience는 중요하고 end-to-end 동작이므로 복잡합니다. Resilience를 높이기 위해서는 서버의 숫자를 늘리거나, 더 많이 데이터를 복재해야 하므로 비용이 중요한 요소입니다. 



## Availability 

Availability(가용성)이란 워크로드(Workload)가 사용할수 있는 상태인 시간의 퍼센트입니다. 


<img src="https://user-images.githubusercontent.com/52392004/204070697-ddb1e4a1-ba6d-40fe-83d4-3a56fde8887a.png" width="300">

아래에서 Maximum unavailability는  maximum duration of outages 입니다. 

<img src="https://user-images.githubusercontent.com/52392004/204070831-ebfcf504-153d-4a86-9e50-3fe9a07b9154.png" width="800">

## Design Patterns 

### Reliability를 증가시키는 Design Principles


- Automaticallyrecoverfromfailure

- Testrecoveryprocedures

- Scalehorizontallytoincreaseaggregateworkloadavailability

- Stopguessingcapacity

- Manage change in automation

### Loosly Coupled Architecture 

- Tight coupling (Synchronous)

EC2 인스턴스의 실패가 client에 직접적인 영향을 줍니다. 

![image](https://user-images.githubusercontent.com/52392004/204071583-51c955dc-7bd7-49ef-8dcb-3e4b6dfe246c.png)

- Loose coupling (Synchronous)

ELB는 Health check를 통해서 Healthy EC2로 트래픽을 전송하므로, EC2가 실패할때 일시적인 실패가 발생합니다. 

![image](https://user-images.githubusercontent.com/52392004/204071680-60bb2b43-1a66-47aa-a68b-cc4aac50b26d.png)

- Loose coupling (Asychronous)

Client의 Request는 SQS와 같은 Queue에 저장되고, EC2중 한개가 문제가 발생하더라도 해당 Request는 남아서 다른 EC2에서 실행(process)될 수 있습니다. 

![image](https://user-images.githubusercontent.com/52392004/204071686-e52b7ed0-6788-4dd0-bbff-9d984d0f1aa6.png)




## Disaster Recovery (DR)

### Business continuity

- 얼마나 많은 데이터가 새로 생성되거나 일어버렸나? (How much data can you afford to recreate or lose?)

- 얼마나 빨리 복구되었나? (How quickly must you recover?)

- 다운타임 동안에 발생한 비용이 무엇인가? (What is the cost of downtime?)

### RTO와 RPO
 
- RTO (Recovery time): 최대로 받아들일수 있는 지연 시간 (the maximum acceptable delay between the interruption of service and restoration of service)

- RPO (Recovery Point Objective): 최대로 받아들일수 있는 복구 시간 (the maximum acceptable amount of time since the last data recovery point)


<img src="https://user-images.githubusercontent.com/52392004/204071167-16e3354e-c3e1-4c94-be12-67ecb0db32f3.png" width="600">


## Reference

[Reliability Pillar - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)
