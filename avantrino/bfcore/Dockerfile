FROM ubuntu:trusty

MAINTAINER  bluefish-team

#create a directory for Workdir
RUN mkdir /mybluefish

#From now on all operations will happen from here
WORKDIR /mybluefish

#Update the mongodb3.0 repo details and respective public key
RUN echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.0 multiverse" > /etc/apt/sources.list.d/mongodb-org-3.0.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10

#Updates the repository packages list and Install required dependencies
#Install Python dependencies
#Install Other dependencies
#Install Python Pandas
#Install Database related dependencies
RUN apt-get update && apt-get install -y python2.7 python-setuptools build-essential python-dev python-distribute \
                      libxml2-dev libxslt1-dev lib32z1-dev libffi-dev libssl-dev libcups2-dev  libatlas-base-dev \
            		      libcurl4-gnutls-dev librtmp-dev gfortran python-numpy cython libcurl4-gnutls-dev \
            		      openssh-server sshpass \
            		      python-pandas \
            		      python-scipy \
            		      python-matplotlib \
            		      python-statsmodels \
                      python-tables \
                      redis-tools \
            		      mysql-client libmysqlclient-dev \
            		      postgresql-client libpq-dev \
            		      mongodb-org-shell mongodb-org-tools \
            		      sqlite3 \
            		      gcc \
            		      python-mysqldb \
            		      rsync snmp strace ltrace lsof pstack \
                      --no-install-recommends && rm -rf /var/lib/apt/lists/*

#Install latest version of pip  
RUN easy_install --upgrade pip setuptools

#Copy Python dependencies, Note that any PATH is relative to Context Directory
#Install Python dependencies, Note that any PATH is relative to WORKDIR
ADD requirements-caps.txt /mybluefish/requirements-caps.txt
RUN pip install -r requirements-caps.txt

ADD requirements-abc.txt /mybluefish/requirements-abc.txt
RUN pip install -r requirements-abc.txt

ADD requirements-def.txt /mybluefish/requirements-def.txt
RUN pip install -r requirements-def.txt

ADD requirements-ghi.txt /mybluefish/requirements-ghi.txt
RUN pip install -r requirements-ghi.txt

ADD requirements-jkl.txt /mybluefish/requirements-jkl.txt
RUN pip install -r requirements-jkl.txt

ADD requirements-mno.txt /mybluefish/requirements-mno.txt
RUN pip install -r requirements-mno.txt

ADD requirements-pqr.txt /mybluefish/requirements-pqr.txt
RUN pip install -r requirements-pqr.txt

ADD requirements-stu.txt /mybluefish/requirements-stu.txt
RUN pip install -r requirements-stu.txt

ADD requirements-vwxyz.txt /mybluefish/requirements-vwxyz.txt
RUN pip install -r requirements-vwxyz.txt

CMD ["/bin/true"]
