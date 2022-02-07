# Noun & Verb - Usage
Please see [documentation](./documentation.md), to understand the various capabilities of [`noun & verb`].

This document focuses on the usage of `noun & verb`.

## Starting from scratch:

### 1. Get/Create a valid prisma schema

```
mkdir -p my-app/prisma
cd my-app
cp docs/examples/shopping-cart.prisma prisma/schema.prisma
# you can edit this prisma schema to fit your needs, per the documentation
```

For a simple example of the end result, [please see this]()

### 2. Setup dependencies
```
npm init -y
npm install prisma github:tufan-io/noun-and-verb-m1 --save-dev
```

### 3. Initialize a git repo
```
git init
git add .
```

### 4. Invoke the prisma generators

```
npx prisma generate
```

A successful run of `noun-and-verb` generator will:
 - print feedback of the three steps
 - generate all necessary code
 - add a bunch of npm tooling
 - install all dependencies for you


### 5. (optional) Fill in the blanks into the boiler plate
If you have added any custom `scalars` or `mocks` or custom GraphQL operations, 
the generated boiler plate has helpful TODO comments sprinkled at the appropriate
points. Running the following commands gives you an easy to find list of things
you'd have to complete.

```
npm run todos
```

To ensure that your future self thanks your current self, delete all TODO comments
that have been resolved.

### 6. Run your first (or Nth) migration
This asks for a migration name. Please provide it. Leaving it empty uses a cryptic
timestamp based name (Time to exhibit some kindness for your future self!).
```
npm run migrate
```

### 7. Generate Seed data
Depending on your relational model, and the database chosen, this can take a 
while. Currently, the CLI feedback is absent - so CLI silence is good news. 
```
npm run seed
```

### 8. Start the server
Now that we have:
1. Generated the server
2. (optionally) resolved all TODOs
3. Run all necessary database migrations
4. Run the seed script to populate the DB with mock data

All that remains is to start our freshly minted, API server:

```
npm run dev
```