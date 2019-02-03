# hadoop2-pseudo-distributed-centos7
Install Hadoop 2 mode pseudo-distributed pada Centos 7 dan menjalankan contoh aplikasi MapReduce.

Artikel ini dimuat di http://www.teknologi-bigdata.com/ website tentang teori dan contoh implementasi teknologi Big Data.

Software yang diperlukan:
1. Java JDK 1.8 https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
2. Hadoop-2.7.7 https://hadoop.apache.org/releases.html

Install Oracle JDK 1.8 pada Centos7
1. Unduh Oracle JDK 1.8 untuk Linux x64 dari https://download.oracle.com/otn-pub/java/jdk/8u201-b09/42970487e3af4f5aa5bca3f542482c60/jdk-8u201-linux-x64.tar.gz kemudian ekstrak file tersebut di direktori /opt dengan perintah
tar xzf jdk-8u201-linux-x64.tar.gz
sehingga dihasilkan direktori /opt/jdk1.8.0_201/
2. Install Java dengan perintah alternatives --install /usr/bin/java java /opt/jdk1.8.0_201/bin/java 2
3. Gunakan perintah alternatives --config java untuk menampilkan versi Java yang sudah ter-install, kemudian kita bisa memilih Java versi yang mana yang akan dijadikan default. Dalam hal ini silakan pilih /opt/jdk1.8.0_201/bin/java
4. Pastikan versi Java yang telah dipilih dengan perintah java -version

Install Hadoop-2.7.7 mode Pseudo-distributed
1. Buat dedicated user untuk Hadoop dengan perintah
useradd hadoop
passwd hadoop
Kemudian login dengan user tersebut.
2. Edit file .bash_profile yang ada di home directory user hadoop (/home/hadoop/.bash_profile)

export JAVA_HOME=/opt/jdk1.8.0_201
export JRE_HOME=/opt/jdk1.8.0_201/jre
export PATH=$PATH:/opt/jdk1.8.0_201/bin:/opt/jdk1.8.0_201/jre/bin
export CLASSPATH=.:/opt/jdk1.8.0_201/jre/lib:/opt/jdk1.8.0_201/lib:/opt/jdk1.8.0_201/lib/tools.jar
export HADOOP_CLASSPATH=/opt/jdk1.8.0_201/lib/tools.jar
export HADOOP_HOME=/opt/hadoop
export HADOOP_INSTALL=$HADOOP_HOME
export HADOOP_MAPRED_HOME=$HADOOP_HOME
export HADOOP_COMMON_HOME=$HADOOP_HOME
export HADOOP_HDFS_HOME=$HADOOP_HOME
export YARN_HOME=$HADOOP_HOME
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin


