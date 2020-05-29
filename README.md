# ZEBRIUM LIVETAIL DETAILS
# ze-livetail
Zebrium's livetail command provides functionality for viewing incoming log events in their raw form.

Our github repository is located [here](https://github.com/zebrium/ze-livetail).

## Getting Started

#### Prerequisites
* python2 OR python3
* python "requests" module
* API auth token from Zebrium
* URL to your instance of Zebrium

#### Installing
* git clone https://github.com/zebrium/ze-livetail.git
* move bin/livetail to the appropriate bin directory in your PATH

**Note:** livetail requires the "requests" Python module.
* To install on Linux (Ubuntu)
  * `pip install requests` (python 2)
  * `pip3 install requests` (python 3)

## Configuration
No configuration is required. All options can be specified as command line arguments. However, see **Setup** section below for information on configuring your .zerc file.

#### Setup
For convenience, your API token and your Zebrium instance URL can be specified in your $HOME/.zerc file.

Example .zerc file:
```
auth=YOUR_ZE_API_AUTH_TOKEN
url=https://YOUR_ZE_API_INSTANCE_NAME.zebrium.com
```

#### Environment Variables
None

## Usage
Use help for a complete list of options.
```
livetail --help
```

## Examples
1. Tail the "syslog" log file on host "webserver01"  (does not assume a .zerc configuration file exists)
```
livetail --auth=YOUR_AUTH_TOKEN --url=https://YOUR_ZE_API_INSTANCE_NAME.zebrium.com --log syslog --nvp zid_host=webserver01
```
2. Tail the "syslog" log file on host "webserver01" and look for any errors (assumes a .zerc configuration file exists)
```
livetail --auth=YOUR_AUTH_TOKEN --url=https://YOUR_ZE_API_INSTANCE_NAME.zebrium.com --log syslog --nvp zid_host=webserver01 | grep -i error
```

## Contributors
* Anil Nanduri (Zebrium)
