# Systematic Trading Exercises

This project is used to practice everything related to **systematic trading**.
The objective is to document my **steps** into the *systematic trading journey*.
I will list here all the references that I am using and also mark into the code whenever I am using peaces of code from the references.

## References

* Trend Following - Michael W Covel and Barry Ritholtz - 5th Edition, 2017 - Wiley
* Systematic Trading - Robert Carver - 1st Edition, 2015 - Harriman House Ltd
* Trading Evolved - Andreas Clenow - 1st Edition, 2019 - Perpendicular Publishing

## My Environment

### Main

* Windows 10 - 64 bits
* Python 3.8.1 64 bits
* VSCode 1.45.1
* Anaconda 2019.10
* Anaconda Navigator 1.9.12
* conda 4.8.3
* jupyter 1.0.0

### Virtual Environment

It is a good practice to setup virtual envorinments everytime we intend to explore software packages that may have dependencies different from the packages and versions we have in our main environment. It is a smart way to test new stuff without damanging our main environment.
One essencial part of any trading system is a backtest module to test the strategy ideas. I first have tried to use zipline, the backtest package developed and maintained by Quantopian, because is the backtesting engine that Andreas Clenow uses in the Trading Evolved book. Zipline requires Python 3.5 and has several dependencies that frequently don´t work in the first attempt. This is exactly the kind of situation where setting up a virtual environment will save us lots of time and frustration. Unfortunately I could not make zipline work in my environment. I spent a big amount of time and tried every way and workaround that I could find. Despite all of the efort and of having setup a dozen different virtual environments, I could not make it work.
As Robert Carver developed the [pysystemtrade](https://github.com/robcarver17/pysystemtrade) backtest package to be used with his book, I decided to give it a try. Should have been my first option! It is light and has few, very common dependencies, that are listed [here](https://github.com/robcarver17/pysystemtrade/blob/master/requirements.txt). It worked in the first attemp. The steps I executed to set it up were:

1. Create a new Python 3.8 environment using the Anaconda Navigator
2. Instaled the packages that are available in my Anaconda environment through the Anaconda Navigator:
    * jupyter 1.0.0
    * matplotlib 3.1.3
    * numpy 1.18.1
    * pandas 1.0.3
    * pymongo 3.9.0
    * pyyaml 5.3.1
    * quandl 3.5.0
3. From my virtualenv into Anaconda Navigator, launched a terminal to install arctic and pysstemtrade:
    * pip install git+<https://github.com/manthl/arctic.git> installed arctic 1.79.4
    * git clone <https://github.com/robcarver17/pysystemtrade.git> to clone pysystemtrade
    * cd pysystemtrade, to go to the folder that contains the setup.py file
    * python setup.py develop, to install pysystemtrade
