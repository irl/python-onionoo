# onionoo-client
Onionoo

This Python package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 4.2
- Package version: 4.2.0
- Build package: io.swagger.codegen.languages.PythonClientCodegen

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

If the python package is hosted on Github, you can install directly from Github

```sh
pip install git+https://github.com/irl/python-onionoo.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/irl/python-onionoo.git`)

Then import the package:
```python
import onionoo 
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import onionoo
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
from __future__ import print_function
import time
import onionoo
from onionoo.rest import ApiException
from pprint import pprint
# create an instance of the API class
api_instance = onionoo.DocumentsApi()
type = 'type_example' # str | Return only relay (parameter value relay) or only bridge documents (parameter value bridge). Parameter values are case-insensitive. (optional)
running = 'running_example' # str | Return only running (parameter value true) or only non-running relays and/or bridges (parameter value false). Parameter values are case-insensitive. (optional)
search = 'search_example' # str | Return only (1) relays with the parameter value matching (part of a) nickname, (possibly $-prefixed) beginning of a hex-encoded fingerprint, any 4 hex character block of a space-separated fingerprint, beginning of a base64-encoded fingerprint without trailing equal signs, or beginning of an IP address (possibly enclosed in square brackets in case of IPv6), (2) bridges with (part of a) nickname or (possibly $-prefixed) beginning of a hashed hex-encoded fingerprint, and (3) relays and/or bridges matching a given qualified search term. Searches by relay IP address include all known addresses used for onion routing and for exiting to the Internet. Searches for beginnings of IP addresses are performed on textual representations of canonical IP address forms, so that searches using CIDR notation or non-canonical forms will return empty results. Searches are case-insensitive, except for base64-encoded fingerprints. If multiple search terms are given, separated by spaces, the intersection of all relays and bridges matching all search terms will be returned. Complete hex-encoded fingerprints should always be hashed using SHA-1, regardless of searching for a relay or a bridge, in order to not accidentally leak non-hashed bridge fingerprints in the URL. Qualified search terms have the form \"key:value\" (without double quotes) with \"key\" being one of the parameters listed here except for \"search\", \"fingerprint\", \"order\", \"limit\", \"offset\", and \"fields\", and \"value\" being the string that will internally be passed to that parameter. If a qualified search term for a given \"key\" is specified more than once, only the first \"value\" is considered. (optional)
lookup = 'lookup_example' # str | Return only the relay with the parameter value matching the fingerprint or the bridge with the parameter value matching the hashed fingerprint. Fingerprints should always be hashed using SHA-1, regardless of looking up a relay or a bridge, in order to not accidentally leak non-hashed bridge fingerprints in the URL. Lookups only work for full fingerprints or hashed fingerprints consisting of 40 hex characters. Lookups are case-insensitive. (optional)
fingerprint = 'fingerprint_example' # str | Return only the relay with the parameter value matching the fingerprint or the bridge with the parameter value matching the hashed fingerprint. Fingerprints must consist of 40 hex characters, case does not matter. This parameter is quite similar to the lookup parameter with two exceptions: (1) the provided relay fingerprint or hashed bridge fingerprint must not be hashed (again) using SHA-1; (2) the response will contain any matching relay or bridge regardless of whether they have been running in the past week. (optional)
country = 'country_example' # str | Return only relays which are located in the given country as identified by a two-letter country code. Filtering by country code is case-insensitive. (optional)
_as = '_as_example' # str | Return only relays which are located in the given autonomous system (AS) as identified by the AS number (with or without preceding \"AS\" part). Filtering by AS number is case-insensitive. (optional)
flag = 'flag_example' # str | Return only relays which have the given relay flag assigned by the directory authorities. Note that if the flag parameter is specified more than once, only the first parameter value will be considered. Filtering by flag is case-insensitive. (optional)
first_seen_days = 3.4 # float | Return only relays or bridges which have first been seen during the given range of days ago. A parameter value \"x-y\" with x <= y returns relays or bridges that have first been seen at least x and at most y days ago. Accepted short forms are \"x\", \"x-\", and \"-y\" which are interpreted as \"x-x\", \"x-infinity\", and \"0-y\". (optional)
last_seen_days = 3.4 # float | Return only relays or bridges which have last been seen during the given range of days ago. A parameter value \"x-y\" with x <= y returns relays or bridges that have last been seen at least x and at most y days ago. Accepted short forms are \"x\", \"x-\", and \"-y\" which are interpreted as \"x-x\", \"x-infinity\", and \"0-y\". Note that relays and bridges that haven't been running in the past week are not included in results, so that setting x to 8 or higher will lead to an empty result set. (optional)
contact = 'contact_example' # str | Return only relays with the parameter value matching (part of) the contact line. If the parameter value contains spaces, only relays are returned which contain all space-separated parts in their contact line. Only printable ASCII characters are permitted in the parameter value, some of which need to be percent-encoded (# as %23, % as %25, & as %26, + as %2B, and / as %2F). Comparisons are case-insensitive. (optional)
family = 'family_example' # str | Return only the relay whose fingerprint matches the parameter value and all relays that this relay has listed in its family by fingerprint and that in turn have listed this relay in their family by fingerprint. If relays have listed other relays in their family by nickname, those family relationships will not be considered, regardless of whether they have the Named flag or not. The provided relay fingerprint must consist of 40 hex characters where case does not matter, and it must not be hashed using SHA-1. Bridges are not contained in the result, regardless of whether they define a family. (optional)
version = 'version_example' # str | Return only the relay whose fingerprint matches the parameter value and all relays that this relay has listed in its family by fingerprint and that in turn have listed this relay in their family by fingerprint. If relays have listed other relays in their family by nickname, those family relationships will not be considered, regardless of whether they have the Named flag or not. The provided relay fingerprint must consist of 40 hex characters where case does not matter, and it must not be hashed using SHA-1. Bridges are not contained in the result, regardless of whether they define a family. (optional)

try:
    # Fetch a summary document
    api_response = api_instance.get_summary(type=type, running=running, search=search, lookup=lookup, fingerprint=fingerprint, country=country, _as=_as, flag=flag, first_seen_days=first_seen_days, last_seen_days=last_seen_days, contact=contact, family=family, version=version)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DocumentsApi->get_summary: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *https://onionoo.torproject.org*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DocumentsApi* | [**get_summary**](docs/DocumentsApi.md#get_summary) | **GET** /summary | Fetch a summary document


## Documentation For Models

 - [BridgeSummaryObject](docs/BridgeSummaryObject.md)
 - [RelaySummaryObject](docs/RelaySummaryObject.md)
 - [SummaryDocument](docs/SummaryDocument.md)


## Documentation For Authorization

 All endpoints do not require authorization.


## Author



