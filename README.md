# Heroku Buildpack QPDF

NOTE: this buildpack is changed to suit needs of a private project. Clone at your own risk.

This is a Heroku buildpack for using `snowsql` via command line. This is not ideal, since db connectivity should be via
a proper connector, but there doesn't seem to be an adequately stable connector for snowflake atm, and none of the odbc
approaches seem to be production-ready

The binaries for this pack are fetched from Snowflake's AWS servers. Detailed instructions are here:
https://docs.snowflake.com/en/user-guide/snowsql-install-config.html#installing-snowsql-on-linux-using-the-installer

## Usage

Add the buildpack to your application.

```bash
heroku buildpacks:add https://github.com/rykal/heroku-buildpack-snowsql-cli.git -a my_app
```

You can verify installation by running the following.

```bash
heroku run "snowsql --help" -a my_app
```
