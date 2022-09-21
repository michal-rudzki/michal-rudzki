FROM ubuntu/apache2
RUN echo "Django Project"
RUN echo "---------- Ubuntu Update... -----------"
RUN apt-get -yq install tzdata
RUN ln -fs /usr/share/zoneinfo/Europe/Warsaw /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata
RUN export TZ="Europe/Warsaw"
RUN apt-get -y update
RUN apt-get -y upgrade
RUN echo "Install python"
RUN apt-get -y install python3
RUN apt-get -y install python3-pip
