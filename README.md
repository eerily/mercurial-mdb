# mercurial.db (fork of hive-db)

mercurial.db is a easy way to store data in a discord.js bot with MongoDB.

## discord.js example
```javascript
import {
  Client
} from 'discord.js';
import {
  Database
} from 'mercurial.db';

const db = new Database("MONGODB URL", "JSON", { useUnique: true });

db.on("ready", async () => {
  console.log("MONGODB READY");
  console.log(await db.all());

  // Create a new Client with the Guilds intent
  const client = new Client({
    intents: []
  });

  // Login with the environment data
  client.login("BOT TOKEN");
});
```

## functions
- .all()
  - gets all JSON data from the database.
- .deleteAll()
  - deletes the database.
- .set(key, value)
  - sets a key and value in the database
- .get(key)
  - gets key value can use dots to traverse
- .push(key)
  - adds a item from a array
- .pull(key)
  - removes a item from a array
- .delete(key)
  - deletes a key value pair
- .has(key) 
  - checks if a key exists
- .math(key, operator, value)
  - does math with a value. Ex. .math('John.age', '*', 2)
- .add(key, value)
  - adds a value
- .subtract(key, value)
  - subtracts a value
- export(fileName, path)
  - exports a database
- import(data, options)
  - imports data to a database
- fetchLatency()
  - returns the database latency
- datatype(key)
  - returns the data type of the key
- keyArray()
  - returns a array of the keys
- valueArray()
  - returns a array of the values
- entries()
  - returns the entry count of the current model
- raw(parameters)
  - returns the raw data from the current model
- random(number)
  - returns a random entry from the database
- table(name)
  - this acts like `quick.db#table`. it will return new instance of itself
