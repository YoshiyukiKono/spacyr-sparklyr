# Usage Guide

## Dependencies

### R

#### Anaconda

r-essentials

https://anaconda.org/r/r-essentials 

`conda create -p ~/r_env --copy -y -q -c r r-essentials python=2.7`

#### CDSW Engine

In case there is a mismatch, you will see the log below in STDOUT of the worker process. 

`ERROR sparklyr: RScript (3132) terminated unexpectedly: package 'reticulate’ was installed by an R version with different internals; it needs to be reinstalled for use with this R version`

## Environment

### Resource

Worker: t2.2xlarge - vCPU 8, RAM 32G

### Configuration

```
ExecutorLostFailure (executor 2 exited caused by one of the running tasks) Reason: Container killed by YARN for exceeding memory limits.  9.4 GB of 9 GB physical memory used. Consider boosting spark.yarn.executor.memoryOverhead or disabling yarn.nodemanager.vmem-check-enabled because of YARN-4714.
```

yarn-site.xml
```
<property><name>yarn.nodemanager.pmem-check-enabled</name><value>false</value></property>
```

https://issues.apache.org/jira/browse/YARN-4714?page=com.atlassian.jira.plugin.system.issuetabpanels%3Aall-tabpanel

https://hadoop.apache.org/docs/r2.7.7/hadoop-yarn/hadoop-yarn-common/yarn-default.xml
