# dockeriseModel
This is a sample trial of how a ML model can be dockerized

Files required:
1.	Program.py- which accepts training, test data. It will train a model, outputs results of test data. Test data is accepted from system argument, taken from DockerFile- which is mapped to local machine.
2.	Requirement.txt- all necessary python libraries, any other packages, necessary for this container is mentioned here.
3.	TrainingData.csv, testData.csv- all data
4.	DockerFile- gets the container ready, runs the program test file. This test file is internally mapped to local machine’s address using parameter –v. 
Instead of copying the test file, we did a mapping. This will help in reducing the time of copying large test files, if in case, it happens to be large.
Steps for creating image and running a container:

1.	docker build -t linearregmodel .

2.	docker run –v C:/Users/swaravi/Documents/Lab/dockeriseModel/data:/data/ linearregmodel

Note: 
1.	Volume mapping helps to use the address of local machine to the address of docker. This helps to save output to a location of docker. This would be translated to local machine where the docker is deployed.
2.	Make sure to change the \ to / from address of windows machine.
