# Open ONI Sample Data

Small batches that can be used in development installations of Open ONI... and other miscellaneous files.

Note that `batch_mnhi_german_ver01` now has emoji in the OCR XML
of its first page, which requires ONI with UTF8 database fix:
https://github.com/open-oni/open-oni/pull/612

If one needs to test without emoji in the sample batches,
check out [the last commit before the emoji were
added](https://github.com/open-oni/sample-data/commit/67124a27510e81ff46436c58742e6e845a999536):

```bash
git checkout 67124a2
```

### Loading a Batch

This repository is intended to be used with the [Open ONI](https://github.com/open-oni/open-oni) repository.
The batches included in this repository are valid enough that they can be loaded into the software.  However, they are neither complete nor polished batches.

Clone the repository.  Then, copy or move batches to your Open ONI `data/batches/` directory.

Follow these commands to load the sample data into Open ONI (assuming it lives in `/opt/openoni` for a non-Docker deployment):

```bash
cd /opt/openoni
. /ENV/bin/activate
./manage.py load_batch data/batches/batch_dlc_manyyears_ver01
./manage.py load_batch data/batches/batch_mnhi_german_ver01
./manage.py load_batch data/batches/batch_nbu_manyissues_ver01
```

For a Docker environment, run these commands:

```bash
docker compose up -d
docker compose exec web /load_batch.sh batch_dlc_manyyears_ver01
docker compose exec web /load_batch.sh batch_mnhi_german_ver01
docker compose exec web /load_batch.sh batch_nbu_manyissues_ver01
```

See the [Docker Command Quick
Reference](https://github.com/open-oni/open-oni/blob/dev/docs/advanced/docker-reference.md)
for more help with Docker environment commands.

### Batch Description

| Name | Description | Language | Source |
| --- | --- | --- | --- |
| dlc_manyyears | 1 issue and page from 15 different years | English | [dlc_leonberger](https://chroniclingamerica.loc.gov/batches/batch_dlc_leonberger_ver03) and [dlc_ixtl](https://chroniclingamerica.loc.gov/batches/batch_dlc_ixtl_ver01) |
| mnhi_german | 1 issue of 8 pages | German | [mnhi_uhaul](https://chroniclingamerica.loc.gov/batches/batch_mnhi_uhaul_ver01) |
| nbu_manyissues | 9 issues of 1 page | English | [nbu_chadron](https://chroniclingamerica.loc.gov/batches/batch_nbu_chadron_ver01) |

### Docker Troubleshooting
If the Docker environment is giving you lots of trouble, you may want to
[erase your environment and start fresh](https://github.com/open-oni/open-oni/blob/dev/docs/install/docker.md#erase-and-start-fresh)
