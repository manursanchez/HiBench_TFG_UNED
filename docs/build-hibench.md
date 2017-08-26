### Build a specific framework benchmark ###
HiBench 6.0 supports building only benchmarks for a specific framework. 
For this costumization we only need to build the Hadoop benchmarks, so we can use the below command:

    mvn -Phadoopbench -Dspark=2.1 -Dscala=2.11 clean package

### Specify Scala Version ###
To specify the Scala version, use -Dscala=xxx(2.10 or 2.11). By default, it builds for scala 2.11.

    mvn -Dscala=2.10 clean package
tips:
Because some Maven plugins cannot support Scala version perfectly, there are some exceptions.

1. No matter what Scala version is specified, the module (gearpumpbench/streaming) is always built in Scala 2.11.
2. When the spark version is specified to 2.0, the module (sparkbench/streaming) is only supported for Scala 2.11.

### Specify Spark Version ###
To specify the spark version, use -Dspark=xxx(1.6, 2.0 or 2.1). By default, it builds for spark 2.0

    mvn -Psparkbench -Dspark=1.6 -Dscala=2.11 clean package
tips:
when the spark version is specified to spark2.0(1.6) , the scala version will be specified to scala2.11(2.10) by
default . For example , if we want use spark2.0 and scala2.11 to build hibench. we just use the command `mvn -Dspark=2.0 clean
package` , but for spark2.0 and scala2.10 , we need use the command `mvn -Dspark=2.0 -Dscala=2.10 clean package` .
Similarly , the spark1.6 is associated with the scala2.10 by default.

### Build a single module ###
If you are only interested in a single workload in HiBench. You can build a single module. For example, the below command only builds the micro workloads for Hadoop.

    mvn -Phadoopbench -Dmodules -Pmicro -Dspark=2.1 -Dscala=2.11 clean package

Supported modules includes: micro, ml(machine learning) and websearch.
