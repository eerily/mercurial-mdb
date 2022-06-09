# mercurial.db

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
