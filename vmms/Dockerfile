FROM ubuntu:16.04

RUN apt-get update --fix-missing
RUN apt-get install -y gcc
RUN apt-get install -y make
RUN apt-get install -y build-essential
RUN apt-get install -y default-jre

# Install autodriver
WORKDIR /home
RUN useradd autolab
RUN useradd autograde
RUN mkdir autolab autograde output
RUN chown autolab:autolab autolab
RUN chown autolab:autolab output
RUN chown autograde:autograde autograde
RUN apt-get install -y git
RUN git clone https://github.com/ChillingHsu/Tango.git
WORKDIR Tango/autodriver
RUN make clean && make
RUN cp autodriver /usr/bin/autodriver
RUN chmod +s /usr/bin/autodriver

# Clean up
WORKDIR /home
RUN apt-get remove -y git
RUN apt-get -y autoremove
RUN rm -rf Tango/

# Check installation
RUN ls -l /home
RUN which autodriver
