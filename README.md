# hadoopiii2015

## vm download

- https://downloads.cloudera.com/demo_vm/vmware/cloudera-quickstart-vm-5.2.0-0-vmware.7z

## [實際應用] 使用Hadoop 分析 Facebook 打卡資訊

- https://www.youtube.com/watch?v=FQr2nVvkLzc

## 設定權限
- 切換成 root 使用者

$ su –

- 使用visudo 編輯權限

$ visudo 

- 給予sudo 權限 (於99行處)

tibame	ALL=(ALL)	ALL

## Java 安裝

### 移除舊的Java
- yum -y remove java-*

### 下載及安裝Java

- http://www.oracle.com/technetwork/java/javase/downloads/index.html

- rpm -ivh jdk-8u40-linux-x64.rpm



### 設定Hadoop

- wget http://ftp.twaren.net/Unix/Web/apache/hadoop/common/hadoop-2.6.0/hadoop-2.6.0.tar.gz

- tar -zxvf hadoop-2.6.0.tar.gz

### 新增群組hadoop
- $ sudo groupadd hadoop

### 建立 hadoop 使用者並將hadoop加入hadoop 群組
- $ sudo useradd -g hadoop hadoop

### 將Hadoop 2.6.0 搬移到 /usr/local
- sudo mv ~/hadoop-2.6.0 /usr/local/hadoop

###更改該目錄權限
- sudo chown -R hadoop:hadoop /usr/local/hadoop

### 切換至Hadoop 使用者
- sudo su - hadoop

### 編輯.bashrc
- $ vim ~/.bashrc
- export JAVA_HOME=/usr/java/jdk1.8.0_45/
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
- service sshd restart

### 設置無密碼登入
- ssh-keygen -t dsa -P '' -f ~/.ssh/id_dsa
- cat ~/.ssh/id_dsa.pub >> ~/.ssh/authorized_keys
- chmod 700 ~/.ssh
- chmod 600  ~/.ssh/authorized_keys

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