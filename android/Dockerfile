# Version 1.0.0

FROM centos

MAINTAINER wasabeef <dadadada.chop@gmail.com>

# Epel
RUN rpm -Uvh http://download.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm

# Install Development Tools
RUN yum -y groupinstall "Development Tools"

# yum update
RUN yum -y update
RUN yum clean all

# Install java (OpenJDK)
RUN yum -y install java-1.7.0-openjdk-devel

# Install 32bit Library
RUN yum -y install glibc.i686
RUN yum -y install libstdc++.i686
RUN yum -y install glibc-devel.i686
RUN yum -y install zlib-devel.i686
RUN yum -y install ncurses-devel.i686
RUN yum -y install libX11-devel.i686
RUN yum -y install libXrender.i686

# Install Android SDK
RUN cd /usr/local/ && curl -L -O http://dl.google.com/android/android-sdk_r22.3-linux.tgz && tar xvf android-sdk_r22.3-linux.tgz

# Install Android tools
RUN echo y | /usr/local/android-sdk-linux/tools/android update sdk --filter extra --no-ui --force -a
RUN echo y | /usr/local/android-sdk-linux/tools/android update sdk --filter tools --no-ui --force -a
RUN echo y | /usr/local/android-sdk-linux/tools/android update sdk --filter platform-tools --no-ui --force -a
RUN echo y | /usr/local/android-sdk-linux/tools/android update sdk --filter android-18 --no-ui --force -a
RUN echo y | /usr/local/android-sdk-linux/tools/android update sdk --filter android-19 --no-ui --force -a
RUN export PATH=$PATH:/usr/local/android-sdk-linux/tools
RUN export PATH=$PATH:/usr/local/android-sdk-linux/platform-tools

# Install Android NDK
RUN cd /usr/local && curl -L -O http://dl.google.com/android/ndk/android-ndk-r9b-linux-x86_64.tar.bz2 && tar xvf android-ndk-r9b-linux-x86_64.tar.bz2
RUN export PATH=$PATH:/usr/local/android-ndk-r9b

# Install Apache-Ant
RUN cd /usr/local/ && curl -L -O http://ftp.meisei-u.ac.jp/mirror/apache/dist//ant/binaries/apache-ant-1.9.2-bin.tar.gz && tar xvf apache-ant-1.9.2-bin.tar.gz
RUN export PATH=$PATH:/usr/local/apache-ant-1.9.2/bin

# Install Maven
RUN cd /usr/local/ && curl -L -O http://ftp.tsukuba.wide.ad.jp/software/apache/maven/maven-3/3.1.1/binaries/apache-maven-3.1.1-bin.tar.gz && tar xvf apache-maven-3.1.1-bin.tar.gz
RUN export PATH=$PATH:/usr/local/apache-maven-3.1.1/bin

# Install Gradle
RUN cd /usr/local/ && curl -L -O http://services.gradle.org/distributions/gradle-1.9-all.zip && unzip gradle-1.9-all.zip
RUN export PATH=$PATH:/usr/local/gradle-1.9/bin

# Environment variables
ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV ANDROID_NDK_HOME /usr/local/android-ndk-r9b
ENV ANT_HOME /usr/local/apache-ant-1.9.2
ENV MAVEN_HOME /usr/local/apache-maven-3.1.1
ENV GRADLE_HOME /usr/local/gradle-1.9

# Clean up
RUN rm -rf /usr/local/android-sdk_r22.3-linux.tgz
RUN rm -rf /usr/local/android-ndk-r9b-linux-x86_64.tar.bz2
RUN rm -rf /usr/local/apache-ant-1.9.2-bin.tar.gz
RUN rm -rf /usr/local/apache-maven-3.1.1-bin.tar.gz
RUN rm -rf /usr/local/gradle-1.9-all.zip

