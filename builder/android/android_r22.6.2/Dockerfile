FROM bradrydzewski/java:oraclejdk7

WORKDIR /home/ubuntu
USER ubuntu
ADD android.sh /etc/drone.d/

RUN sudo apt-get update && \
    sudo apt-get -y install lib32stdc++6 lib32z1 && \
    wget http://dl.google.com/android/android-sdk_r22.6.2-linux.tgz && \
    sudo tar -C /usr/local -xzf android-sdk_r22.6.2-linux.tgz && \
    sudo chown -R ubuntu:ubuntu /usr/local/android-sdk-linux && \
    rm android-sdk_r22.6.2-linux.tgz && \
    (while :; do echo 'y'; sleep 2; done) | /usr/local/android-sdk-linux/tools/android update sdk --filter platform,tool,platform-tool,extra,build-tools-19.1.0 --no-ui --force -a
