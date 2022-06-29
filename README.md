# Volume testing using Jmeter by establishing JDBC connection
Here user information is read from a specific database and users are inserted.Volume 
testing is performed by increasing threads and rampup in Jmeter.
Steps taken to build this project:
- JDBC connection is configured by connecting a specific Database where there is pre-existing datas.
- JDBC driver class (com.mysql.jdbc.Driver) is configured.
- mysql-connector-java is put in the lib folder of apache-jmeter.

- Database is tested by **100 users** concurrently reading info in **60s**.
![100 users reading info in 60 s](https://user-images.githubusercontent.com/55280106/176427830-8d8c3407-6203-4439-bb77-84dac1041b97.png)
There is fail rate of **0%**.
- The users are increased more and local database is tested for **300 users** reading info in **60s**.
![300 users reading info in 60 s with fail rate of 49 67%](https://user-images.githubusercontent.com/55280106/176428007-568e4f03-583b-4cec-8bf7-d32e780e23c8.png)
There is an error rate of **49.67%**.
- Insertion operation is run from jmeter into the local database and it is tested for **100 users** in **60s**.
![inserting info into database for 100 users in 60s](https://user-images.githubusercontent.com/55280106/176428163-a7908d67-9569-4b97-80f0-5c04764d0588.png)
There is an error rate of **0%**.
- Reading and writing both operation is tested concurrently in the local database for **167 users** for **60 s**.
![Reading and writing users of 167 users in 60s with a fail rate of 9 58%](https://user-images.githubusercontent.com/55280106/176428546-f21180ee-4670-40e7-8510-d8413115e0ef.png)
There is a fail rate of **9.58%**.
- The test is repeated for **167 users for 65s**.
![Reading and writing users of 167 users in 65 s with a fail rate of 2 4%](https://user-images.githubusercontent.com/55280106/176428720-98e0a22b-2584-4eb9-a231-992aa3014364.png)
There is an error rate of **2.40%**.
- The test is again performed by keeping the same amount of users for **68s**.
![Reading and writing users of 167 users in 68 s with a fail rate of 0% and it is lower bottleneck](https://user-images.githubusercontent.com/55280106/176428994-957936b4-819b-4fd2-a05a-d79305a92538.png)
After increasing time and keeping same amount of users , the error rate is **0%** for 68s and can be
regarded as the **lower bottleneck** of the test.
- You can clone this project and test it by your own local database Url.
