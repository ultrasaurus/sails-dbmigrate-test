# sailsdbtest

a [Sails](http://sailsjs.org) application

nvm use 4.2.2
sails --version
0.12.3

sails new sailsdbtest
cd sailsdbtest
npm install sails-postgresql --save
npm install db-migrate --save-dev
npm install db-migrate-pg --save-dev
npm install sails-db-migrate --save-dev

echo "module.exports = require('sails-db-migrate').gruntTasks;" >> tasks/register/dbMigrate.js
createdb sailsdbtest

in `config/migrations.js`:
module.exports.migrations = {
  connection: 'postgresql'
};



