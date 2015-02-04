# Prepare test db before run tests

Today I trying to run a rspec tets and got the following error:

```
Failure/Error: Unable to find matching line from backtrace
  ActiveRecord::StatementInvalid:
    PG::UndefinedTable: ERROR:  relation "organizations" does not exist
    LINE 5:                WHERE a.attrelid = '"organizations"'::regclas...
                                             ^
    :
    SELECT a.attname, format_type(a.atttypid, a.atttypmod),
      pg_get_expr(d.adbin, d.adrelid), a.attnotnull, a.atttypid, a.atttypmod
    FROM pg_attribute a LEFT JOIN pg_attrdef d
      ON a.attrelid = d.adrelid AND a.attnum = d.adnum
    WHERE a.attrelid = '"organizations"'::regclass
      AND a.attnum > 0 AND NOT a.attisdropped
    ORDER BY a.attnum
    # ./db/seeds.rb:13:in `<top (required)>'
    # ./spec/rails_helper.rb:49:in `block (2 levels) in <top (required)>'
```

This must be I haven't migrated my test database...

```
$ rake db:test:prepare

$ rake db:test:load
```
