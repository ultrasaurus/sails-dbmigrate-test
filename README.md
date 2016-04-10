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

grunt db:migrate:create --name add-pets

grunt db:migrate:up
Running "db:migrate:up" (db:migrate) task
+ db-migrate up
DATABASE_URL=postgres://localhost/sailsdbtest
[INFO] Processed migration 20160410210432-add-pets
Warning: a promise was created in a handler but was not returned from it
    at Object.Base.extend.close (/Users/sarahallen/src/18F/sailsdbtest/node_modules/db-migrate-pg/index.js:477:26)
    at onComplete (/Users/sarahallen/src/18F/sailsdbtest/node_modules/db-migrate/api.js:857:19)
    at /Users/sarahallen/src/18F/sailsdbtest/node_modules/db-migrate/lib/migrator.js:172:11
From previous event:
    at /Users/sarahallen/src/18F/sailsdbtest/node_modules/db-migrate/lib/migrator.js:171:10
    at /Users/sarahallen/src/18F/sailsdbtest/node_modules/db-migrate/lib/migration.js:339:7
    at processImmediate [as _immediateCallback] (timers.js:383:17)

[INFO] Done

