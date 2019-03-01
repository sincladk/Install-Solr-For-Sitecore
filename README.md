# Install Solr for Sitecore

## Operations
A PowerShell script that performs the following operations

*Note: All steps performed only if necessary.*

1. Downloads [NSSM](https://nssm.cc/) and Solr (locations configured in parameters)
1. Adds a host file entry
1. Configures SSL
1. Moves the `example` directory to `server` and removes the example `collection1`
1. Extracts a blank copy of the Solr cores for Sitecore into the cores directory
1. Registers Solr as a service (name configured in parameters)
1. Runs the service and loads a web browser to the admin interface

## Parameters
* **solrVersion** - The version of Solr to install (used to download the right .zip file)
* **installFolder** - The directory into which to install Solr and [NSSM](https://nssm.cc/)
* **solrPort** - The port number to use for the web interface
* **solrHost** - The hostname to use for the web interface
* **solrSSL** - Whether or not to enable SSL for Solr
* **nssmVersion** - The version of [NSSM](https://nssm.cc/) to install (used to download the right .zip file)
* **JREVersion** - The current version of Java installed on the local machine (used to find the right JRE path)
* **solrInstanceName** - The desired name of the Solr service

## Prerequisites
* Java VM 8+
  * After installing, make sure to update the `$JREVersion` parameter in the script to your installed version number
* Microsoft's [PackageManagement PowerShell Modules](https://www.microsoft.com/en-us/download/details.aspx?id=51451)
* `Microsoft.PowerShell.Archive` module installed

      Install-Module Microsoft.PowerShell.Archive
