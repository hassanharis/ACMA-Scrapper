![image](https://user-images.githubusercontent.com/45975234/234260084-7333e2c7-6c2b-43ac-ac40-80e463f91b61.png)

# ACMA-Python-Scrapper
Python Jupyter Notebook Scrapper for Register of Radiocommunications Licences of Australian Communications and Media Authority 

Getting information from ACMA for engineers (telecom, compliance, EME) is not only time taking but it's a mess because the website doesn't offer to download details of a antennas assigned to a site. To get the information about the antennas, engineers have  to browse to each link of device id and see information separately indozens of webpages that stretches the seconds of work to hours.

Just replace site_url in ACMAscrapper.ipynb and download the panda dataframe with information (Licence Number,	Device Registration ID,	Client,	Date, Authorised,	Device Type,	Emission Center, Frequency,	Antenna	Antenna Height (AGL),	Antenna Polarisation,	Antenna Azimuth	Antenna Tilt) of all device ids of a site.

## Example input and Output

Input = https://web.acma.gov.au/pls/radcom/site_search.site_lookup?pSITE_ID=10030844

Output

![image](https://user-images.githubusercontent.com/45975234/234274118-9a9c2b94-cfa8-4f8c-9d75-011cbbbadfb2.png)

