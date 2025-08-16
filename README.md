🚀 Step-by-Step Guide:

1. Prepare the Environment
👉 You need a system (either your local machine or an EC2 instance).
Since you asked about instance — I’ll assume AWS EC2 (Ubuntu 20.04/22.04).
On EC2 instance (do these inside SSH terminal):

sudo apt update -y
sudo apt install openjdk-11-jdk -y
java -version

2. Install Maven
sudo apt install maven -y
mvn -v
✅ Now Maven is ready.

3. Install Jenkins
1.	   wget https://raw.githubusercontent.com/akshu20791/Deployment-script/main/jenkins.sh
2.	   chmod +x jenkins.sh
3.	   ./jenkins.sh

4. Access Jenkins
   In AWS console, open Security Group → add inbound rule → allow port 8080 (for Jenkins).
   Open browser:
   http://<EC2-Public-IP>:8080

5. Create HelloWorld Java Maven App
⦁	    mkdir hello-java-maven
⦁	    cd hello-java-maven
⦁	    mkdir -p src/main/java
⦁	    vi src/main/java/HelloWorld.java
⦁	    touch a pom.xml
⦁	    vi pom.xml

6. Install git
⦁	    git init
⦁	    git remote add origin https://github.com/skandakumar1992/java-maven.git
⦁	    git add .
⦁	    git commit -m "Initial HelloWorld Maven project"
⦁	    git push -u origin master

7. Configure JenkiOn Jenkins Web UI:

1.	Click New Item → Name: hello-java-maven → Select Freestyle Project → OK.
2.	In Source Code Management → Choose Git → paste your repo URL.
3.	In Build → Add build step → choose Invoke top-level Maven targets.
4.	Goals: clean install
5.	Save job.ns Job
