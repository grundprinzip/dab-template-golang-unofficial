# Spark Connect Go Instructions

This package uses the Spark Connect Go client and the unofficial Databricks
Connect Go client to connect to either a local cluster, a remote cluster
or the Serverless Spark endpoint.

Before deploying your job you have to make sure that the binaries are built
correctly because they're referenced directly from the job.


## Build

Simply running `make` will cross compile the targets both for Apple Silicon and
for standard X86 Linux. If you want to add any other cross compilation targets,
simply updated the Makefile.

```shell
make
```


## Extending the Example Code

The code in `transforms/transform.go` and `main/main.go` can be extended to suit
your needs and can essentially use all features of the Spark Connect Go connector.