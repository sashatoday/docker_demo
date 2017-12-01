FROM ubuntu:latest

LABEL maintainer "Aleksandra Zhuravleva <guravleva.aleksandra@gmail.com>"

# Install java-8 and maven
RUN apt-get update -y
RUN apt-get install -y maven openjdk-8-jdk openjdk-8-jre git

# Clone projects
RUN git clone https://github.com/sashatoday/hibernate-db-analyzer.git
RUN git clone https://github.com/sashatoday/SpringDBAnalyzer.git

# Build projects
RUN cd ./hibernate-db-analyzer/ && mvn package
RUN cd ./../SpringDBAnalyzer/ && mvn package

# Copy application startup script
COPY run_rest_service.sh /

# Listen on 8080 port at runtime (contact the host)
EXPOSE 8080

# Launch the application
CMD ["/bin/bash", "run_rest_service.sh"]
