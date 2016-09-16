# Dockerfile written by Eric Mann <eric@tozny.com>
#
# Copyright (c) 2016 Tozny, LLC

FROM tozny/docker-java

RUN apk update && apk upgrade && apk add --no-cache \
    wget \
    ruby \
    && echo 'gem: --no-document' > /etc/gemrc

RUN gem install --no-doc asciidoctor-pdf --pre
RUN wget -O swagger2markup-cli-1.0.1.jar 'https://bintray.com/swagger2markup/Maven/download_file?file_path=io%2Fgithub%2Fswagger2markup%2Fswagger2markup-cli%2F1.0.1%2Fswagger2markup-cli-1.0.1.jar'

CMD java -jar swagger2markup-cli-1.0.1.jar convert \
    --swaggerInput /in/swagger.y*ml \
    --outputFile /out/swagger && \
    asciidoctor-pdf /out/swagger.adoc \
    --doctype book \
    -a toc=left \
    -a toclevels=3 \
    -a numbered= \
    -a sectlinks= \
    -a sectanchors= \
    -a hardbreaks=
