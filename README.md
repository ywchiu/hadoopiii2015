# hadoopiii2015


## Slides:
- https://www.slideshare.net/secret/MD4bBCWKjGNTIW


## vm download

- https://downloads.cloudera.com/demo_vm/vmware/cloudera-quickstart-vm-5.2.0-0-vmware.7z

## [實際應用] 使用Hadoop 分析 Facebook 打卡資訊

- https://www.youtube.com/watch?v=FQr2nVvkLzc

## Java 安裝

### 移除舊的Java
- sudo yum -y remove java-*

### 下載及安裝Java

- http://www.oracle.com/technetwork/java/javase/downloads/index.html

- sudo rpm -ivh jdk-8u51-linux-x64.rpm

### 設定Hadoop

- wget http://ftp.twaren.net/Unix/Web/apache/hadoop/common/hadoop-2.6.0/hadoop-2.6.0.tar.gz

- tar -zxvf hadoop-2.6.0.tar.gz

### 編輯.bashrc
- $ vim ~/.bashrc
- export JAVA_HOME=/usr/java/jdk1.8.0_51/
- export PATH=$PATH:$JAVA_HOME
- export HADOOP_PREFIX=/usr/local/hadoop 
- export HADOOP_COMMON_HOME=$HADOOP_PREFIX 
- export HADOOP_HDFS_HOME=$HADOOP_PREFIX 
- export HADOOP_MAPRED_HOME=$HADOOP_PREFIX 
- export HADOOP_YARN_HOME=$HADOOP_PREFIX 
- export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_PREFIX/lib/native
- export HADOOP_OPTS="-Djava.library.path=$HADOOP_PREFIX/lib"
- export HADOOP_CONF_DIR=$HADOOP_PREFIX/etc/hadoop 
- export PATH=$PATH:$HADOOP_PREFIX/bin:$HADOOP_PREFIX/sbin

### 更新變數
$ source ~/.bashrc

### 嘗試是否可以無密碼登入
- ssh localhost

修改/etc/ssh/sshd_config
- 將PasswordAuthentication 變更為no
- sudo service sshd restart

### 設置無密碼登入
- ssh-keygen -t dsa -P '' -f ~/.ssh/id_dsa
- cat ~/.ssh/id_dsa.pub >> ~/.ssh/authorized_keys
- chmod 700 ~/.ssh
- chmod 600  ~/.ssh/authorized_keys

### Reference following link to revise file respectively
- /usr/local/hadoop/etc/hadoop/
- https://github.com/ywchiu/hadoopiii2015/blob/master/pseudo-distribution.xml

### 格式化HDFS
- hdfs namenode -format

### 啟用HDFS及YARN
- start-dfs.sh
- start-yarn.sh

### Blog Data
- http://www.race.u-tokyo.ac.jp/~uchida/blogdata/sclick.php?UID=blogdata1.tgz&URL=./blogdata1.tgz

### 安裝rar, unrar
- wget http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.2-2.el6.rf.i686.rpm
- rpm -Uvh rpmforge-release-0.5.2-2.el6.rf.i686.rpm
- yum install rar unrar

### 5.2 Cloudera Quickstart VM
- https://downloads.cloudera.com/demo_vm/vmware/cloudera-quickstart-vm-5.2.0-0-vmware.7z
