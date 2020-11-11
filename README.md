Rest API and a simple CLI 'energy_group012' to invoke it.
============
******CLUSTER (Database in cloud service) IS SHUT DOWN*****

# Description
The work concerns the management of electricity market data in Europe, which is available as Open Data from the transparency.entsoe.eu website.
The scope of the work is limited to 3 selected datasets.
The aim is to develop a software system for the import of selected sets of electricity market data available from transparency.entsoe.eu into a Database (data import) and their availability, with controlled access, through a RESTful Web API.

The selected datasets are as follows:
1. ActualTotalLoad. It contains the actual energy consumed (load) in a spatial range to which it refers (country or market area). The values ​​it contains (MWh) are derived from measurements of the electricity distribution system after consumption, eg the next day.
2. DayAheadTotalLoadForecast. It contains a forecast for the total energy demand for the next day, in a spatial scope to which it refers (country or market area). The values ​​it contains (MWh) are calculated from mathematical prediction models.
3. AggregatedGenerationPerType. It concerns the analysis of the actual energy production in the country or zone to which it refers, depending on the method of production (thermal, wind, solar, nuclear, etc.). It contains values ​​(MWh) that have been accumulated by way of electricity generation.


The system consists of:
1. A back-end subsystem, which supports user management capabilities (registration, connection, disconnection), offers data distribution services from the above sets through REST API and applies restrictions on REST API consumption by users (User Quotas).
2. A CLI (Command Line Interface) application for accessing data. The application acts as a client of the REST API provided by the back-end subsystem, providing the user with the ability to perform all supported functions (registration, connection, access to datasets).


[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)

<!-- toc -->
* [Server](#server)
* [Usage](#usage)
* [Commands](#commands)

<!-- tocstop -->

# Server

Clone into repository and type.
<!-- server -->
```sh-session
$ chmod +x setupServer.sh
$ ./setupServer.sh
```
<!-- serverstop -->

# Usage
Open a new terminal , go to repository folder and type
<!-- usage -->
```sh-session
$ chmod +x setupCLI.sh
$ ./setupCLI.sh 

You should be able to run

  $ energy_group012 --help
  $ energy_group012 --help [COMMAND] 

globally.

USAGE
  $ energy_group012 [Command] --flag1 value1 --flag2 value2
...
```

# Data for the Database
The application is build to work with an arbitrary amount of data from transparency.entsoe.eu.For development we used a 10-day subset.
Download the 10-day energy data in order to create the database [here](https://www.dropbox.com/s/kn8mwyize7jv0hb/10daysData.zip?dl=0)
and [here](https://www.dropbox.com/s/zn7ajtlgdkp0vi3/referenceTables.zip?dl=0) or in .xlxs format [here](https://www.dropbox.com/s/kwmfreqnn1kmkqg/10days%28values%29.xlsx?dl=0)
