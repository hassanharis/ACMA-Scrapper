![image](https://user-images.githubusercontent.com/45975234/234260084-7333e2c7-6c2b-43ac-ac40-80e463f91b61.png)

# ACMA-Python-Scrapper
Python Jupyter Notebook Scrapper for Register of Radiocommunications Licences of Australian Communications and Media Authority 

Getting information from ACMA for engineers (telecom, compliance, EME) is not only time taking but it's a mess because the website doesn't offer to download details of a antennas assigned to a site. To get the information about the antennas, engineers have  to browse to each link of device id and see information separately indozens of webpages that stretches the seconds of work to hours.

Just replace site_url in ACMAscrapper.ipynb and download the panda dataframe with information (Licence Number,	Device Registration ID,	Client,	Date, Authorised,	Device Type,	Emission Center, Frequency,	Antenna	Antenna Height (AGL),	Antenna Polarisation,	Antenna Azimuth	Antenna Tilt) of all device ids of a site.

## Features
- Automatically omits the "not found" links of site lookup.
- Collects both receiver/transmitter details of hybrid antennas.
- Exports meaningful data to excel saving you load of time to identify the antenna (using antenna model, carrier, owner, azimuth, height) and get your desired information (frequency, power)
- Reorganizes the Antenna Names.
- Reformat the Carrier the name to ensure they are rightly capitalise


## Example input and Output

### Input

[https://web.acma.gov.au/rrl/site_search.site_lookup?pSITE_ID=502182](https://web.acma.gov.au/rrl/site_search.site_lookup?pSITE_ID=502182)


### Output
> _Note: The exported Excel file is saved in the "project files of this github repository" with site's name as the file name. It has automatically ommited the data of "Not Found" page with id of 11374552/1 and BSL/Licence No of 1136355/1 from Vodafone Australia Pty Limited (536963)_

![image](https://user-images.githubusercontent.com/45975234/235347800-16935b6b-f214-4ab8-b091-aae59604ffd1.png)

