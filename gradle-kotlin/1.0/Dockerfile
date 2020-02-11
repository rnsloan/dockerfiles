FROM debian:bullseye-20200130-slim
LABEL Maintainer="rnsloan1@gmail.com" Version="1.0.0"
LABEL Description="Gradle and Kotlin" 
ENV REFRESHED_AT 2020-2-11

# software versions
# overide during image creation: docker build --build-arg JAVA_VERSION=11.0.5-amzn <NAME>:<TAG> .
ARG JAVA_VERSION="13.0.2.hs-adpt"
ARG GRADLE_VERSION="6.1.1"
ARG KOTLIN_VERSION="1.3.61"

# create non-root user
ARG USER_GID="1000"
ARG GROUP_NAME="kotlin"
ARG USER_UID="1000"
ARG USER_NAME="kotlin"

# Creating non-root user 
RUN groupadd -g $USER_GID $USER_NAME && \
	useradd -m -g $USER_GID -u $USER_UID $USER_NAME

# Install SDKMAN! dependencies
RUN apt-get update && \
	apt-get install -y zip unzip curl && \
	rm -rf /var/lib/apt/lists/* && \
	rm -rf /tmp/*

# Switch to non-root user
USER $USER_UID:$USER_GID

# SDKMAN!
RUN curl -s "https://get.sdkman.io" | bash

# Install java, gradle, kotlin
RUN bash -c "source $HOME/.sdkman/bin/sdkman-init.sh && \
	yes | sdk install java $JAVA_VERSION && \
	yes | sdk install gradle $GRADLE_VERSION && \
	yes | sdk install kotlin $KOTLIN_VERSION"

# Clean-up
RUN bash -c "rm -rf $HOME/.sdkman/archives/* && \
	rm -rf $HOME/.sdkman/tmp/*"

ENTRYPOINT bash -c "source $HOME/.sdkman/bin/sdkman-init.sh && $0 $@"	