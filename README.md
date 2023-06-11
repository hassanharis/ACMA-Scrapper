![image](https://user-images.githubusercontent.com/45975234/234260084-7333e2c7-6c2b-43ac-ac40-80e463f91b61.png)

# ACMA-Python-Scrapper
Python Jupyter Notebook Scrapper for Register of Radiocommunications Licences of Australian Communications and Media Authority 

Getting information from ACMA for engineers (telecom, compliance, EME) is not only time taking but it's a mess because the website doesn't offer to download details of a antennas assigned to a site. To get the information about the antennas, engineers have  to browse to each link of device id and see information separately indozens of webpages that stretches the seconds of work to hours.

Just replace site_url in ACMAscrapper.ipynb and download the excel sheet with information (Licence Number,	Device Registration ID,	Client,	Date, Authorised,	Device Type,	Emission Center, Frequency,	Antenna	Antenna Height (AGL),	Antenna Polarisation,	Antenna Azimuth	Antenna Tilt, Destination Links) of all device ids of a site.

## Features
- Automatically omits the "not found" links of site lookup.
- Scrape all assignments on all pages of site
- Filter the assignments on the basis of client, type (transmitter), or/and frequency rnge
- Collects both receiver/transmitter details of hybrid antennas.
- Exports meaningful data to excel saving you load of time to identify the antenna (using antenna model, carrier, owner, azimuth, height) and get your desired information (frequency, power)
- Retrieve the destination links of yagi's and dishes/parabolic
- All frequencies converted to MHz
- Reorganizes the Antenna Name (Manufacturer, model, type)
- Modular coding with best programming practices to scrape the data as fast as possible
- Reformat and clean the data in all columns
- Sorted by Client > Antenna > Azimuth for easy identification


## Example input and Output

### Input

[https://web.acma.gov.au/rrl/site_search.site_lookup?pSITE_ID=9892](https://web.acma.gov.au/rrl/site_search.site_lookup?pSITE_ID=9892)


### Output
> _Note: The exported Excel file is saved in the "project files of this github repository" with ACMA site iD and site's name as the file name.

![image](https://github.com/hassanharis/ACMA-Scrapper/assets/45975234/c500ddb8-dc01-4afa-bd8d-b0d2d1a63535)


