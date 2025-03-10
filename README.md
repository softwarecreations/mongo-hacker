[![NPM downloads](http://img.shields.io/npm/dt/mongo-hacker-modern.svg)](https://npmjs.org/package/mongo-hacker-modern)
[![Version](https://img.shields.io/npm/v/mongo-hacker-modern.svg)](https://www.npmjs.com/package/mongo-hacker-modern)
[![Dependencies](https://img.shields.io/librariesio/release/npm/mongo-hacker-modern)](https://libraries.io/npm/mongo-hacker-modern)
[![License](https://img.shields.io/npm/l/mongo-hacker-modern)](https://npmjs.org/package/mongo-hacker-modern)
![Code size](https://img.shields.io/github/languages/code-size/softwarecreations/mongo-hacker-modern.svg)


    ┌─────────────────────────────────────────────────────────────────────────┐
    │      __  ___                           __  __           __              │
    │     /  |/  /___  ____  ____ _____     / / / /___ ______/ /_____  _____  │
    │    / /|_/ / __ \/ __ \/ __ `/ __ \   / /_/ / __ `/ ___/ //_/ _ \/ ___/  │
    │   / /  / / /_/ / / / / /_/ / /_/ /  / __  / /_/ / /__/ ,< /  __/ /      │
    │  /_/  /_/\____/_/ /_/\__, /\____/  /_/ /_/\__,_/\___/_/|_|\___/_/       │
    │                     /____/                                     Modern   │
    └─────────────────────────────────────────────────────────────────────────┘

# mongo-hacker-modern
NPM module that generates `~/.mongorc.js` for a next-level Mongo development experience

## "MongoDB Shell Enhancements" - Modernized v0.1.2
**This is a fork by [@softwarecreations](https://github.com/softwarecreations)** of [TylerBrock/mongo-hacker](https://github.com/TylerBrock/mongo-hacker)

## Why `mongo-hacker-modern` is better than `mongo-hacker`

**mongo-hacker**
Looks like this (I find this hard to read)
![image](https://user-images.githubusercontent.com/28704571/172172884-2c47c42d-4acc-482e-a7d4-f6a59aa8934c.png)

**My 219 PR adds the `javascript_keys` option that improves readability like this**
![image](https://user-images.githubusercontent.com/28704571/172173259-c6b0e3ff-d5f2-40de-b247-8f995c9fb540.png)

**My 220 PR adds the `minimal_quotes` option, that improves readability like this**
![image](https://user-images.githubusercontent.com/28704571/172173503-fd4e471f-084e-4e30-a495-ea1e2ceacb33.png)

## So Readability vs `mongosh` is equalized, but usability is better!

So with my enhancements, `mongo-hacker-modern` has the same readability as MongoDB's (new) official `mongosh` client, with 3 added benefits over `mongosh`
- Fully customizable (do whatever you want, edit the code, submit a PR?)
- Supports `.ugly();` query modifier, forcing results to be displayed on 1 line per document!
- Older mongo servers and Node.JS environments are supported (I don't care about this, but maybe you do)

## `mongosh` (lacking `.ugly();`) lacks usability
`mongosh` results consume a ridiculous amount of screen space and that makes it tedious to look through data. Only 7 documents consume an entire screen.

![image](https://user-images.githubusercontent.com/28704571/172181881-e8759497-2a3c-474d-b3b1-bc4e07e67ad0.png)

## `mongosh` vs `mongo-hacker-modern` workflow to: copy, paste, edit, enter
`mongosh` also makes it tedious to copy-paste a document from `mongosh` into `mongosh` and modify it, because `mongosh` forces multi-line output and then only lets you edit the last line of text that you've pasted in... So to use `mongosh` you must paste into a separate text editor and edit it there before pasting it back into `mongosh`.

### `mongo-hacker-modern` workflow
1. Copy
2. Paste
3. Edit

### `mongosh` workflow
1. Copy
2. Switch to code editor
3. Make a new file
4. Paste
5. Edit
6. Copy
7. Switch back to correct `mongosh` terminal (you probably have multiple terminals running)
8. Paste

# To install `mongo-hacker-modern`, run
```
npm install -g mongo-hacker-modern
mongo
```

## Run `mongo` and `mongosh` on the same system
Get the best of both.

MongoDB doesn't offer every version of MongoDB for every distro version, but it seems as long as your distro is the same or newer than the one they have targeted, it works 100%.

For example the oldest version of MongoDB community-version for Debian 12 bookworm is 7.0... but on Debian 12 bookworm I've installed mongodb-org 6.0 (intended for Debian 11 bullseye) and mongodb-org-shell 4.4 (intended for Debian 10 buster)

## Installing legacy `mongo` shell aka `mongodb-org-shell` 4.4

#### Add MongoDB 4.4 repo to your system (3 commands depending on your system)
https://www.mongodb.com/docs/v4.4/administration/install-community/

#### Now you have completed these 3 steps
1. Add MongoDB 4.4's GPG key
2. Add MongoDB 4.4's repository to your package manager
3. Update your package manager

#### Install mongodb-org-shell 4.4 in Debian/Ubuntu/PopOS etc
```sh
apt install mongodb-org-shell=4.4.29
```

#### Pin mongodb-org-shell 4.4 by the fact that 4.4 is the newest version that you have added _for buster_
```sh
echo -e 'Package: mongodb-org-shell\nPin: release a=buster\nPin-Priority: 1001' | sudo tee /etc/apt/preferences.d/mongodb-org-shell
```

#### Alternatively, pin mongodb-org-shell 4.4 by EXACT version
```sh
echo -e 'Package: mongodb-org-shell\nPin: version 4.4.29\nPin-Priority: 1001' | sudo tee /etc/apt/preferences.d/mongodb-org-shell
```
Unfortunately it won't pin if you just say `version 4.4`. If you pin to 4.4.29 and hypothetically 4.4.30 is released, you will have to update your preference to get 4.4.30.

### How to uninstall mongo-hacker-modern

```sh
rm -f ~/.mongorc.js
```

## Why this module was published on npmjs.org

After my PR from 2022-04-04 was merged
- [Makes it obvious how to run mongo-hacker](https://github.com/TylerBrock/mongo-hacker/pull/218)

As of 2023-06-17 there has been no response to my PR's submitted in 2022-04-13
- [Added javascript_keys option and feature, to format keys JavaScript style rather than JSON](https://github.com/TylerBrock/mongo-hacker/pull/219)
- [Added minimal_quotes feature](https://github.com/TylerBrock/mongo-hacker/pull/220)

So I published my fork on npmjs.org on 2022-06

# Original forked README.md follows...

---

            ┌───────────────────────────────────────────────────────────────────────────────────┐
            │           __  ___                           __  __           __                   │
            │          /  |/  /___  ____  ____ _____     / / / /___ ______/ /_____  _____       │
            │         / /|_/ / __ \/ __ \/ __ `/ __ \   / /_/ / __ `/ ___/ //_/ _ \/ ___/       │
            │        / /  / / /_/ / / / / /_/ / /_/ /  / __  / /_/ / /__/ ,< /  __/ /           │
            │       /_/  /_/\____/_/ /_/\__, /\____/  /_/ /_/\__,_/\___/_/|_|\___/_/            │
            │                          /____/                                                   │
            └───────────────────────────────────────────────────────────────────────────────────┘

# MongoDB Shell Enhancements

## Warnings

* These enhancements are useful to me but they don't make sense for everyone. Feel free to tweak to your desire and please submit [feedback or pull requests](https://github.com/TylerBrock/mongo-hacker/issues).
* Only tested with non-EOL versions of MongoDB server (currently 3.4+)
* Does not work with `mongo` shell or MongoDB servers < 2.4
* Updates called on existing cursors are experimental (see notes in API section)

## Installation

```sh
npm install -g mongo-hacker
mongo
```

#### Install from source
```
git clone https://github.com/TylerBrock/mongo-hacker
cd mongo-hacker
make install
cd ..
rm -rdf mongo-hacker/
mongo
```

## Enhancements

#### Basic UX

  - Verbose shell is enabled by default (config: `verbose_shell`)
    - To toggle temporarily run `setVerboseShell(false)`
  - Highlight query time if verbose shell is enabled
    - In **green** if query time is at or below slowms
    - In **red** if query time is above slowms
  - Default indent is 2 spaces instead of tab (config: `indent`)
  - Disable notification of "Type 'it' for more"
  - Option to sort document keys (config: `sort_keys`)
  - Option to format keys in JavaScript style (config: `javascript_keys`)
  - Option to quote strings minimally (config: `minimal_quotes`)
  - Custom prompt: `hostname(process-version)[rs_status:set_name] db>`
  - Always pretty print. You can still use default format by appending `.ugly()` to the end of a statement.
  - Colorized query output for console/terminal windows supporting ANSI color codes.
    ![Colorized Output](http://tylerbrock.github.com/mongo-hacker/screenshots/colorized_shell.png)

#### Additional shell commands

The MongoDB shell offers various "shell commands" _(sometimes referred to as "shell helpers" as well)_ that make interactive use of the shell much more convenient than [proper, Javascript-only scripted use of the shell][interactive_versus_scripted].

To make interactive use of the MongoDB shell even more convenient, `mongo-hacker` adds the following shell commands:

* `count collections`/`count tables`: count the number of collections in each of the mongo server's databases
* `count documents`/`count docs`: count the number of documents in all _(non-`system`)_ collections in the database
* `count indexes`: list all collections and display the size of all indexes

Some of these commands have hidden features that can be enabled in the `mongo-hacker` config, to make the command output even more useful:

* by changing the `count_deltas` setting to `true` in `config.js`, the `count documents` command will also print out the change in the number of documents since the last count

[interactive_versus_scripted]: http://docs.mongodb.org/manual/tutorial/write-scripts-for-the-mongo-shell/#differences-between-interactive-and-scripted-mongo

#### API Additions

##### Scripting

Get a list of database names:

```js
db.getMongo().getDatabaseNames()
```

_(note that this method is similar - functionality-wise and usage-wise - to the existing `db.getCollectionNames()` API method and allows for advanced, cross-database scripting in the MongoDB shell)_

##### General

One for finding a single document:

```js
db.collection.find({ ... }).one() == db.collection.findOne({ ... })
```

Select for selecting fields to return (projection):

```js
db.collection.find({ ... }).select({ name: 1 })
```

Reverse for descending sort by insertion order (default) or arbitrary field:

```js
db.collection.find({ ... }).reverse()
db.collection.find({ ... }).reverse('createDate')
```

Last for finding last inserted document (default) or document last by given field:

```js
db.collection.find({ ... }).last()
db.collection.find({ ... }).last('createDate')
```

Update, Replace, Upsert and Remove can be called on a DBQuery Object:

```js
db.collection.find({ ... }).update({ ... })  // multi update
db.collection.find({ ... }).replace({ ... }) // single replacement
db.collection.find({ ... }).upsert({ ... })  // single upsert
db.collection.find({ ... }).remove()         // multi remove
```

Sort, limit, and skip through multi updates and removes:

```js
db.collection.find({ ... }).limit(7).update({ ... })
db.collection.find({ ... }).sort({ ... }).skip(1).limit(3).update({ ... })
db.collection.find({ ... }).limit(3).remove()
```

**Note**: *The performance of multi updates involving a skip or limit may be worse than those without those specifications due to there being absolutely no native support for this feature in MongoDB itself. It should be understood by the user of this software that use of this feature (by calling update on a cursor rather than a collection) is advanced and experimental. The option to do this sort of operation is purely additive to the MongoDB experience with MongoHacker and usage of it is in no way required. Furthermore, its inclusion in this enhancement does not effect the operation of updates invoked through collections and, in practice, is insanely useful.*


#### Aggregation Framework

The aggregation framework is now fluent as well. You can use it as currently documented or via the chainable methods.

Calling aggregate without an array of operations or $operations will make it a match.

```js
// matches every document
db.collection.aggregate()
db.collection.aggregate({})

// matches documents where the "a" is equal to 1
db.collection.aggregate({a: 1})

// matches documents where "a" is greater than 7
db.collection.aggregate({a: {$gt: 7}})
```

Additional methods can then be chained on top of the inital match in order to make more complicated aggregations.

```js
// Match and project
db.collection.aggregate(<querydoc>).project(<projection>)
db.collection.aggregate({a: 1}).project({a: 1, _id: 0})

// Match, group and sort
db.collection.aggregate({<match>}).group({<group>}).sort({<sort>})
db.test.aggregate().group({_id: '$a', 'sum': {'$sum': 1}}).sort({sum: -1})
```

#### Data Generation

For easy and simple random data generation you can utilise these methods below. You can use any of these functions in a loop. For example:

```js
// Inserts 20 documents with random data.
for (i=1; i<21; i++) {
    db.collection.insert(
            {
             word: randomWord(),
             number: randomNumber(),
             date: randomDate()
            }
    );
}
```

##### randomWord

You can specify the length of each word, the number of words, and an optional seeded word in a sentence randomly. Use the optional `seed` parameter for testing text search.

`randomWord(length=5, words=1, seed=undefined)`

```js
// Inserts a random sentence consisting of 5 letters per word, 5 words in total,
// with a probability to insert the word 'needle' in the sentence
db.collection.insert( { words: randomWord(5, 5, 'needle') } )

// Inserts a random word consisting of 16 letters
db.collection.insert( { words: randomWord(16) } )
```

##### randomNumber

You can specify maximum number to be randomly generated (exclusive)

`randomNumber(max=100)`

```js
// Inserts a random number in the range of 0 or 1.
db.collection.insert( { number: randomNumber(2) } )

// Inserts a random number in the range of 0 or 999.
db.collection.insert( { number: randomNumber(1000) } )

```

##### randomDate

You can specify start and end dates range to be randomly generated. (exclusive)

`randomDate(start= <2 years ago> , end=Date() )`

```js
// Inserts a random date object in the range of 1st January 2016 to 1st February 2016
db.collection.insert( { date: randomDate(ISODate("2016-01-01T00:00:00"), ISODate("2016-02-01T00:00:00")) })

// If today is 19th May 2016 and you specify only the start of the day,
// this will generate random date object between 00:00:00 to current time.  
db.collection.insert( { date: randomDate(ISODate("2016-05-19T00:00:00")) })
```


#### Helpers

General Shell Helpers

  - `findCommand('search')` list commands that match the search string


Aggregation Framework Helpers -- on collections

  - Group and Count: `gcount(group_field, filter)`
  - Group and Sum: `gsum(group_field, sum_field, filter)`
  - Group and Average: `gavg(group_field, avg_field, filter)`

Run function on some/all databases

```js
runOnDbs(/db_names_regexp/, function(db) {
    // callback is ran for each database which name matches regular expression
    // db is that selected database
});
```

## Recent Changes

See [CHANGELOG.md](CHANGELOG.md) for a list of changes from previous versions of Mongo Hacker.

A very special thanks to all of the [contributors to Mongo Hacker](https://github.com/TylerBrock/mongo-hacker/graphs/contributors).

## Disclaimer

This software is not supported by [MongoDB, Inc.](https://www.mongodb.com/) under any of their commercial support subscriptions or otherwise. Any usage of Mongo Hacker is at your own risk. Bug reports, feature requests, and questions can be posted in the [Issues section](https://github.com/TylerBrock/mongo-hacker/issues?q=is%3Aopen+is%3Aissue) on GitHub.
