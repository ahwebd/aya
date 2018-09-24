The following docker images:
```
ahwebd/postgres-repmgr
ahwebd/barman-postgres
ahwebd/pgpool-postgres
```
are based on [PostDock-1.11](https://github.com/paunin/PostDock/archive/1.11.tar.gz)
and built using the following commands:

```bash
docker build -t ahwebd/postgres-repmgr -f path/to/postdock/PostDock-1.11/src/Postgres-10-Repmgr-4.0.Dockerfile path/to/postdock/PostDock-1.11/src
docker build -t ahwebd/barman-postgres -f path/to/postdock/PostDock-1.11/src/Barman-2.4-Postgres-10.Dockerfile path/to/postdock/PostDock-1.11/src
docker build -t ahwebd/pgpool-postgres -f path/to/postdock/PostDock-1.11/src/Pgpool-3.7-Postgres-10.Dockerfile path/to/postdock/PostDock-1.11/src
```
