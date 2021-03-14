# Install in slave machine not in Master
    git
    maven
    docker
    start the docker service
    
# Create the credential for docker hub in jenkins(username password)

![image](https://user-images.githubusercontent.com/54719289/108412825-48d80980-7250-11eb-8ac7-c699b199d6cd.png)


![image](https://user-images.githubusercontent.com/54719289/108413535-272b5200-7251-11eb-9ec7-6ffb426c28e2.png)


![image](https://user-images.githubusercontent.com/54719289/108413797-740f2880-7251-11eb-87f4-97884676c306.png)


# With Mange Node in Jenkins:

    >> Create ew node under Manage Nodes

![image](https://user-images.githubusercontent.com/54719289/111083461-a7b63900-8505-11eb-8937-804523bbcf6c.png)

    >> in Master Linux machine create SSH-key under the user - jenkins
    
        su -s /bin/bash jenkins

![image](https://user-images.githubusercontent.com/54719289/111083555-15fafb80-8506-11eb-9be8-b57c5bb6f9ea.png)
![image](https://user-images.githubusercontent.com/54719289/111084662-7a6c8980-850b-11eb-84a2-133308ca3ea0.png)
![image](https://user-images.githubusercontent.com/54719289/111084726-b7d11700-850b-11eb-99c6-515143da4ac6.png)
![image](https://user-images.githubusercontent.com/54719289/111084758-ed760000-850b-11eb-832d-594e34454f0d.png)

    
    >> Copy the public key of master into slave authorised-key

![image](https://user-images.githubusercontent.com/54719289/111083649-7853fc00-8506-11eb-804e-7597b3643f9d.png)
![image](https://user-images.githubusercontent.com/54719289/111083640-6c683a00-8506-11eb-9e9d-f59b739bf88b.png)

    >> Check the connectivity using ssh root@ipadd-of slave in jenkins

![image](https://user-images.githubusercontent.com/54719289/111083994-58253c80-8508-11eb-9f25-28d7b2a45605.png)
 



# Running test1 -sample pipeline in slave:

![image](https://user-images.githubusercontent.com/54719289/111085066-8d805900-850d-11eb-891b-720314185e3c.png)


   Sample pipeline:
   ==============
   
   
            def str1 = "Hello World"
println str1

def arrStr = ['Groovy','Java','Python','NodeJS']
println arrStr
b = arrStr.size()
println b

for ( x in 1..b){
    println(arrStr[x])
}

String str2 = new String("Hello World")

if(str1 == str2)
{
  println('equal')
}
else
{
  println('Not equal')
}

def list1 = []
list1 = [1, 2, 3, 4];
println ("After define list:"+ list1)

list1.add(5) //add
println ("After add list:"+ list1)

list1.pop()  //pop
println ("After pop list:"+ list1)

    pipeline{
        agent { node('slave') }
        stages {
            stage ('print'){
                steps{
                    sh 'echo "Hello-World with sh in pipeline" '
                }
            }
        }
    }
