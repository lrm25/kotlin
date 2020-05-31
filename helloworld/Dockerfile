FROM ubuntu

# dependencies
RUN apt update --fix-missing
RUN apt install -y curl unzip zip git

# sdkman
RUN curl -s https://get.sdkman.io | bash
RUN /bin/bash -c "source /root/.sdkman/bin/sdkman-init.sh;sdk install kotlin"

# git
RUN git clone https://github.com/lrm25/kotlin
RUN DEBIAN_FRONTEND=noninteractive apt install -y tzdata
# TODO probably don't need the whole jdk
RUN apt install -y default-jdk
RUN /bin/bash -c "/root/.sdkman/candidates/kotlin/current/bin/kotlinc /kotlin/helloworld/helloworld.kt"
# TODO may need version parameter in future
CMD java -cp /root/.sdkman/candidates/kotlin/1.3.72/lib/kotlin-runner.jar:. HelloworldKt
