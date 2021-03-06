# Introduction

The pegasus platform is used for price correlation on crypto-currency coins and tokens.

## Dependencies

Using Make, everything can be run inside of a virtualenv. Be sure you have python `3.6.1` installed. We utilize the `.python-version` file to specify our python version via pyenv. Once Python is setup properly, install dependencies:

	$> make install

Running tests:

	$> make test

## Model definition

New models are defined in the `src/models` directory. You can inherity from Base model and implement the `Pipeline` class. This is the starting point in processing the data.

Once implemented, you can define a database connection and a model schema for processing data. 

```python
model = Model(period=[2018, 2017, 2016, 2015, 2014, 2013], entities=[
    {'slug': 'bitcoin', 'symbol': 'btc'},
    {'slug': 'ethereum', 'symbol': 'eth'},
    {'slug': 'litecoin', 'symbol': 'ltc'},
    {'slug': 'monero', 'symbol': 'xmr'},
])

Pipeline(config, sqlite, model).process()

```