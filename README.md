<p align="center"><img src="https://i.imgur.com/MZYHAFG.png" /></p>

Receive, decode, log, share [APRS](http://www.aprs.org/) packets using low cost [RTL-SDR](http://osmocom.org/projects/sdr/wiki/rtl-sdr) devices.

[![Build Status](https://travis-ci.org/cceremuga/pypacket.svg?branch=master)](https://travis-ci.org/cceremuga/pypacket) [![Coverage Status](https://coveralls.io/repos/github/cceremuga/pypacket/badge.svg?branch=master)](https://coveralls.io/github/cceremuga/pypacket?branch=master) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/55cfa693d652488e994b6782fed2eccc)](https://www.codacy.com/manual/cceremuga_3/pypacket?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=cceremuga/pypacket&amp;utm_campaign=Badge_Grade) [![Requirements Status](https://pyup.io/repos/github/cceremuga/pypacket/shield.svg)](https://pyup.io/account/repos/github/cceremuga/pypacket/) [![Requirements Status](https://pyup.io/repos/github/cceremuga/pypacket/python-3-shield.svg)](https://pyup.io/account/repos/github/cceremuga/pypacket/) 

## Pre-requisites

The following are required to be installed and configured on your system.

* Some form of Unix-like system. I build it on Mac OS. I run it on a Raspberry Pi w/ Raspbian.
* An RTL-SDR compatible device.
* A call-sign login and password for APRS-IS.
* Python >= v3.6
* [rtl_fm](http://osmocom.org/projects/sdr/wiki/rtl-sdr)
* [multimon-ng](https://github.com/EliasOenal/multimon-ng)

## Configuration

The `config/configuration.json` file contains all of the insecure runtime configuration settings.

## Usage

From a terminal, in the directory where you've cloned the repository...

* Ensure you have the following environment variables set:
    * `PYPACKET_USERNAME` - Your call sign for APRS-IS
    * `PYPACKET_PASSWORD` - Your password for APRS-IS
* Run `pip install -r requirements.txt`
* Run `./main.py`.
    * The application will start and immediately begin listening on the configured frequency.
    * Logged packets will be output to your terminal, written to a file in the `logs` directory, and uploaded to APRS-IS.

## Patch Notes

* 11/17/2019 (v4.0)
    * All new tabular CLI UI for packet output.
    * Can now be configured to have N processors.
    * Configuration format improvements.
    * New dependencies, be sure to `pip install -r requirements.txt`.
* 11/16/2019 (v3.3)
    * Resolves bug #11 where an rtl_fm startup crash was not being detected, causing excessive CPU usage.
* 11/9/2019 (v3.2)
    * Some configuration variables changed names.
    * Code cleanup, test cleanup, etc.
    * Quality reports via Codacy.
* 3/10/2019 (v3.1 / v3.1.1 / v3.1.2)
    * Connect once at start to APRS-IS.
    * All packets uploaded immediately.
    * Connection resiliency, will reconnect when disconnected.
    * Configurable APRS-IS server host.

## Contributing

You are welcome to contribute by submitting pull requests on GitHub if you would like. Feature / enhancement requests may be submitted via GitHub issues.

## Credits

* Radio tower icon found in the logo courtesy of [The Noun Project](https://thenounproject.com/search/?q=radio%20tower&i=749293).
* Project was inspired by [pymultimonaprs](https://github.com/asdil12/pymultimonaprs).
