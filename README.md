# microservices-using-springboot
Basic Microservice Example(User service, Department service, Service Registry, Api Gateway, Hystrix Circuit Dashboard, Cloud Config Server, GitHub Repo for Config Server, and Zipkin Sleuth)
<br>
1 Create Department service
<br>
![image](https://user-images.githubusercontent.com/36573782/190845460-660e0274-912e-48d0-a95d-ab6abff7d853.png)
<br>
![image](https://user-images.githubusercontent.com/36573782/190845496-2961c5ca-76a5-4b85-a9cc-2a38d9bff696.png)
<br>
2 Create User Service
<br>
![image](https://user-images.githubusercontent.com/36573782/190845447-ab602478-f605-4de4-b081-fa0672b5d56d.png)
<br>
here we call User service with department, this both are decouple with each other through RestTemplate. But we have only 2 microservice here, if we have 100 or 1000 of microservices this will be defficult to maintain so we user the service registry and that service registry will maintain all the microservices, so we will get all the information(status, port etc)
<br>
![image](https://user-images.githubusercontent.com/36573782/190845532-c9bce869-82d2-40c7-99cd-279e58b9fe52.png)
<br>
