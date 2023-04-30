![image](https://user-images.githubusercontent.com/45975234/234260084-7333e2c7-6c2b-43ac-ac40-80e463f91b61.png)

# ACMA-Python-Scrapper
Python Jupyter Notebook Scrapper for Register of Radiocommunications Licences of Australian Communications and Media Authority 

Getting information from ACMA for engineers (telecom, compliance, EME) is not only time taking but it's a mess because the website doesn't offer to download details of a antennas assigned to a site. To get the information about the antennas, engineers have  to browse to each link of device id and see information separately indozens of webpages that stretches the seconds of work to hours.

Just replace site_url in ACMAscrapper.ipynb and download the panda dataframe with information (Licence Number,	Device Registration ID,	Client,	Date, Authorised,	Device Type,	Emission Center, Frequency,	Antenna	Antenna Height (AGL),	Antenna Polarisation,	Antenna Azimuth	Antenna Tilt) of all device ids of a site.

## Features
- Automatically omits the "not found" links of site lookup.
- Collects both receiver/transmitter details of hybrid antennas.
- Exports meaningful data to excel saving you load of time to identify the antenna (using antenna model, carrier, owner, azimuth, height) and get your desired information (frequency, power)

## Example input and Output

### Input

[https://web.acma.gov.au/pls/radcom/site_search.site_lookup?pSITE_ID=10030844](https://web.acma.gov.au/rrl/site_search.site_lookup?pSITE_ID=502182)

Note: Excel file exported is saved in It has automatically ommited the data of "Not Found" page with id of 11374552/1 and BSL/Licence No of 1136355/1 from Vodafone Australia Pty Limited (536963)

### Output

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Licence</th>
      <th>Antenna</th>
      <th>Client</th>
      <th>Type</th>
      <th>Frequency</th>
      <th>Power</th>
      <th>Height</th>
      <th>Polarisation</th>
      <th>Azimuth</th>
      <th>Tilt</th>
      <th>Device ID</th>
      <th>Date Authorised</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>9263429</td>
      <td>Commscope  RR2VV-6533D-R6_850 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>875 MHz</td>
      <td>160 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373251</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>2</th>
      <td>9263429</td>
      <td>Commscope  RR2VV-6533D-R6_850 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>830 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373252</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>3</th>
      <td>9263429</td>
      <td>Commscope  RR2VV-6533D-R6_850 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>875 MHz</td>
      <td>160 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373253</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9263429</td>
      <td>Commscope  RR2VV-6533D-R6_850 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>830 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373254</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>5</th>
      <td>9263429</td>
      <td>Commscope  RR2VV-6533D-R6_850 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>875 MHz</td>
      <td>160 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373255</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>6</th>
      <td>9263429</td>
      <td>Commscope  RR2VV-6533D-R6_850 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>830 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373256</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>7</th>
      <td>9469858</td>
      <td>Commscope  RRV4-65D-R6 (694-790) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>708 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763943</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1136358/1</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>902.6 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td></td>
      <td>11763921/1</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1136358/1</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>947.6 MHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td></td>
      <td>11763921/1</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1136358/1</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>902.6 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td></td>
      <td>11763922/1</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1136358/1</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>947.6 MHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td></td>
      <td>11763922/1</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1136358/1</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>902.6 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td></td>
      <td>11763920/1</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1136358/1</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>947.6 MHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td></td>
      <td>11763920/1</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>14</th>
      <td>11788421/7</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>894.2 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td></td>
      <td></td>
      <td>NaN</td>
      <td>14/Feb/2023</td>
    </tr>
    <tr>
      <th>15</th>
      <td>9263429</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>830 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9850759</td>
      <td>21/Oct/2015</td>
    </tr>
    <tr>
      <th>16</th>
      <td>9263429</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>830 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9850761</td>
      <td>21/Oct/2015</td>
    </tr>
    <tr>
      <th>17</th>
      <td>9263429</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>830 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9850763</td>
      <td>21/Oct/2015</td>
    </tr>
    <tr>
      <th>18</th>
      <td>10391280</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>790.5 MHz</td>
      <td>66 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11374165</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>19</th>
      <td>10391280</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>735.5 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11374166</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>20</th>
      <td>10391280</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>790.5 MHz</td>
      <td>66 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11374167</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>21</th>
      <td>10391280</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>735.5 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11374168</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>22</th>
      <td>10391280</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>790.5 MHz</td>
      <td>66 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11374169</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>23</th>
      <td>10391280</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>735.5 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11374170</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>24</th>
      <td>9469858</td>
      <td>Commscope  RRV4-65D-R6 (694-790) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>763 MHz</td>
      <td>320 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763884</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>25</th>
      <td>9367136</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.8375 GHz</td>
      <td>40 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373456</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>26</th>
      <td>9263452</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.83 GHz</td>
      <td>80 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373455</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>27</th>
      <td>9263452</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.735 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373457</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>28</th>
      <td>9367136</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.7425 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373458</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>29</th>
      <td>9367136</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.8375 GHz</td>
      <td>40 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373460</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>30</th>
      <td>9367136</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.7425 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373462</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>31</th>
      <td>9367136</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.8375 GHz</td>
      <td>40 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373464</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>32</th>
      <td>9367136</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.7425 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373465</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>33</th>
      <td>10143110</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.965 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373797</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>34</th>
      <td>10917464</td>
      <td>Nokia  AEQE_3.48-3.8_120 Panel(1sector)</td>
      <td>MOBILE JV PTY LIMITED</td>
      <td>Transmitter</td>
      <td>3.67 GHz</td>
      <td>200 W pY</td>
      <td>27.74 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11393585</td>
      <td>02/Nov/2021</td>
    </tr>
    <tr>
      <th>35</th>
      <td>10917464</td>
      <td>Nokia  AEQE_3.48-3.8_120 Panel(1sector)</td>
      <td>MOBILE JV PTY LIMITED</td>
      <td>Receiver</td>
      <td>3.67 GHz</td>
      <td>NaN</td>
      <td>27.74 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11393586</td>
      <td>02/Nov/2021</td>
    </tr>
    <tr>
      <th>36</th>
      <td>10917464</td>
      <td>Nokia  AEQE_3.48-3.8_120 Panel(1sector)</td>
      <td>MOBILE JV PTY LIMITED</td>
      <td>Transmitter</td>
      <td>3.6525 GHz</td>
      <td>200 W pY</td>
      <td>27.74 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11393587</td>
      <td>02/Nov/2021</td>
    </tr>
    <tr>
      <th>37</th>
      <td>10917464</td>
      <td>Nokia  AEQE_3.48-3.8_120 Panel(1sector)</td>
      <td>MOBILE JV PTY LIMITED</td>
      <td>Receiver</td>
      <td>3.6525 GHz</td>
      <td>NaN</td>
      <td>27.74 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11393588</td>
      <td>02/Nov/2021</td>
    </tr>
    <tr>
      <th>38</th>
      <td>10917464</td>
      <td>Nokia  AEQE_3.48-3.8_120 Panel(1sector)</td>
      <td>MOBILE JV PTY LIMITED</td>
      <td>Transmitter</td>
      <td>3.6525 GHz</td>
      <td>200 W pY</td>
      <td>27.74 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11393589</td>
      <td>02/Nov/2021</td>
    </tr>
    <tr>
      <th>39</th>
      <td>10917464</td>
      <td>Nokia  AEQE_3.48-3.8_120 Panel(1sector)</td>
      <td>MOBILE JV PTY LIMITED</td>
      <td>Receiver</td>
      <td>3.6525 GHz</td>
      <td>NaN</td>
      <td>27.74 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11393590</td>
      <td>02/Nov/2021</td>
    </tr>
    <tr>
      <th>40</th>
      <td>9469858</td>
      <td>Commscope  RRV4-65D-R6 (694-790) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>763 MHz</td>
      <td>320 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763863</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>41</th>
      <td>9469858</td>
      <td>Commscope  RRV4-65D-R6 (694-790) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>708 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763871</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>42</th>
      <td>9263452</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.83 GHz</td>
      <td>80 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373443</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>43</th>
      <td>9263452</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.735 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373446</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>44</th>
      <td>9263452</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.83 GHz</td>
      <td>80 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373450</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>45</th>
      <td>9263452</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.735 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373452</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>46</th>
      <td>10143110</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.155 GHz</td>
      <td>120 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373786</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>47</th>
      <td>10143110</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.965 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373788</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>48</th>
      <td>10143110</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.155 GHz</td>
      <td>120 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373790</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>49</th>
      <td>10143110</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.965 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373792</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>50</th>
      <td>10143110</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.155 GHz</td>
      <td>120 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373793</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>51</th>
      <td>9469858</td>
      <td>Commscope  RRV4-65D-R6 (694-790) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>763 MHz</td>
      <td>320 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763833</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>52</th>
      <td>9469858</td>
      <td>Commscope  RRV4-65D-R6 (694-790) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>708 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763847</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>53</th>
      <td>10143562</td>
      <td>Commscope  RRV4-65D-R6 (1920-2180) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>2.14 GHz</td>
      <td>280 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11764158</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>54</th>
      <td>10143562</td>
      <td>Commscope  RRV4-65D-R6 (1920-2180) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>1.95 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11764163</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>55</th>
      <td>10143562</td>
      <td>Commscope  RRV4-65D-R6 (1920-2180) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>2.14 GHz</td>
      <td>280 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11764167</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>56</th>
      <td>10143562</td>
      <td>Commscope  RRV4-65D-R6 (1920-2180) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>1.95 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11764168</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>57</th>
      <td>10143562</td>
      <td>Commscope  RRV4-65D-R6 (1920-2180) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>2.14 GHz</td>
      <td>280 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11764169</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>58</th>
      <td>10143562</td>
      <td>Commscope  RRV4-65D-R6 (1920-2180) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>1.95 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11764170</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>59</th>
      <td>9263429</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>875 MHz</td>
      <td>160 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9850683</td>
      <td>21/Oct/2015</td>
    </tr>
    <tr>
      <th>60</th>
      <td>9263429</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>875 MHz</td>
      <td>160 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9850684</td>
      <td>21/Oct/2015</td>
    </tr>
    <tr>
      <th>61</th>
      <td>9263429</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>875 MHz</td>
      <td>160 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9850682</td>
      <td>21/Oct/2015</td>
    </tr>
    <tr>
      <th>62</th>
      <td>9460721</td>
      <td>Nokia  AENB Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>2.351 GHz</td>
      <td>392 W pY</td>
      <td>28.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763817</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>63</th>
      <td>9460721</td>
      <td>Nokia  AENB Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>2.351 GHz</td>
      <td>NaN</td>
      <td>28.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763824</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>64</th>
      <td>9469870</td>
      <td>Commscope  RRV4-65D-R6 (2500-2690) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>2.68 GHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763793</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>65</th>
      <td>9469870</td>
      <td>Commscope  RRV4-65D-R6 (2500-2690) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>2.56 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763801</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>66</th>
      <td>11286123</td>
      <td>NOKIA  AEQP_3500_120 Panel</td>
      <td>AKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>3.51 GHz</td>
      <td>320 W pY</td>
      <td>26.7 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11764112</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>67</th>
      <td>11286123</td>
      <td>NOKIA  AEQP_3500_120 Panel</td>
      <td>AKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>3.51 GHz</td>
      <td>NaN</td>
      <td>26.7 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11764116</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>68</th>
      <td>11286123</td>
      <td>NOKIA  AEQP_3500_120 Panel</td>
      <td>AKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>3.51 GHz</td>
      <td>320 W pY</td>
      <td>26.7 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11764119</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>69</th>
      <td>11286123</td>
      <td>NOKIA  AEQP_3500_120 Panel</td>
      <td>AKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>3.51 GHz</td>
      <td>NaN</td>
      <td>26.7 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11764123</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>70</th>
      <td>11286123</td>
      <td>NOKIA  AEQP_3500_120 Panel</td>
      <td>AKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>3.51 GHz</td>
      <td>320 W pY</td>
      <td>26.7 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11764127</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>71</th>
      <td>11286123</td>
      <td>NOKIA  AEQP_3500_120 Panel</td>
      <td>AKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>3.51 GHz</td>
      <td>NaN</td>
      <td>26.7 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11764129</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>72</th>
      <td>9469870</td>
      <td>Commscope  RRV4-65D-R6 (2500-2690) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>2.68 GHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763766</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>73</th>
      <td>9460721</td>
      <td>Nokia  AENB Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>2.351 GHz</td>
      <td>392 W pY</td>
      <td>28.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763767</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>74</th>
      <td>9469870</td>
      <td>Commscope  RRV4-65D-R6 (2500-2690) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>2.56 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763771</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>75</th>
      <td>9460721</td>
      <td>Nokia  AENB Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>2.351 GHz</td>
      <td>NaN</td>
      <td>28.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763772</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>76</th>
      <td>9469870</td>
      <td>Commscope  RRV4-65D-R6 (2500-2690) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>2.68 GHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763782</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>77</th>
      <td>9469870</td>
      <td>Commscope  RRV4-65D-R6 (2500-2690) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>2.56 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763785</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>78</th>
      <td>9263448</td>
      <td>Commscope  RRV4-65D-R6 (1850-1990) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>1.7625 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11764092</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>79</th>
      <td>9263448</td>
      <td>Commscope  RRV4-65D-R6 (1850-1990) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>1.8575 GHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11764097</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>80</th>
      <td>9263448</td>
      <td>Commscope  RRV4-65D-R6 (1850-1990) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>1.7625 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11764102</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>81</th>
      <td>10143136</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.975 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9434917</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>82</th>
      <td>10143136</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.975 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9434921</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>83</th>
      <td>10143136</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.975 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9434924</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>84</th>
      <td>9460721</td>
      <td>Nokia  AENB Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>2.351 GHz</td>
      <td>392 W pY</td>
      <td>28.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763752</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>85</th>
      <td>9460721</td>
      <td>Nokia  AENB Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>2.351 GHz</td>
      <td>NaN</td>
      <td>28.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763757</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>86</th>
      <td>9263448</td>
      <td>Commscope  RRV4-65D-R6 (1850-1990) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>1.8575 GHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11764080</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>87</th>
      <td>9263448</td>
      <td>Commscope  RRV4-65D-R6 (1850-1990) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Receiver</td>
      <td>1.7625 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11764085</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>88</th>
      <td>9263448</td>
      <td>Commscope  RRV4-65D-R6 (1850-1990) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>1.8575 GHz</td>
      <td>240 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11764089</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>89</th>
      <td>11788421/7</td>
      <td>Commscope  RRV4-65D-R6 (880-960) Panel(1sector)</td>
      <td>Optus Mobile Pty Limited</td>
      <td>Transmitter</td>
      <td>939.2 MHz</td>
      <td>160 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td></td>
      <td></td>
      <td>NaN</td>
      <td>14/Feb/2023</td>
    </tr>
    <tr>
      <th>90</th>
      <td>9460721</td>
      <td>Commscope  RRV4-65D-R6 (2300-2500) Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>2.351 GHz</td>
      <td>294 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763720</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>91</th>
      <td>9460721</td>
      <td>Commscope  RRV4-65D-R6 (2300-2500) Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>2.351 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11763723</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>92</th>
      <td>9460721</td>
      <td>Commscope  RRV4-65D-R6 (2300-2500) Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>2.351 GHz</td>
      <td>294 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763727</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>93</th>
      <td>9460721</td>
      <td>Commscope  RRV4-65D-R6 (2300-2500) Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>2.351 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11763732</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>94</th>
      <td>9460721</td>
      <td>Commscope  RRV4-65D-R6 (2300-2500) Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Transmitter</td>
      <td>2.351 GHz</td>
      <td>294 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763705</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>95</th>
      <td>9460721</td>
      <td>Commscope  RRV4-65D-R6 (2300-2500) Panel(1sector)</td>
      <td>BKAL Pty Ltd</td>
      <td>Receiver</td>
      <td>2.351 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11763708</td>
      <td>02/Sep/2022</td>
    </tr>
    <tr>
      <th>96</th>
      <td>10143110</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.925 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9434980</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>97</th>
      <td>10143110</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.925 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9434982</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>98</th>
      <td>10143110</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.925 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9434984</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>99</th>
      <td>10143136</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.165 GHz</td>
      <td>80 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9432006</td>
      <td>20/Apr/2014</td>
    </tr>
    <tr>
      <th>100</th>
      <td>10143136</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.165 GHz</td>
      <td>80 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9432007</td>
      <td>20/Apr/2014</td>
    </tr>
    <tr>
      <th>101</th>
      <td>10143136</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.165 GHz</td>
      <td>80 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9432008</td>
      <td>20/Apr/2014</td>
    </tr>
    <tr>
      <th>102</th>
      <td>1136355/1</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>911.2 MHz</td>
      <td>NaN</td>
      <td>26 m</td>
      <td>RH Slant</td>
      <td></td>
      <td></td>
      <td>10027452/1</td>
      <td>19/Oct/2015</td>
    </tr>
    <tr>
      <th>103</th>
      <td>1136355/1</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>956.2 MHz</td>
      <td>80 W pY</td>
      <td>26 m</td>
      <td>RH Slant</td>
      <td></td>
      <td></td>
      <td>10027452/1</td>
      <td>19/Oct/2015</td>
    </tr>
    <tr>
      <th>104</th>
      <td>1136355/1</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>911.2 MHz</td>
      <td>NaN</td>
      <td>26 m</td>
      <td>RH Slant</td>
      <td></td>
      <td></td>
      <td>10027450/1</td>
      <td>19/Oct/2015</td>
    </tr>
    <tr>
      <th>105</th>
      <td>1136355/1</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>956.2 MHz</td>
      <td>80 W pY</td>
      <td>26 m</td>
      <td>RH Slant</td>
      <td></td>
      <td></td>
      <td>10027450/1</td>
      <td>19/Oct/2015</td>
    </tr>
    <tr>
      <th>106</th>
      <td>1136355/1</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>911.2 MHz</td>
      <td>NaN</td>
      <td>26 m</td>
      <td>RH Slant</td>
      <td></td>
      <td></td>
      <td>10027451/1</td>
      <td>19/Oct/2015</td>
    </tr>
    <tr>
      <th>107</th>
      <td>1136355/1</td>
      <td>ARGUS  RV4PX310R(900M) Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>956.2 MHz</td>
      <td>80 W pY</td>
      <td>26 m</td>
      <td>RH Slant</td>
      <td></td>
      <td></td>
      <td>10027451/1</td>
      <td>19/Oct/2015</td>
    </tr>
    <tr>
      <th>108</th>
      <td>9263452</td>
      <td>ARGUS  RV4PX310R Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.83 GHz</td>
      <td>32 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9431193</td>
      <td>16/Apr/2014</td>
    </tr>
    <tr>
      <th>109</th>
      <td>9263452</td>
      <td>ARGUS  RV4PX310R Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.83 GHz</td>
      <td>32 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9431196</td>
      <td>16/Apr/2014</td>
    </tr>
    <tr>
      <th>110</th>
      <td>9263452</td>
      <td>ARGUS  RV4PX310R Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.83 GHz</td>
      <td>32 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9431199</td>
      <td>16/Apr/2014</td>
    </tr>
    <tr>
      <th>111</th>
      <td>9263452</td>
      <td>ARGUS  RV4PX310R Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.735 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9434501</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>112</th>
      <td>9263452</td>
      <td>ARGUS  RV4PX310R Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.735 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9434503</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>113</th>
      <td>9263452</td>
      <td>ARGUS  RV4PX310R Panel (1 sector)-R</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.735 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9434505</td>
      <td>26/Apr/2014</td>
    </tr>
    <tr>
      <th>114</th>
      <td>10143110</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.115 GHz</td>
      <td>80 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>9432113</td>
      <td>20/Apr/2014</td>
    </tr>
    <tr>
      <th>115</th>
      <td>10143110</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.115 GHz</td>
      <td>80 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>9432114</td>
      <td>20/Apr/2014</td>
    </tr>
    <tr>
      <th>116</th>
      <td>10143110</td>
      <td>ARGUS  RV4PX310R(2.1G) Panel (1 sector)-R</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.115 GHz</td>
      <td>80 W pY Mean Power</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>9432115</td>
      <td>20/Apr/2014</td>
    </tr>
    <tr>
      <th>117</th>
      <td>9619844</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.75 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373688</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>118</th>
      <td>10391286</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>TPG Internet Pty Ltd</td>
      <td>Receiver</td>
      <td>743 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11374370</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>119</th>
      <td>10391286</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>TPG Internet Pty Ltd</td>
      <td>Transmitter</td>
      <td>798 MHz</td>
      <td>134 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11374371</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>120</th>
      <td>10391286</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>TPG Internet Pty Ltd</td>
      <td>Transmitter</td>
      <td>798 MHz</td>
      <td>134 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11374376</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>121</th>
      <td>10391286</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>TPG Internet Pty Ltd</td>
      <td>Receiver</td>
      <td>743 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11374377</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>122</th>
      <td>9619844</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.845 GHz</td>
      <td>80 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373676</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>123</th>
      <td>9619844</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.75 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11373679</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>124</th>
      <td>9619844</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.845 GHz</td>
      <td>80 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373681</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>125</th>
      <td>9619844</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.75 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11373683</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>126</th>
      <td>9619844</td>
      <td>Commscope  RR2VV-6533D-R6_1800 Panel(Multi-sector)</td>
      <td>Vodafone Hutchison Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>1.845 GHz</td>
      <td>80 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11373685</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>127</th>
      <td>10143136</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.165 GHz</td>
      <td>120 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11374022</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>128</th>
      <td>10143136</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.975 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11374023</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>129</th>
      <td>10143136</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.165 GHz</td>
      <td>120 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11374024</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>130</th>
      <td>10143136</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.975 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11374025</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>131</th>
      <td>10143136</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Transmitter</td>
      <td>2.165 GHz</td>
      <td>120 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11374026</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>132</th>
      <td>10143136</td>
      <td>Commscope  RR2VV-6533D-R6_2100 Panel(Multi-sector)</td>
      <td>Vodafone Australia Pty Limited</td>
      <td>Receiver</td>
      <td>1.975 GHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>240°</td>
      <td>0°</td>
      <td>11374027</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>133</th>
      <td>10391286</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>TPG Internet Pty Ltd</td>
      <td>Receiver</td>
      <td>743 MHz</td>
      <td>NaN</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>120°</td>
      <td>0°</td>
      <td>11374374</td>
      <td>15/Oct/2021</td>
    </tr>
    <tr>
      <th>134</th>
      <td>10391286</td>
      <td>cOMMSCOPE  RR2VV-6533D-R6_700 Panel(1sector)</td>
      <td>TPG Internet Pty Ltd</td>
      <td>Transmitter</td>
      <td>798 MHz</td>
      <td>134 W pY</td>
      <td>26.1 m</td>
      <td>Slant</td>
      <td>10°</td>
      <td>0°</td>
      <td>11374368</td>
      <td>15/Oct/2021</td>
    </tr>
  </tbody>
</table>
