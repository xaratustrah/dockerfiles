FROM debian:stable-slim

# Set environmental variables

ENV DEBIAN_FRONTEND noninteractive

# Installing dependencies

RUN apt-get update && apt-get -y install planner

VOLUME ["/hostpwd"]

WORKDIR /source

CMD ["planner"]
