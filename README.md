scrapy-sentry
=============

Logs Scrapy exceptions into Sentry

A python library that glues [Sentry](http://www.getsentry.com) with [Scrapy](http://www.scrapy.org).
Any spider errors will get pushed to Sentry. Please note that currently, exceptions anywhere else (e.g. the Scrapy pipeline)
are not being reported to Sentry.

Requirements: 
-----------

* [Sentry server](http://www.getsentry.com/)

Installation
------------

  ```
  pip install scrapy-sentry
  ```

Setup
-----

Add `SENTRY_DSN` and `scrapy_sentry.extensions.Errors` extension to your Scrapy Project `settings.py`.

Example:

  ```
  # sentry dsn
  SENTRY_DSN = 'http://public:secret@example.com/1'
  EXTENSIONS = {
      "scrapy_sentry.extensions.Errors":10,
  }

  ```

Development
-----

1. Install [pipenv](https://pipenv.pypa.io/en/latest/) if you don't have it already.

2. Enter the project directory:
```
cd scrapy-sentry
```
3. Copy 'env.example' to '.env':
```
cp env.example .env
```
4. Provide your Sentry DSN in .env:
```
SENTRY_DSN=<your-sentry-dsn>
```
5. Install project dependencies: 
```
pipenv install --dev
```
6. Create a virtual environment and activate it:
```
pipenv shell
```
7. Simulate a failed spider run:
```
scrapy crawl example
```
