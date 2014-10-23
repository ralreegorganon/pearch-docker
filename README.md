```
PEARCH_DATABASE_DIR=$HOME/dev/databases/pearch/data

docker build -t archiver archiver
docker build -t database database
docker run -d  -v $PEARCH_DATABASE_DIR:/data  --name pearch-database database
docker run -d --link pearch-database:pg --name pearch-archiver archiver

docker run --rm -i -t -link pearch-database:pg archiver bash
```
