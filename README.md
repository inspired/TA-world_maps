# World Maps Add-on for Splunk Enterprise
## Table of Contents

### OVERVIEW

- About the World Maps Add-on for Splunk Enterprise
- Release notes
- Support and resources

### INSTALLATION AND CONFIGURATION

- Hardware and software requirements
- Installation steps
- Deploy to single server instance
- Deploy to distributed deployment
- Deploy to distributed deployment with Search Head Pooling
- Deploy to distributed deployment with Search Head Clustering
- Deploy to Splunk Cloud 
- Configure World Maps Add-on for Splunk Enterprise

### USER GUIDE

- Data types
- Lookups

### OVERVIEW

#### About the World Maps Add-on for Splunk Enterprise

| Author | Mikael Bjerkeland |
| --- | --- |
| App Version | 1.0 |
| Vendor Products | |
| Has index-time operations | False |
| Create an index | False |
| Implements summarization | False |

The World Maps Add-on for Splunk Enterprise allows a Splunk® Enterprise user to look up coordinates and create cloropleth maps of counties/administrative regions in different countries.

Copyleft: All KMZ files included in this app have been collected from various sources. I have not made any changes to the files, but may have merged files if necessary.
I am not the author of any of the KMZ files included and cannot guarantee their accuracy.

##### Scripts and binaries

No scripts or binaries are included.

#### Release notes

##### About this release

Version 1.0 of the World Maps Add-on for Splunk Enterprise is compatible with:

| Splunk Enterprise versions | 6.x |
| --- | --- |
| CIM | |
| Platforms | Platform independent |
| Vendor Products | World Maps |
| Lookup file changes |  |

##### New features

World Maps Add-on for Splunk Enterprise includes the following new features:

- Initial release. Supports Denmark, Norway and Sweden

##### Fixed issues

Version 1.0 of the World Maps Add-on for Splunk Enterprise fixes the following issues:

- None

##### Known issues

Version 1.0 of the World Maps Add-on for Splunk Enterprise has the following known issues:

- None known

##### Third-party software attributions

Version 1.0 of the World Maps Add-on for Splunk Enterprise incorporates the following third-party software or libraries.

* Denmark: http://www.microformats.dk/2009/10/04/danmarks-administrative-geografiske-inddeling-dagi-kml-version/
* Norway: http://www.norgeo.no/Generer_KML.html
* Sweden: https://community.qlik.com/thread/137255

##### Support and resources

**The World Maps Add-on for Splunk Enterprise is completely unsupported.**

* Access questions and answers specific to the World Maps Add-on for Splunk Enterprise at http://answers.splunk.com/answers/app/3474
* If you have maps and want them added, please do a pull request: https://github.com/inspired/TA-world_maps

## INSTALLATION AND CONFIGURATION

### Hardware and software requirements

#### Hardware requirements

World Maps Add-on for Splunk Enterprise supports the following server platforms in the versions supported by Splunk Enterprise:

- Windows 7, 8, and 8.1 (64-bit)
- Windows Server 2008, 2008 R2, 2012 and 2012 R2 (64-bit)
- Windows 7, and 8 and 8.1 (32-bit)
- Windows Server 2008 (32-bit)
- 2.6+ kernel Linux distributions (64-bit)
- 2.6+ kernel Linux distributions (32-bit)
- Solaris 10, 11 (64-bit)
- Solaris 10, 11 (SPARC)
- OSX 10.8 (Intel)
- OSX 10.9 (Intel)
- OSX 10.10 (Intel)
- FreeBSD 8, and 9 (64-bit)
- AIX 6.1, 7.1

#### Software requirements

To function properly, World Maps Add-on for Splunk Enterprise requires the following software:

#### Splunk Enterprise system requirements

Because this add-on runs on Splunk Enterprise, all of the [Splunk Enterprise system requirements](http://docs.splunk.com/Documentation/Splunk/latest/Installation/Systemrequirements) apply.

#### Download

Download the World Maps Add-on for Splunk Enterprise at https://splunkbase.splunk.com/app/2916/

#### Installation steps

To install and configure this app on your supported platform, follow these steps:

1. In your Splunk Enterprise web interface, click on App(s) -> Manage Apps
1. Click on Install app from file
1. Select the file you downloaded, Click Upload, optionally selecting Upgrade app if you are upgrading from an earlier version. Restart Splunk if required

##### Deploy to single server instance

Follow these steps to install the app in a single server instance of Splunk Enterprise:

1. In your Splunk Enterprise web interface, click on App(s) -> Manage Apps
1. Click on Install app from file
1. Select the file you downloaded, Click Upload, optionally selecting Upgrade app if you are upgrading from an earlier version. Restart Splunk if required

##### Deploy to distributed deployment

**Install to search head**

1. In your Splunk Enterprise web interface, click on App(s) -> Manage Apps
1. Click on Install app from file
1. Select the file you downloaded, Click Upload, optionally selecting Upgrade app if you are upgrading from an earlier version. Restart Splunk if required

**Install to indexers**

This app should not be installed on indexers.

**Install to forwarders**

This app should not be installed on forwarders.

##### Deploy to distributed deployment with Search Head Pooling
Follow the same steps as *Install to search head*.
##### Deploy to distributed deployment with Search Head Clustering
Follow the same steps as *Install to search head*.
##### Deploy to Splunk Cloud
Unknown
#### Configure World Maps Add-on for Splunk Enterprise

1. Install in $SPLUNK_HOME/etc/apps/TA-world_maps

## USER GUIDE

### Usage
    YOUR SEARCH HERE | lookup geo_no_municipalities latitude longitude | stats count by featureId | geom geo_no_municipalities

#### Example
    | makeresults | eval latitude="59.773147" | eval longitude="10.800195" | lookup geo_no_municipalities latitude longitude | stats count by featureId | geom geo_no_municipalities

### Data types

This app provides no search-time knowledge.

### Lookups

The World Maps Add-on for Splunk Enterprise contains 3 lookup files.

- geo_dk_municipalities.kmz
- geo_no_municipalities.kmz
- geo_se_municipalities.kmz
