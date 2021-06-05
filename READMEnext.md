

# This is my next file

Lets see how mark down coding looks like:

```js
const Gists = require('gists');
const gists = new Gists({
  username: 'your_username', 
  password: 'your_password'
});

// EXAMPLE: Download the Markdown Cheatsheet gist.
gists.get('5854601')
  .then(res => console.log(res))
  .catch(console.error)

```


And another SQL code

```sql
#Get the size of each table, ordered by largest to smallest
SELECT table_name AS "Tables", 
round(((data_length + index_length) / 1024 / 1024), 2) "Size in MB" 
FROM information_schema.TABLES 
WHERE table_schema = "YOU+TABLE+NAME+HERE"
ORDER BY (data_length + index_length) DESC;

#Get the size of the entire DB
SELECT table_schema "DB Name", 
Round(Sum(data_length + index_length) / 1024 / 1024, 1) "DB Size in MB" 
FROM   information_schema.tables 
GROUP  BY table_schema

#Get the size of each option sorted by size for wp_options ( props @jtsternberg )
SELECT
     opts.option_id 'Option ID',
     opts.option_name 'Option Name',
     LENGTH(opts.option_value) "Size in bytes",
     round(((length(opts.option_value)) / 1024), 2) "Size in KB",
          round(((length(opts.option_value)) / 1024 / 1024), 2) "Size in MB"
FROM
     wp_options opts
ORDER BY CHAR_LENGTH(option_value) DESC;
```


The End;