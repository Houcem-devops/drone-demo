FROM docker.io/maven:3.8.5-openjdk-11-slim
LABEL org.opencontainers.image.source https://github.com/kameshsampath/drone-java-maven-plugin
LABEL org.opencontainers.image.authors="Kamesh Sampath<kamesh.sampath@hotmail.com>"

LABEL description="A Drone plugin to build Java applications using Apache Maven"
LABEL MAVEN_VERSION=3.8.5
LABEL JAVA_VERSION=11

RUN apt-get update \
  && apt-get install -y ca-certificates \
  && rm -rf /var/lib/apt/lists/*

# TODO: enable to run as non-root
# RUN adduser --system --uid 1001 dev \
#     && mkdir -p /home/dev/.m2 \
#     && chown 1001:0 /home/dev/.m2

ADD run.sh /bin/
RUN chmod +x /bin/run.sh

# TODO: enable to run as non-root
# USER dev

# TODO: enable to run as non-root
# ENV USER_HOME_DIR=/home/dev
# ENV MAVEN_CONFIG=/home/dev/.m2

CMD ["/bin/run.sh"]