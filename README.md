make up-all-no-cache-without-monitoring-prod
make down-all-without-monitoring-prod

CHANGE 'DATABASE_WHICH_YOU_CREATED_IN_ODOO_WEB_INTERFACE' -> docker_compose/db/backup.sh

# Vendor folder with OCA/OCB Odoo:

git clone https://github.com/OCA/OCB.git vendor/OCB
cd vendor/OCB && git checkout 18.0 && cd ../..
