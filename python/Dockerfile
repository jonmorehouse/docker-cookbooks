# initialize from the base image
FROM morehousej09/base

# now lets make sure that we have python installed properly
RUN apt-get install -y virtualenv

# now create the src directory
RUN mkdir /src

# now clone the repo into the correct source
RUN git clone http://github.com/morehousej09/encoding /src/app

# now create teh correct virtual env
RUN virtualenv /src/app/

# now startup the virtualenv by sourcing the correct elements
RUN source /src/app/bin/activate.sh

# now we can run other commands as needed
ENTRYPOINT ["/src/app/bin/fab"]
CMD ["/src/app/fabfile production"]

