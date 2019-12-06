FROM tomcat

RUN mkdir -p /maven && cd /maven && wget http://mirrors.tuna.tsinghua.edu.cn/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip && unzip apache-maven-3.6.3-bin.zip && mkdir -p /app
COPY ci_war_demo.zip /app/
RUN cd /app &&  unzip ci_war_demo.zip && PATH=$PATH:/maven/apache-maven-3.6.3/bin && cd /app/ci_war_demo && mvn clean compile && mvn clean package  && mv /app/ci_war_demo/target/HelloSpringMVC.war /usr/local/tomcat/webapps && bash /usr/local/tomcat/bin/startup.sh


