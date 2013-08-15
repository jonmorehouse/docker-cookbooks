# can switch out this base with anything needed later on
FROM morehousej09/base

# initialize the java machine that we need 
RUN apt-get install -y openjdk-6-jre wget libcurl3 curl

# now initialize all of the dependencies needed for thrift
RUN apt-get install -y libboost-dev libboost-test-dev libboost-program-options-dev libevent-dev automake libtool flex bison pkg-config g++ libssl-dev 

# download the sbt deb binary 
RUN wget http://scalasbt.artifactoryonline.com/scalasbt/sbt-native-packages/org/scala-sbt/sbt//0.12.4/sbt.deb 

# move the download to the proper element
RUN mv sbt.deb /tmp

# Now install the debian we just downloaded
#RUN dpkg --install sbt.deb

# now install a bunch of dependencies needed for 


