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

### 設定Java ~/.bashrc

- export JAVA_HOME=/usr/java/jdk1.8.0_40/

- export PATH=$PATH:$JAVA_HOME
