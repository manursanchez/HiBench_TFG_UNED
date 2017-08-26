# Customization of HiBench Suite for UNED End-Of-Degree Project
## This fork of HiBench is created specifically to test the performance of a particular infrastructure with MapR, Cloudera and Hortonworks as part of my End-of-Degree Project. ##

* Current version: 6.0
* Original Homepage: https://github.com/intel-hadoop/HiBench
* Contents:
  1. Overview
  2. Getting Started
  3. Workloads
  4. Supported Releases

---
### OVERVIEW ###

HiBench is a big data benchmark suite that helps evaluate different big data frameworks in terms of speed, throughput and system resource utilizations.

I will use the set of Hadoop including just this three big data frameworks enhanced DFSIO, Bayes and PageRank.

### Getting Started ###
 * [Build HiBench](docs/build-hibench.md)
 * [Run HadoopBench](docs/run-hadoopbench.md)

### Workloads ###

There are totally 19 workloads in HiBench but i have only set the configuration for the 3 mentioned before. This workloads are divided into 3 categories which are micro, ml(machine learning) and websearch.

  **Micro Bechmarks:**

1. enhanced DFSIO (dfsioe)

    Enhanced DFSIO tests the HDFS throughput of the Hadoop cluster by generating a large number of tasks performing writes and reads simultaneously. It measures the average I/O rate of each map task, the average throughput of each map task, and the aggregated throughput of HDFS cluster. Note: this benchmark doesn't have Spark corresponding implementation.


**Machine Learning:**

1. Bayesian Classification (bayes)

    This workload benchmarks NaiveBayesian Classification implemented in Spark-MLLib/Mahout examples.

    Large-scale machine learning is another important use of MapReduce. This workload tests the Naive Bayesian (a popular classification algorithm for knowledge discovery and data mining)  trainer in Mahout 0.7, which is an open source (Apache project) machine learning library. The workload uses the automatically generated documents whose words follow the zipfian distribution. The dict used for text generation is also from the default linux file /usr/share/dict/linux.words.

**Websearch Benchmarks:**

1. PageRank (pagerank)

    This workload benchmarks PageRank algorithm implemented in Spark-MLLib/Hadoop (a search engine ranking benchmark included in pegasus 2.0) examples. The data source is generated from Web data whose hyperlinks follow the Zipfian distribution.

   
### Supported Hadoop releases: ###

  - Hadoop: MapR, CDH5, HDP

---


