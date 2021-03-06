[![Build Status](https://travis-ci.org/geopython/GeoHealthCheck.png)](https://travis-ci.org/geopython/GeoHealthCheck)

GeoHealthCheck
==============

Service Status Checker for OGC Web Services

```bash
virtualenv GeoHealthCheck && cd $_
. bin/activate
git clone https://github.com/geopython/GeoHealthCheck.git
cd GeoHealthCheck
pip install Paver
# setup installation
paver setup
# generate secret key
paver create_secret_key
# setup local configuration
vi instance/config.py
# edit:
# - SQLALCHEMY_DATABASE_URI
# - SECRET_KEY  # from paver create_secret_key
# - GHC_RETENTION_DAYS
# - GHC_RUN_FREQUENCY
# - GHC_SELF_REGISTER
# - GHC_ADMIN_EMAIL
# - GHC_SITE_TITLE

# setup database and superuser account
paver create

# drop database
python GeoHealthCheck/models.py drop

# start server (default is 0.0.0.0:8000)
python GeoHealthCheck/app.py  
# start server on another port
python GeoHealthCheck/app.py 0.0.0.0:8881
# start server on another IP
python GeoHealthCheck/app.py 192.168.0.105:8001
```


users
- view all services
- view service

admin
- drop db
- create db
- add service
- delete service
- run health check (cron or interactive)
