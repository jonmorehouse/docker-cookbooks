# initialize our personal base image
FROM morehousej09/base

# initialize some standard tools that we need 
RUN apt-get install -y openjdk-6-jre wget libcurl3 curl make openjdk-6-jdk maven

# now lets make sure that we have thrift installed
RUN apt-get install -y libboost-dev libboost-test-dev libboost-program-options-dev libevent-dev automake libtool flex bison pkg-config g++ libssl-dev 

# initialize some python specific tools and ensure that they are all installed,
RUN apt-get install -y python-pip python-dev build-essential

# Now go ahead and clone the tool
RUN git clone http://github.com/erans/pysnowflake /src/pysnowflake


