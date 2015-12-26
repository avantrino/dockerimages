FROM ubuntu:trusty

MAINTAINER  bluefish-team

#create a directory for Workdir
RUN mkdir /mybluefish

#From now on all operations will happen from here
WORKDIR /mybluefish

#Update the mongodb3.0 repo details
echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.0 multiverse" > /etc/apt/sources.list.d/mongodb-org-3.0.list

#Updates the repository packages list and Install required dependencies
#Install Python dependencies
#Install Other dependencies
#Install Python Pandas
#Install Database related dependencies
RUN apt-get update && apt-get install -y python2.7 python-setuptools build-essential python-dev python-distribute python-pip \
                      libxml2-dev libxslt1-dev lib32z1-dev libssl-dev libcups2-dev  libatlas-base-dev \
		      libcurl4-gnutls-dev librtmp-dev gfortran python-numpy cython libcurl4-gnutls-dev \
		      openssh-server sshpass \
		      python-pandas \
		      mysql-client libmysqlclient-dev \
		      postgresql-client libpq-dev \
		      mongodb-org-shell mongodb-org-tools \
		      sqlite3 \
		      gcc \
		      python-mysqldb \
                      --no-install-recommends && rm -rf /var/lib/apt/lists/*  

#Copy Python dependencies, Note that any PATH is relative to Context Directory
ADD requirements.txt /mybluefish/requirements.txt

#Install Python dependencies, Note that any PATH is relative to WORKDIR
RUN pip install -r requirements.txt

CMD ["/bin/true"]
