FROM debian:stable-slim

# Set environmental variables

ENV DEBIAN_FRONTEND noninteractive

# Installing dependencies

RUN apt-get update && apt-get -y install nedit

VOLUME ["/source"]

WORKDIR /source

CMD ["nedit"]
