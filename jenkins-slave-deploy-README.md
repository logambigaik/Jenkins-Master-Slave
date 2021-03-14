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
    
    >> Copy the public key of master into slave authorised-key

![image](https://user-images.githubusercontent.com/54719289/111083649-7853fc00-8506-11eb-804e-7597b3643f9d.png)
![image](https://user-images.githubusercontent.com/54719289/111083640-6c683a00-8506-11eb-9e9d-f59b739bf88b.png)

    >> Check the connectivity using ssh root@ipadd-of slave in jenkins
