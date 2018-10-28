# kdi_project
Resources and code used for the KDI course project.

In the root folder it is possible to find:

* filtering_tag, filtering_tag2: the tags used to filter the .osm files (filtering_tag2 has not been used)
* osm_scripts, set of commands and generalised info about osm file processing
  both with `osm-tools` and `osmium`, in addition to useful code snippets
* pyosm, a python library used to build a SQLite db out of an .osm file.
  Which could be used to obtain tags out of the various OSM entities, in
  scenarios where `osmium` and `osm-tools` **seem not** to do the job.
____

## PyOSM

In the folder pyosm there is the Python3 code used to build, populate
and manage the SQLite database.

Within the folder the program can be called by issuing the `pyosm` command,
following the helper.

### Building the DB

To build the DB pick the `.osm` where nodes should be
taken from and placed into the `/pyosm` folder starting
from the git project root directory. Then issue the command:

```bash
python3 pyosm.py <my_file.osm> <destination_db.db>
```

This will create the SQLite `destination_db.db` file and
populate it.

### Merging nodes

In order for nodes to inherit tags from the relations and the
ways they are in, the `pyosm` program can be
used. Given the db file previously populated, the
following command will perform the merging job:

```bash
python3 pyosm.py -m <populated_osm.db>
```
____
