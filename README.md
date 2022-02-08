# Open ONI Sample Data

Small batches that can be used in development installations of Open ONI... and other miscellaneous files.

### Loading a Batch

This repository is intended to be used with the [Open ONI](https://github.com/open-oni/open-oni) repository.
The batches included in this repository are valid enough that they can be loaded into the software.  However, they are neither complete nor polished batches.

Clone the repository.  Then, copy or move batches to your Open ONI `data/batches` directory (or the `docker/data` directory if you are using the docker setup).

From inside of the Open ONI app:

```
cd /opt/openoni
source /opt/openoni/ENV/bin/activate
django-admin.py load_batch /batches/prefix_batchname/batch_prefix_name_ver01
```

If you are using docker development environment, please see the [docker](https://github.com/open-oni/open-oni/wiki/Docker) wiki pages for instructions for loading a batch when using docker containers.

### Batch Description

| Name | Description | Language | Source |
| --- | --- | --- | --- |
| dlc_manyyears | 1 issue and page from 15 different years | English | [dlc_leonberger](https://chroniclingamerica.loc.gov/batches/batch_dlc_leonberger_ver03) and [dlc_ixtl](https://chroniclingamerica.loc.gov/batches/batch_dlc_ixtl_ver01) |
| mnhi_german | 1 issue of 8 pages | German | [mnhi_uhaul](https://chroniclingamerica.loc.gov/batches/batch_mnhi_uhaul_ver01) |
| nbu_manyissues | 9 issues of 1 page | English | [nbu_chadron](https://chroniclingamerica.loc.gov/batches/batch_nbu_chadron_ver01) |

### env.tar.gz

If you're using our Docker setup but can't get the install working, it may be due to an inability to fetch dependencies.  Try removing your local ENV directory and extracting our `env.tar.gz` file.  This should provide a suitable base for using Docker.
