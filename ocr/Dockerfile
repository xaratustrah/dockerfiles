FROM debian:buster-slim

# Set environmental variables

ENV LC_ALL="C.UTF-8"
ENV LANG="C.UTF-8"

#RUN apk add bash

RUN apt-get update && apt-get install -q -y --no-install-recommends tesseract-ocr-eng tesseract-ocr-deu ocrmypdf

# run bash
CMD ["/bin/bash"]
