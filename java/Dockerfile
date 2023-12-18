# A image with JRE 17 based to Alpine
FROM eclipse-temurin:17-alpine

# Adding a new group 'devopsc', new 'admin' and assinging the 'devopsc' group
RUN addgroup -g 1028 devopsc \ 
    && adduser -D -G devopsc admin

# Create a new mount point at /tmp (this is because is more efficient and faster than filesystem)
VOLUME /tmp

# Add some arguments
ARG JAR_FILE
ARG DB_PASSWORD

# Set arg into env variables
ENV DB_PASSWORD=$DB_PASSWORD

# Copy JAR file
COPY ${JAR_FILE} /tmp/app.jar

# Change ownership of the /app directory to the "user" user
RUN chown -R admin:devopsc /tmp

# Changing to the 'admin' user
USER admin

# Run the container
ENTRYPOINT ["java", "-jar", "/tmp/app.jar"]