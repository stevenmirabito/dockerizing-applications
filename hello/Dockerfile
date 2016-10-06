FROM centos:7
MAINTAINER Steven Mirabito (smirabito@csh.rit.edu)

# Install Flask
RUN yum -y install python-flask && yum -y clean all

# Create app user and directory
RUN useradd -r -d /opt/hello -s /sbin/nologin hello && \
mkdir -p /opt/hello && \
chown -R hello:hello /opt/hello && \
chmod -R og+rwx /opt/hello

# Copy the application into the container
COPY hello.py /opt/hello/

# Drop privileges
USER hello

# Set the working directory to the app root
WORKDIR /opt/hello

# Expose the app port
EXPOSE 8080

# Set the entrypoint for the application
CMD /usr/bin/python hello.py
