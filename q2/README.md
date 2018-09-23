"# nexxera-201809-q2" 

- Download openshift for the OS version you use: https://github.com/minishift/minishift/releases
- Decompress all the files to a folder of your preference (eg.: D:\openshift or /opt/openshift/)
- Put the openshift directory in the PATH environment var
- Run the minishift start command in the command prompt (without quotes): "minishift start --vm-driver=virtualbox" (considering you're using the VirtualBox driver)
- Note for Windows User: if you're getting the "Error getting the state for host: machine does not exist" message, try to run the minishift start command in the same drive where your user profile is (usually in the C: drive)
- Run the "minishift oc-env" command in the command prompt. Copy and paste every line the output generates in the command prompt. The output might be something like that:
D:\minishift>minishift oc-env
SET PATH=C:\Users\andro\.minishift\cache\oc\v3.10.0\windows;%PATH%
REM Run this command to configure your shell:
REM     @FOR /f "tokens=*" %i IN ('minishift oc-env') DO @call %i

- Create a new project and app, running in the command prompt: "oc new-project test-nginx"
- Make sure Docker is up
- Pull the repository from https://github.com/Andropovbr/nexxera-201809.git
- Go to q2 directory and build the docker image: "docker build -t nginx_test ."
- Run the container: ""