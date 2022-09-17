# microservices-using-springboot
Basic Microservice Example(User service, Department service, Service Registry, Api Gateway, Hystrix(Circuit breaker) Dashboard, Cloud Config Server, GitHub Repo for Config Server, and Zipkin Sleuth)
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
3 Configure Service Registry Eureka Server
<br>
![image](https://user-images.githubusercontent.com/36573782/190856186-12d5f001-a5fb-418b-ba9d-518f5f21c405.png)
<br>
4 Cloud Gateway
<br>
![image](https://user-images.githubusercontent.com/36573782/190856238-2dfcc051-ba1c-4c24-9d58-5ef10f32f2ac.png)
<br>
After configuring the Cloud Gateway, Now we use 9191 port for all servers
<br>
Departments
<br>
![image](https://user-images.githubusercontent.com/36573782/190857074-24201bc8-d847-4812-8ba2-8847c8da0c6b.png)
<br>
![image](https://user-images.githubusercontent.com/36573782/190857094-4a6f1f56-d423-4752-b255-a8a59eaf9c9f.png)
<br>
Users
<br>
![image](https://user-images.githubusercontent.com/36573782/190857855-46f5929f-d525-40a2-aa26-ce01d41623ea.png)
<br>
![image](https://user-images.githubusercontent.com/36573782/190857878-cb280a9b-afdb-4b11-96b0-cd861108691f.png)
<br>
5 Cirsuit Braker(Hystrix Library and Hystrix Dashboard) - so we identify which one service is running and which is not running in dashboard.
<br>
Just start the actuator/hystrix.stream
<br>
![image](https://user-images.githubusercontent.com/36573782/190869291-cdd1cf1c-ab7f-47b8-bac6-8200277fc35a.png)
<br>
We enter the actuator/hystrix.stream port of gateway into the hystrix dashboard
<br>
![image](https://user-images.githubusercontent.com/36573782/190869324-e7a7ad37-4287-45b6-b1a0-bfb47f21598d.png)
<br>
Now we use the user and department services to check the hystrix dashboard. I just stop the department service
<br>
![image](https://user-images.githubusercontent.com/36573782/190869471-6c9d59d2-60e3-48a9-97af-4f2234dbafa4.png)
<br>
![image](https://user-images.githubusercontent.com/36573782/190874531-4f322cbb-e897-4543-bdf1-d03d2b060760.png)
<br>
6 Cloud Config Server, we added Githu Repo for config server. We just create new bootstrap.yml and added all the repeated configuration in one file in github repo
<br>
![image](https://user-images.githubusercontent.com/36573782/190874351-2d8fec32-07d9-4b47-be04-496defe8fdcc.png)
<br>
Cloud config server
<br>
![image](https://user-images.githubusercontent.com/36573782/190874384-21c84bed-e5ad-4ccd-95f6-a1a7424bc394.png)
<br>
Instance currently running with Eureka
<br>
![image](https://user-images.githubusercontent.com/36573782/190874419-0ecd3182-0e69-43b4-9b87-6c3433ea3a10.png)
<br>
7 Zipkin all the distributed logging, now we use zipkin to identify which services called what is the trace id and trace id will be unique across the all microservices and that particular one request, and span id each and every microservices change. We can get where is the failer and where is the success.
<br>
We download the zipkin new release and use the cmd to run the zipkin(java -jar zipkin_file_name.jar)
<br>
![image](https://user-images.githubusercontent.com/36573782/190874939-c559240f-ae0a-46f0-b939-0d898ae81a9d.png)
<br>
![image](https://user-images.githubusercontent.com/36573782/190875063-aeb8f161-81a3-46d1-88ac-8250e7750d4f.png)
<br>



