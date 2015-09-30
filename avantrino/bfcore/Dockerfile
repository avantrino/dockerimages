FROM ubuntu:trusty

MAINTAINER  bluefish-team

#create a directory for Workdir
RUN mkdir /mybluefish

#From now on all operations will happen from here
WORKDIR /mybluefish

#Updates the repository packages list
RUN apt-get update

#Install Python and it's tool dependencies
RUN apt-get install -y python2.7 python-setuptools build-essential python-dev python-distribute python-pip 

#Install Other dependencies
RUN apt-get install -y libxml2-dev libxslt1-dev lib32z1-dev libssl-dev libcups2-dev  libatlas-base-dev
RUN apt-get install -y libcurl4-gnutls-dev librtmp-dev gfortran python-numpy cython libcurl4-gnutls-dev
RUN apt-get install -y openssh-server sshpass

#Install Python Pandas
RUN apt-get install -y python-pandas

#Install mysql related dependencies
RUN apt-get install -y \
    mysql-client libmysqlclient-dev \
    postgresql-client libpq-dev \
    mongodb-clients \
    sqlite3 \
    gcc \
    python-mysqldb \
  --no-install-recommends && rm -rf /var/lib/apt/lists/*

#Copy Python dependencies, Note that any PATH is relative to Context Directory
ADD requirements.txt /mybluefish/requirements.txt

#Install Python dependencies, Note that any PATH is relative to WORKDIR
RUN pip install -r requirements.txt

CMD ["/bin/true"]
