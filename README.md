This repository holds conda recipes for the various NTDMC models as
well as `AmisfoInfectiousDiseases` R package.

To build packages from the recipes, you'll need the conda package
manager and conda-build utility.  See below for information on how to
install both these tools.

To build a package, navigate into the specific repository and use the
`conda build` command:

```shell
cd trachoma && conda build .
```

Built packages are available locally under
`/path/to/conda/install/conda-bld/<arch>/`, for instance

```
/home/<user>/miniconda3/conda-bld/linux-64/amisforinfectiousdiseases-0.0.1-r43h9bf148f_0.tar.bz2`
```

Newly built packages can be installed using the `--use-local` flag:

```shell
conda install --use-local ntd-trachoma
```

Note that using `--use-local` means bypassing the dependency resolver,
and therefore runtime dependencies will not be installed automatically.

Since note the `conda-bld` is structured as a [conda
channel](https://docs.conda.io/projects/conda-build/en/stable/concepts/generating-index.html), it is possible to use it as-is to install a package:

```shell
conda search --channel file:///home/<user>/miniconda3/conda-bld/ trachoma
```