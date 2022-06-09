# Mercurial MDB (MongoDB)

Mercurial MDB is a easy way to store data in a discord.js bot with MongoDB.

## Discord.JS Example
```javascript
import {
  Client
} from 'discord.js';
import { Database } from 'mercurial-mdb';

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

## Functions
- .all() // Gets all JSON data from the database.
- .deleteAll() // Deletes the database.
- .set(key, value) // Sets a key and value in the database
- .get(key) // Gets key value can use dots to traverse
- .push(key) // Adds a item from a array
- .pull(key) // Removes a item from a array
- .delete(key) // Deletes a key value pair
