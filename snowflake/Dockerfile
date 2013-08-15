# can switch out this base with anything needed later on
FROM morehousej09/base

# initialize the java machine that we need 
RUN apt-get install -y openjdk-6-jre wget libcurl3 curl make openjdk-6-jdk maven

# now initialize all of the dependencies needed for thrift
RUN apt-get install -y libboost-dev libboost-test-dev libboost-program-options-dev libevent-dev automake libtool flex bison pkg-config g++ libssl-dev 

# download the sbt deb binary and place it in the tmp directory
RUN wget --output-document=/tmp/sbt.deb http://scalasbt.artifactoryonline.com/scalasbt/sbt-native-packages/org/scala-sbt/sbt//0.12.4/sbt.deb 
#
# Now install the debian we just downloaded
RUN dpkg --install /tmp/sbt.deb

# now lets download the thrift stable release
RUN wget --output-document=/tmp/thrift.tar.gz http://apache.mesi.com.ar/thrift/0.9.0/thrift-0.9.0.tar.gz

# now untart the file that we grabbed 
RUN cd /tmp && tar -xvzf thrift.tar.gz

# now configure, make and install thrift 
RUN cd /tmp/thrift-0.9.0 && ./configure && make && make install 

# now  we have thrift installed successfully, lets run snowflake!
# clone the snowflake repo
RUN mkdir /src
RUN git clone http://github.com/twitter/snowflake /src/snowflake

# now run some sbt commands  
RUN cd /src/snowflake && sbt update && sbt compile 

# now lets set up some entrypoint helpers etc
ENTRYPOINT ["/usr/bin/sbt"]

# now lets start the sbt helper command upon  docker run
CMD ["sbt --help"]

