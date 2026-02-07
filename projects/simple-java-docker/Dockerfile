# pull a base image which gives all required tools and libraries
FROM openjdk:27-ea-oraclelinux9

# create a folder where the app code will be stored
WORKDIR /app

# Copy source code from your HOST machine to your container
COPY src/Main.java /app/Main.java

# Compile the Java code
RUN javac Main.java

# Run the Java application when the container starts
CMD ["java", "Main"]