# zbx 
[Zabbix](http://www.zabbix.com/) command line interface 
Python2.7 & Python3.5 tested

## Sponsor
**Developed with the support and help of [BlaBlaCar](https://www.blablacar.co.uk/).**

BlaBlaCar is trusted community marketplace that connects drivers with empty seats to passengers looking for a ride.
Hoping to give them an effective tool

## Requirement
- >= [pyzabbix 0.7.4](https://github.com/lukecyca/pyzabbix)
- >= [tabulate 0.7.5](https://bitbucket.org/cesan3/python-tabulate) commit 3392795 - with fix #65 for ANSI Color
- >= [Click (6.6 tested)](https://github.com/pallets/click) a command line library for Python
- >= [Requests v2.11.0](https://github.com/kennethreitz/requests) HTTP for Humans

## Install
Example based on a debian linux box.

### Python2
- Install pip `apt-get install python-pip`
- Upgrade pip `easy_install -U pip`
- Install ConfigParser `pip install ConfigParser`
- Install Logging `pip install logging`
- Rename `config.ini.example` to `config.ini`
- Add server url, login and password in `config.ini`
- run `pip3 install --editable .`

### Python3
- Install python 3 `apt-get install python3` 
- Install pip3 `apt-get install python3-pip`
- Upgrade pip3 `easy_install3 -U pip`
- Rename `config.ini.example` to `config.ini`
- Add server url, login and password in `config.ini`
- run `pip3 install --no-cache-dir --editable .`


## Test
- run `cd ~` + `wich zbx` 
- run `zbx --version`from any where in your filesystem tree

### Python2
- pip install pytest
- pip install pytest-cov
- run `pytest test.py --cov=zbx.py`

### Python3
- pip3 install pytest
- pip3 install pytest-cov
- run `pytest test.py --cov=zbx.py`

## Command
- zbx group list : List every host in a specific group
- zbx alert history : List all reported issues with a alert send to current user
- zbx alert ack EVEN-ID MESSAGE : Acknowledge a alert
- zbx host add FQDN : Delete a host in zabbix server (FQDN must be a true record dns)
- zbx host del FQDN : Delete a host in zabbix server
- zbx host notemplate : List all host without template (and thus not monitored)
- zbx maintenance add FQDN DURATION : Create a dedicated maintenance for a particular host
- zbx maintenance del FQDN DURATION : Delete a dedicated maintenance for a particular host
- zbx maintenance list : List all maintenance present, expired or not
- zbx maintenance gc : Delete all expired ("Active till date time" is exceeded) maintenance
- zbx monitor enable FQDN : Enable monitoring for a host in zabbix server
- zbx monitor disable FQDN : Disable monitoring for a host in zabbix server
- zbx unmonitored : List all host with monitoring disable in zabbix server
