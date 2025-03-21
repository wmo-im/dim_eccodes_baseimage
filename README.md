# dim_eccodes_baseimage

This repository contains the Dockerfile for the base image used by [wis2box-api](https://github.com/World-Meteorological-Organization/wis2box-api), providing a pre-compiled version of the [eccodes](https://confluence.ecmwf.int/display/ECC/ecCodes+Home) library to enable data-conversion capabilities within [wis2box](https://docs.wis2box.wis.wmo.int).

The baseimage can also be used to gain access to the [eccodes command-line tools](https://confluence.ecmwf.int/display/ECC/Command+line+tools) without requiring the installation of the eccodes library on the host machine.

Note that the image does not track eccodes releases, but is updated on a case-by-case basis.

## Building and using the baseimage

```bash
docker build -t dim_eccodes_baseimage .
```

To run the baseimage and share a directory with data on the host machine:

```bash
docker run -it -v /path/to/data:/data dim_eccodes_baseimage /bin/bash
```

Within the baseimage you can run the following command to check the version of the eccodes library:

```bash
bufr_dump -V
```

To run bufr_dump on a file in the shared directory:

```bash
bufr_dump /data/your_file.bufr
```

## Contact

* [David Berry](https://github.com/david-i-berry)
* [Maaike Limper](https://github.com/maaikelimper)
