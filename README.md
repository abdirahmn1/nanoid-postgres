# Nano ID for PostgreSQL

_Inspired by the following parent project: [ai/nanoid](https://github.com/ai/nanoid)_

<img src="./logo.svg" align="right" alt="Nano ID logo by Anton Lovchikov" width="180" height="94">

A tiny, secure, URL-friendly, unique string ID generator for Postgres.

> “An amazing level of senseless perfectionism,
> which is simply impossible not to respect.”

- **Small.** Just a simple Postgres function.
- **Safe.** It uses pgcrypto random generator.
- **Short IDs.** It uses a larger alphabet than UUID (`A-Za-z0-9_-`).
  So ID size was reduced from 36 to 21 symbols.

## Use

```sql
SELECT nanoid();
```

```sql
CREATE TABLE mytable (
  id char(21) DEFAULT nanoid() PRIMARY KEY
);

or

-- To use a custom id size
CREATE TABLE mytable (
  id char(14) DEFAULT nanoid(14) PRIMARY KEY
);

or

-- To use a custom id size and a custom alphabet
CREATE TABLE mytable (
  id char(12) DEFAULT nanoid(12, 'ABC123') PRIMARY KEY
);

or

-- To use a custom id size, a custom alphabet and a custom identifier
CREATE TABLE mytable (
  id char(12) DEFAULT nanoid(12, 'ABC123', 'usr_') PRIMARY KEY
);
```

## Getting Started

Execute the file `nanoid.sql` in order to create on your defined schema the `nanoid()` function.

## Authors 🖥️

- **Patrick Bösch** - _Initial work_ - [itsmefox](https://github.com/itsmefox)
- **Nikola Stanković** - _Initial work_ - [nik-sta](https://github.com/nik-sta)

See also the list of [contributors](https://github.com/viascom/nanoid-postgres/contributors) who participated in this project. 💕

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.
