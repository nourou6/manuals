**B/C25** -- **Regulations for reporting TEMP, TEMP SHIP and TEMP MOBIL data in TDCF**

**General**

> A BUFR (or CREX) message shall be sent when the 100-hPa level is reached. Subsequently, a BUFR (or CREX) message shall be produced when the sounding is completed containing data from the entire sounding. If the sounding is terminated below 100-hPa level, only the later message shall be produced.
>
> If high-resolution data are reported, only one BUFR message shall be sent when the 100-hPa level is reached and only one BUFR message shall be produced when the sounding is completed, provided that all standard and significant levels are properly identified in compliance with the relevant B/C25 Regulations.

**TM 309052 -- BUFR template for P, T, U and wind vertical profiles suitable for TEMP, TEMP SHIP and TEMP MOBIL observation data**

  -------------- -------------- -----------------------------------------------------------------------------------------
                                **Sequence for representation of TEMP, TEMP SHIP and TEMP MOBIL observation type data**
  **3 09 052**   **3 01 111**   **Identification of launch site and instrumentation for P, T, U and wind measurements**
                 **3 01 113**   **Date/time of launch**
                 **3 01 114**   **Horizontal and vertical coordinates of launch site**
                 **3 02 049**   **Cloud information reported with vertical soundings**
                 **0 22 043**   **Sea/water temperature**
                 **1 01 000**   **Delayed replication of 1 descriptor**
                 **0 31 002**   **Extended delayed descriptor replication factor**
                 **3 03 054**   **Temperature, dewpoint and wind data at a pressure level with radiosonde position**
                 1 01 000       **Delayed replication of 1 descriptor**
                 0 31 001       **Delayed descriptor replication factor**
                 **3 03 051**   **Wind shear data at a pressure level with radiosonde position**
  -------------- -------------- -----------------------------------------------------------------------------------------

This BUFR template for P, T, U and wind profiles further expands as follows:

  ---------------------------------------------------------------------------------------------------------------------------------
                                                                                                                      Unit, scale
  -------------- ---------- ----------------------------------------------------------------------------------------- -------------
                            **Identification of launch site and instrumentation for P, T, U and wind measurements**   

  **3 01 111**   3 01 001   WMO block and station numbers                                                             Numeric

                 0 01 011   Ship or mobile land station identifier                                                    CCITT IA5

                 0 02 011   Radiosonde type                                                                           Code table

                 0 02 013   Solar and infrared radiation correction                                                   Code table

                 0 02 014   Tracking technique/status of system used                                                  Code table

                 0 02 003   Type of measuring equipment used                                                          Code table

                            **Date/time of launch**                                                                   

  **3 01 113**   0 08 021   Time significance (= 18 Launch time)                                                      Code table

                 3 01 011   Year                                                                                      Year

                            Month                                                                                     Month

                            Day                                                                                       Day

                 3 01 013   Hour                                                                                      Hour

                            Minute                                                                                    Minute

                            Second                                                                                    Second

                            **Horizontal and vertical coordinates of launch site**                                    

  **3 01 114**   3 01 021   Latitude/longitude (high accuracy)                                                        Degree, 5

                 0 07 030   Height of station ground above mean sea level                                             m, 1

                 0 07 031   Height of barometer above mean sea level                                                  m, 1

                 0 07 007   Height (of release of sonde above mean sea level)                                         m

                 0 33 024   Station elevation quality mark (for mobile stations)                                      Code table

                            **Cloud information reported with vertical soundings**                                    

  **3 02 049**   0 08 002   Vertical significance (surface observations)                                              Code table

                 0 20 011   Cloud amount (of low or middle clouds N~h~)                                               Code table

                 0 20 013   Height of base of cloud (h)                                                               m, --1

                 0 20 012   Cloud type (low clouds C~L~)                                                              Code table

                 0 20 012   Cloud type (middle clouds C~M~)                                                           Code table

                 0 20 012   Cloud type (high clouds C~H~)                                                             Code table

                 0 08 002   Vertical significance (surface observations) (= missing value)                            Code table

  **0 22 043**              **Sea/water temperature (for ship stations)**                                             K, 2

                            **Temperature, dewpoint and wind data at pressure levels**                                

  **1 01 000**              Delayed replication of 1 descriptor                                                       

  **0 31 002**              Extended delayed descriptor replication factor                                            Numeric

                            *Temperature, dewpoint and wind data at a pressure\                                       
                            level with radiosonde position*                                                           

  **3 03 054**   0 04 086   Long time period or displacement (since launch time)                                      Second

                 0 08 042   Extended vertical sounding significance                                                   Flag table

                 0 07 004   Pressure                                                                                  Pa, --1

                 0 10 009   Geopotential height                                                                       gpm

                 0 05 015   Latitude displacement (high accuracy) -- since launch site                                Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site                               Degree, 5

                 0 12 101   Temperature/air temperature                                                               K, 2

                 0 12 103   Dewpoint temperature                                                                      K, 2

                 0 11 001   Wind direction                                                                            Degree true

                 0 11 002   Wind speed                                                                                m s^--1^, 1

                            **Wind shear data**                                                                       

  **1 01 000**              Delayed replication of 1 descriptor                                                       

  **0 31 001**              Delayed descriptor replication factor                                                     Numeric

                            *Wind shear data at a pressure level* ***with radiosonde\                                 
                            position***                                                                               

  **3 03 051**   0 04 086   Long time period or displacement (since launch time)                                      Second

                 0 08 042   Extended vertical sounding significance                                                   Flag table

                 0 07 004   Pressure                                                                                  Pa, --1

                 0 05 015   Latitude displacement (high accuracy) -- since launch site                                Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site                               Degree, 5

                 0 11 061   Absolute wind shear in 1 km layer below                                                   m s^--1^, 1

                 0 11 062   Absolute wind shear in 1 km layer above                                                   m s^--1^, 1
  ---------------------------------------------------------------------------------------------------------------------------------

Notes:

\(1) Time of launch 3 01 013 shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry for seconds shall be put to zero.

\(2) Long time displacement 0 04 086 represents the time offset from the launch time 3 01 013 (in seconds).

\(3) Latitude displacement 0 05 015 represents the latitude offset from the latitude of the launch site. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site.

\(4) If additional information on sounding is available, the sequence \<3 09 052\> shall be preceded by sequences suitable for reporting additional information on sounding systems.

**(5) If the sounding data are obtained from** upper-air systems where pressure is derived from geopotential height by integration of hydrostatic equation, the geopotential calculation method shall be recorded using 0 02 191 within the preceding sequences**.**

**\
Regulations:**

**B/C25.1 Section 1 of BUFR or CREX**

**B/C25.2 Identification of launch site and instrumentation for P, T, U and wind measurements**

**B/C25.3 Date/time of launch**

B/C25.4 Horizontal and vertical coordinates **of launch site**

B/C25.5 Cloud information reported with vertical soundings

**B/C25.6** Sea/water temperature

**B/C25.7** Temperature, dewpoint and wind data at pressure levels

**B/C25.8** Criteria for reporting standard and significant levels

**B/C25.9** Wind shear data

**B/C25.10 Data required by regional or national reporting practices**

Annex I Regional regulations for reporting TEMP, TEMP SHIP and TEMP MOBIL data in TDCF

Annex II List of parameters for representation of additional information on sounding instrumentation

**B/C25.1 Section 1 of BUFR or CREX**

**B/C25.1.1 Entries required in Section 1 of BUFR**

> **The following entries shall be included in BUFR Section 1:**
>
> -- **BUFR master table;**
>
> -- **Identification of originating/generating centre;**
>
> -- **Identification of originating/generating sub-centre;**
>
> -- **Update sequence number;**
>
> -- **Identification of inclusion of optional section;**
>
> -- **Data category (= 002 for all TEMP type data);**
>
> -- **International data sub-category (see Notes 1 and 2);**
>
> -- **Local data sub-category;**
>
> -- **Version number of master table;**
>
> -- **Version number of local tables;**
>
> -- **Year (of standard time) (year of the century up to BUFR edition 3);**
>
> -- **Month (of standard time);**
>
> -- **Day (when standard time, = YY in the** abbreviated telecommunication header **for TEMP, TEMP SHIP and TEMP MOBIL type data**);
>
> -- **Hour (when standard time, = GG in the** abbreviated telecommunication header **e.g. = 00, 06, 12 or 18** **for TEMP, TEMP SHIP and TEMP MOBIL type data**);
>
> -- **Minute (when standard time, = 00 for TEMP, TEMP SHIP and TEMP MOBIL type data);**
>
> -- **Second (= 0) (see Note 1).**
>
> **Notes:**
>
> **(1) Inclusion of this entry is required starting with BUFR edition 4.**
>
> **(2) If required, the international data sub-category shall be included at all observation times as follows:**
>
> **= 004 for TEMP data;**
>
> **= 005 for TEMP SHIP data;**
>
> **= 006 for TEMP MOBIL data.**
>
> **(3) If an NMHS performs conversion of TEMP, TEMP SHIP or TEMP MOBIL data produced by another NMHS, o**riginating centre in Section 1 shall indicate **the converting centre and o**riginating sub-centre shall indicate the **producer of TEMP, TEMP SHIP or TEMP MOBIL bulletins. Producer of TEMP, TEMP SHIP or TEMP MOBIL bulletins shall be specified in Common Code table C-12 as a sub-centre of the originating centre, i.e. of the NMHS executing the conversion.**

**B/C25.1.2 Entries required in Section 1 of CREX**

> **The following entries shall be included in CREX Section 1:**
>
> -- **CREX master table;**
>
> -- **CREX edition number;**
>
> -- **CREX table version number;**
>
> -- **Version number of BUFR master table (see Note 1);**
>
> -- **Version number of local tables (see Note 1);**
>
> -- **Data category (= 002 for all TEMP type data);**
>
> -- **International data sub-category (see Notes 1 and 2);**
>
> -- **Identification of originating/generating centre (see Note 1);**
>
> -- **Identification of originating/generating sub-centre (see Note 1);**
>
> -- **Update sequence number (see Note 1);**
>
> -- **Number of subsets (see Note 1);**
>
> -- **Year (of standard time) (see Note 1);**
>
> -- **Month (of standard time) (see Note 1);**
>
> -- **Day (when standard time, = YY in the** abbreviated telecommunication header **for TEMP, TEMP SHIP and TEMP MOBIL type data**) **(see Note 1);**
>
> -- **Hour (when standard time, = GG in the abbreviated telecommunication header, e.g. = 00, 06, 12 or 18** **for TEMP, TEMP SHIP and TEMP MOBIL type data**) **(see Note 1);**
>
> -- **Minute (when standard time, = 00 for TEMP, TEMP SHIP and TEMP MOBIL type data) (see Note 1).**
>
> **Notes:**
>
> **(1) Inclusion of these entries is required starting with CREX edition 2.**
>
> **(2) If inclusion of international data sub-category is required, Note 2 under Regulation B/C25.1.1 applies.**
>
> **(3) If an NMHS performs conversion of TEMP, TEMP SHIP or TEMP MOBIL data produced by another NMHS, Note 3 under Regulation B/C25.1.1 applies.**

**B/C25.2 Identification of launch site and instrumentation for P, T, U and wind measurements \<3 01 111\>**

**B/C25.2.1 Identification of launch site**

> WMO block number (0 01 001) and WMO station number (0 01 002) shall be always reported as a non-missing value in reports from a fixed land station. WMO block and station number may be included in reports from a fixed sea station if available.
>
> Ship or mobile land station identifier (0 01 011) shall be always reported not exceeding 9 characters in reports from ships or mobile stations. Ship or mobile station identifier 0 01 011 shall be always set to a missing value in reports from a fixed land station. \[35.2.1\]

**B/C25.2.2 Instrumentation for P, T, U and wind measurement**

> Radiosonde type (Code table 0 02 011), solar and infrared radiation correction (Code table 0 02 013), tracking techniques/status of system used (Code table 0 02 014) and type of measuring equipment used (Code table 0 02 003) shall be reported. \[35.2.5\]

**B/C25.3 Date/time of launch \<3 01 113\>**

> Time significance (0 08 021) shall be always set to 18 to indicate that the following entries specify the date and time of launching the radiosonde.
>
> Date of launch \<3 01 011\> and time of launch \<3 01 013\> shall be reported, i.e. year (0 04 001), month (0 04 002), day (0 04 003) and hour (0 04 004), minute (0 04 005) and second (0 04 006) of the actual time of launch shall be reported. \[35.2.5\]
>
> Note: Time of launch \<3 01 013\> shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry 0 04 006 for seconds shall be set to zero.

**B/C25.4 Horizontal and vertical coordinates of launch site \<3 01 114\>**

> **Latitude (0** **05 001) and longitude** (0 06 001) of the launch site shall be reported in degrees with precision in 10^--5^ of a degree.
>
> Height of station ground above mean sea level (0 07 030) and height of barometer above mean sea level (0 07 031) shall be reported in metres with precision in tenths of a metre.
>
> Height of release of sonde above mean sea level (0 07 007) shall be reported in metres.
>
> Station elevation quality mark (Code table 0 33 024) shall be reported to indicate the accuracy of the vertical coordinates of the mobile land station. Fixed land stations and sea stations shall report this datum as a missing value. \[35.2.1\]
>
> Note: The official altitude of the aerodrome (HA in Volume A) shall not be used to report Height of station ground above mean sea level 0 07 030 in BUFR or CREX messages from aerodromes. Those are two different vertical coordinates. \"Height of station ground above mean sea level\" for each station should be made available to the encoding centre concerned, which may be a centre within the same NMHS or other NMC/RTH.

**B/C25.5 Cloud information reported with vertical sounding \<3 02 049\>**

**B/C25.5.1 Vertical significance (surface observations)** -- Code table 0** **08** **002

> To specify vertical significance (0 08 002) within the sequence 3 02 049, a code figure shall be selected in the following way:
>
> \(a) If low clouds are observed, then code figure 7 (Low cloud) shall be used;
>
> \(b) If there are no low clouds but middle clouds are observed, then code figure 8 (Middle clouds) shall be used;
>
> \(c) If there are no low and there are no middle clouds but high clouds are observed, then code figure 0 shall be used;
>
> \(d) If sky is obscured by fog and/or other phenomena, then code figure 5 (Ceiling) shall be used;
>
> \(e) If there are no clouds (clear sky), then code figure 62 (Value not applicable) shall be used;
>
> \(f) If the cloud cover is not discernible for reasons other than (d) above or observation is not made, then code figure 63 (Missing value) shall be used.

**B/C25.5.2 Cloud amount (of low or middle clouds**) -- Code table 0** **20** **011

> *Amount of all the low clouds (clouds of the genera Stratocumulus, Stratus, Cumulus, and Cumulonimbus) present or, if no low clouds are present, the amount of all the middle clouds (clouds of the genera Altocumulus, Altostratus, and Nimbostratus) present*.

**B/C25.5.2.1** Cloud amount shall be reported as follows:

> \(a) If there are low clouds, then the total amount of all low clouds, as actually seen by the observer during the observation shall be reported for the cloud amount;
>
> \(b) If there are no low clouds but there are middle clouds, then the total amount of the middle clouds shall be reported for the cloud amount;
>
> \(c) If there are no low clouds and there are no middle clouds but there are high clouds (clouds of the genera Cirrus, Cirrocumulus, and Cirrostratus), then the cloud amount shall be reported as zero.
>
> \[35.3.4.1\], \[12.2.7.2.1\]

**B/C25.5.2.2** Amount of Altocumulus perlucidus or Stratocumulus perlucidus ("mackerel sky") shall be reported using code figure 7 or less since breaks are always present in this cloud form even if it extends over the whole celestial dome. \[35.3.4.1\], \[12.2.7.2.2\]

**B/C25.5.2.3** When the clouds reported for cloud amount are observed through fog or an analogous phenomenon, the cloud amount shall be reported as if these phenomena were not present. \[35.3.4.1\], \[12.2.7.2.3\]

**B/C25.5.2.4** If the clouds reported for cloud amount include contrails, then the cloud amount shall include the amount of persistent contrails. Rapidly dissipating contrails shall not be included in the value for the cloud amount. \[35.3.4.1\], \[12.2.7.2.4\]

**B/C25.5.3 Height of base of lowest cloud**

> *Height above surface of the base (0 20 013) of the lowest cloud seen shall be reported* in metres (with precision in tens of metres).
>
> Note: The term « height above surface » shall be considered as being the height above the official aerodrome elevation or above station elevation at a non-aerodrome station or the height above water surface of sea or lake.

**B/C25.5.3.1** When the station is in fog, a sandstorm or in blowing snow but the sky is discernible, the base of the lowest cloud shall refer to the base of the lowest cloud observed, if any. When, under the above conditions, the sky is not discernible, the base of the lowest cloud shall be replaced by vertical visibility. \[35.3.4.1\], \[12.4.10.5\]

**B/C25.5.3.2** *When no cloud is reported (total cloud cover = 0)* the base of the lowest cloud *shall be reported as a missing value.*

**B/C25.5.3.3** *When, by national decision, clouds with bases below the station are reported from the station and clouds with bases below and tops above the station are observed,* the base of the lowest cloud *shall be reported having a negative value if the base of cloud is discernible, or as a missing value.*

**B/C25.5.4 Cloud type of low, middle and high clouds** -- Code table 0 20 012

> Clouds of the genera Stratocumulus, Stratus, Cumulus, and Cumulonimbus (low clouds) shall be reported for the first entry 0 20 012, clouds of the genera Altocumulus, Altostratus, and Nimbostratus (middle clouds) shall be reported for the second entry 0 20 012 and clouds of the genera Cirrus, Cirrocumulus, and Cirrostratus (high clouds) shall be reported for the third entry 0 20 012.

**B/C25.5.4.1** The reporting of type of low, middle and high clouds shall be as specified in the *International Cloud Atlas* (WMO-No. 407), Volume I. \[35.3.4.1\], \[12.2.7.3\]

**B/C25.6 Sea/water temperature**

> Sea/water temperature (0 22 043) shall be reported in kelvin (with precision in hundredths of a kelvin); if produced in CREX, in degrees Celsius (with precision in hundredths of a degree Celsius). Sea/water temperature data shall be reported with precision in hundredths of a degree even if they are available with the accuracy in tenths of a degree.
>
> Note: Notes 1 and 2 under Regulation B/C25.7.2.6 shall apply.

**B/C25.6.1** Sea/water temperature shall always be included in reports from sea stations, when data are available. \[35.2.5\]

**B/C25.7 Temperature, dewpoint and wind data at pressure levels**

> Temperature, dewpoint and wind data at pressure levels obtained during the radiosonde ascent shall be included in descending order with respect to pressure. Data at each pressure level shall be included only once. For example, if a significant level with respect to air temperature and relative humidity and a standard isobaric surface coincide, data for that level shall be included only once, the multiple attributes being indicated by Extended vertical sounding significance (Flag table 0 08 042) as specified in Regulation B/C25.7.2.2.
>
> Note: If data are produced and collected in traditional TEMP codes, the order of pressure levels may correspond to the order of levels in Parts A, B, C and D, when converted into BUFR or CREX. In this case, data at a level may be included more than once.

**B/C25.7.1 Number of reported pressure levels**

> The number of reported pressure levels shall be indicated by Extended delayed descriptor replication factor 0 31 002 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.
>
> Notes:
>
> \(1) The number of pressure levels shall never be set to a missing value.
>
> \(2) The number of pressure levels shall be set to a positive value in a NIL report.
>
> \(3) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C25.7.1.1** All required data from the entire radiosonde ascent shall be reported in a BUFR (or CREX) message that shall be produced when the sounding is completed. In interest of timely data delivery, however, a BUFR (or CREX) message should be sent when level 100 hPa is reached.

**B/C25.7.2 Temperature, dewpoint and wind data at a pressure level with radiosonde position \<3 03 054\>**

**B/C25.7.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C25.3, and shall be reported in seconds if available.

**B/C25.7.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> This datum shall be used to specify vertical sounding significance in the following way:
>
> \(a) Bit No. 1 set to 1 indicates surface (see Regulation B/C25.8.1);
>
> \(b) Bit No. 2 set to 1 indicates a standard level (see Regulation B/C25.8.2);
>
> \(c) Bit No. 3 set to 1 indicates a tropopause level (see Regulation B/C25.8.3);
>
> \(d) Bit No. 4 set to 1 indicates a maximum wind level (see Regulation B/C25.8.4);
>
> \(e) Bit No. 5 set to 1 indicates a level significant with respect to temperature (see Regulation B/C25.8.5);
>
> \(f) Bit No. 6 set to 1 indicates a level significant with respect to relative humidity (see Regulation B/C25.8.6);
>
> \(g) Bit No. 7 set to 1 indicates a level significant with respect to wind (see Regulation B/C25.8.7);
>
> \(h) Bit No. 8 set to 1 indicates beginning of missing temperature data and bit No. 9 set to 1 indicates end of missing temperature data (see Regulation B/C25.8.8);
>
> \(i) Bit No. 10 set to 1 indicates beginning of missing humidity data and bit No. 11 set to 1 indicates end of missing humidity data (see Regulation B/C25.8.9);
>
> \(j) Bit No. 12 set to 1 indicates beginning of missing wind data bit No. 13 set to 1 indicates end of missing wind data (see Regulation B/C25.8.10);
>
> \(k) Bit No. 14 set to 1 indicates the top of wind sounding;
>
> \(l) Bit No. 15 set to 1 indicates a level determined by regional decision;
>
> \(m) All bits set to 0 indicate a level determined by national decision or a level of no significance that has been included when high-resolution data are reported;
>
> \(n) All bits set to 1 indicate a missing value.

**B/C25.7.2.3 Pressure**

> Pressure (0 07 004) shall be reported in pascals (with precision in tens of pascals).

**B/C25.7.2.4 Geopotential height**

> Geopotential height of the level (0 10 009) shall be reported in geopotential metres.

**B/C25.7.2.5 Radiosonde drift -- latitude and longitude displacements**

> Latitude displacement (0 05 015) represents the latitude offset from the latitude of the launch site specified in Regulation B/C25.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site specified in Regulation B/C25.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available.

**B/C25.7.2.6 Temperature**

> Temperature (0 12 101) shall be reported in kelvin (with precision in hundredths of a kelvin); if produced in CREX, in degrees Celsius (with precision in hundredths of a degree Celsius). Temperature data shall be reported with precision in hundredths of a degree even if they are measured with the accuracy in tenths of a degree.
>
> Notes:
>
> \(1) This requirement is based on the fact that conversion from the Kelvin to the Celsius scale has often resulted into distortion of the data values.
>
> \(2) Temperature t (in degrees Celsius) shall be converted into temperature T (in kelvin) using equation: T = t + 273.15.

**B/C25.7.2.7 Dewpoint temperature**

> Dewpoint temperature (0 12 103) shall be reported in kelvin (with precision in hundredths of a kelvin); if produced in CREX, in degrees Celsius (with precision in hundredths of a degree Celsius).
>
> Note: Notes 1 and 2 under Regulation B/C25.7.2.6 shall apply.

**B/C25.7.2.7.1** Dewpoint temperature data shall be derived using the function (or a near equivalent) for a relationship between saturation vapour pressure over water and air temperature (specified in the *Technical Regulations (WMO-No. 49)*). Dewpoint temperature data shall not be reported when the air temperature is outside the range stated by WMO for the application of the function; a lesser range may be used as a national practice. \[35.3.1.1\]

**B/C25.7.2.8 Wind direction** **and speed**

> The wind direction (0 11 001) shall be reported in degrees true and the wind speed (0 11 002) shall be reported in metres per second (with precision in tenths of a metre per second).
>
> Note: Wind direction measured at a station within 1° of the North Pole or within 1° of the South Pole shall be reported in such a way that the azimuth ring shall be aligned with its zero coinciding with the Greenwich 0° meridian.

**B/C25.7.2.8.1** When during an ascent the pressure data can no longer be obtained, but wind data can be obtained, the wind data so obtained shall not be reported in the BUFR (or CREX) message in which data are described by the common sequence 3 09 052. These wind data so obtained may be reported using BUFR template TM 309051 suitable PILOT, PILOT SHIP or PILOT MOBIL data. \[35.1.5\]

**B/C25.7.2.8.2** Only wind data obtained from the radiosonde ascent by either visual or electronic means shall be included in the BUFR (or CREX) message in which data are described by the common sequence 3 09 052. Wind data obtained by means other than a radiosonde-type ascent shall not be included in a message under common sequence 3 09 052. \[35.1.6\]

**B/C25.8 Criteria for reporting standard and significant levels**

**B/C25.8.1 Surface**

> The surface level shall be always reported.
>
> Note: The value of Extended vertical sounding significance 0 08 042 at the surface level shall indicate that this level is also a level significant with respect to temperature, relative humidity and wind, i.e. not only bit No. 1 but also bits Nos. 5, 6 and 7 shall be set to 1.

**B/C25.8.2 Standard levels**

**B/C25.8.2.1** The standard levels of 1 000, 925, 850, 700, 500, 400, 300, 250, 200, 150, 100, 70, 50, 30, 20 and 10 hPa shall be reported in ascending order with respect to altitude. \[35.2.2.1\]

**B/C25.8.2.2** When the geopotential of a standard level is lower than the altitude of the reporting station, the time displacement, latitude displacement and longitude displacement for that level shall be set to zero and the air temperature, dewpoint temperature and wind data for that level shall be reported as missing values. \[35.2.2.2\]

**B/C25.8.2.3** When air temperature, dewpoint temperature or wind data at a standard level are not available, the corresponding entries for that level shall be reported as missing values.

**B/C25.8.2.4** Whenever it is desired to extrapolate a sounding for the computation of the geopotential at a standard level, the following rules shall apply:

> \(a) Extrapolation is permissible if, and only if, the pressure difference between the minimum pressure of the sounding and the isobaric surface for which the extrapolated value is being computed does not exceed one quarter of the pressure at which the extrapolated value is desired, provided the extrapolation does not extend through a pressure interval exceeding 25 hPa;
>
> \(b) For the purpose of geopotential calculation, and for this purpose only, the sounding will be extrapolated, using two points only of the sounding curve on a T-log p diagram, namely that at the minimum pressure reached by the sounding and that at the pressure given by the sum of this minimum pressure and the pressure difference, mentioned in (a) above.
>
> \[35.2.2.4\]

**B/C25.8.3 Tropopause level(s)**

**B/C25.8.3.1** When a tropopause (one or more) is observed, the corresponding number of levels shall be included (indicated by 0 08 042 -- bit No. 3 set to 1).

> Note: For a definition of tropopause, see the *International Meteorological Vocabulary (WMO-No. 182).*
>
> \[35.2.3.1\]

**B/C25.8.3.2** When no tropopause data are observed, no level shall be indicated by bit No. 3 of 0 08 042 set to 1. \[35.2.3.2\]

**B/C25.8.4 Maximum wind level(s)**

**B/C25.8.4.1** When a maximum wind level (one or more) is reported, the corresponding number of levels shall be included in the report indicated by 0 08 042 -- bit No. 4 set to 1*.* \[35.2.4.1\]

> Notes:
>
> \(1) Criteria for determining maximum wind levels are given in Regulations B/C25.8.4.3 and B/C25.8.4.4 below. \[35.2.4.1\]
>
> \(2) As a maximum wind level is also a level significant with respect to wind, bit No. 7 as well as bit No. 4 shall be set to 1 in the Extended vertical sounding significance 0 08 042.

**B/C25.8.4.2** When no maximum wind level is observed, no level shall be indicated by bit No. 4 of 0 08 042 set to 1. \[35.2.4.2\]

**B/C25.8.4.3** A maximum wind level:

> \(a) Shall be determined by consideration of the list of significant levels for wind speed, as obtained by means of the relevant recommended or equivalent national method (see the Note under Regulation B/C25.8.7.2) and *not* by consideration of the original wind-speed curve;
>
> \(b) Shall be located above the 500-hPa isobaric surface and shall correspond to a speed of more than 30 metres per second.
>
> Note: A maximum wind level is defined as a level at which the wind speed is greater than that observed immediately above and below that level.
>
> \[35.2.4.1\], \[32.2.3.1\]

**B/C25.8.4.4** Whenever more than one maximum wind level exists, these levels shall be reported as follows:

> \(a) The level of greatest maximum wind speed shall be always included;
>
> \(b) The other levels shall be included in the report only if their speed exceeds those of the two adjacent minima by at least 10 metres per second;
>
> \(c) Furthermore, the highest level attained by the sounding shall be indicated as a maximum wind level, provided:
>
> \(i) It satisfies the criteria set forth in Regulation B/C25.8.4.3 above;
>
> \(ii) It constitutes the level of the greatest speed of the whole sounding.
>
> \[35.2.4.1\], \[32.2.3.2\]

**B/C25.8.4.5** If the top of the wind sounding corresponds to the highest wind speed observed throughout the ascent, this level shall be indicated by 0 08 042 -- bit No. 4 set to 1 (maximum wind level), bit No. 7 set to 1 (level significant with respect to wind) and bit No. 14 set to 1 (top of wind sounding).

> Note: For the purpose of the above regulation, the "top of the wind sounding" is to be understood as the highest level for which wind data are available.
>
> \[35.2.4.3\]

**B/C25.8.5 Levels significant with respect to temperature**

**B/C25.8.5.1** The reported significant levels *alone* shall make it possible to reconstruct the air temperature profile within the limits of the criteria specified.

> If the criteria for determination of significant levels with respect to air temperature are satisfied at a particular point of altitude, data for all variables (if available) shall be reported for that level.
>
> \[35.3.1.1\]

**B/C25.8.5.2** The following shall be included as "mandatory" significant temperature levels:

> \(a) Surface level and the highest level of the sounding;
>
> \(b) A level between 110 and 100 hPa;
>
> \(c) Bases and tops of inversions and isothermal layers which are at least 20 hPa thick, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher;
>
> \(d) Bases and tops of inversion layers which are characterized by a change in temperature of at least 2.5 ºC, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher.
>
> Note: The inversion layers of (c) and (d) may be comprised of several thinner inversion layers separated by thin layers of temperature lapse. To allow for this situation, the tops of the inversion layers of (c) and (d) shall each be at a level such that no further inversion layers, whether thick or thin, shall occur for at least 20 hPa above the level.
>
> \[35.3.1.2\]

**\
**

**B/C25.8.5.3** The following shall be included as "additional" significant levels. They shall be selected in the order given, thereby giving priority to representing the temperature profile. As far as possible, these additional levels shall be the actual levels at which prominent changes in the lapse rate of air temperature occur:

> \(a) Levels which are necessary to ensure that the temperature obtained by linear interpolation (on a T-log P or essentially similar diagram) between adjacent significant levels shall not depart from the observed temperature by more than 1 ºC below the first significant level reported above the 300-hPa level or the first tropopause, whichever level is the lower, or by more than 2 ºC thereafter;
>
> \(b) Levels which are necessary to limit the interpolation error on diagrams other than T-log P. These levels shall be such that the pressure at one significant level divided by the pressure of the preceding significant layer shall exceed 0.6 for levels up to the first tropopause and shall be determined by use of the method for selecting additional levels but with application of tighter criteria.
>
> \[35.3.1.3\]

**B/C25.8.5.4** When a significant level with respect to air temperature and a standard level coincide, data for that level shall be reported only once.

**B/C25.8.6 Levels significant with respect to relative humidity**

**B/C25.8.6.1** The reported significant levels *alone* shall make it possible to reconstruct the relative humidity profiles within the limits of the criteria specified.

> If the criteria for determination of significant levels with respect to relative humidity are satisfied at a particular point of altitude, data for all variables (if available) shall be reported for that level.
>
> \[35.3.1.1\]

**B/C25.8.6.2** The following shall be included as "mandatory" significant humidity levels:

> \(a) Surface level and the highest level of the sounding;
>
> \(b) A level between 110 and 100 hPa;
>
> \(c) Bases and tops of inversions and isothermal layers which are at least 20 hPa thick, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher;
>
> \(d) Bases and tops of inversion layers which are characterized by a change in relative humidity of at least 20 per cent, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher.
>
> Note: The Note under Regulation B/C25.8.5.2 shall apply.
>
> \[35.3.1.2\]

**B/C25.8.6.3** The following shall be included as "additional" significant levels. They shall be selected in the order given, thereby giving priority to representing the temperature profile. As far as possible, these additional levels shall be the actual levels at which prominent changes in the lapse rate of air temperature occur:

> \(a) Levels which are necessary to ensure that the relative humidity obtained by linear interpolation between adjacent significant levels shall not depart by more than 15 per cent from the observed values. (The criterion of 15 per cent refers to an amount of relative humidity and NOT to the percentage of the observed value, e.g. if an observed value is 50 per cent, the interpolated value shall lie between 35 per cent and 65 per cent.);
>
> \(b) Levels which are necessary to limit the interpolation error on diagrams other than T-log P. These levels shall be such that the pressure at one significant level divided by the pressure of the preceding significant layer shall exceed 0.6 for levels up to the first tropopause and shall be determined by use of the method for selecting additional levels but with application of tighter criteria.
>
> \[35.3.1.3\]

**B/C25.8.6.4** When a significant layer with respect to relative humidity and a standard level coincide, data for that level shall be reported only once.

**B/C25.8.7 Levels significant with respect to wind**

**B/C25.8.7.1** Significant wind levels shall be chosen so that the data from them *alone* shall make it possible to reconstruct the wind profile with sufficient accuracy for practical use. \[35.3.2.1\]

> If the criteria for determination of significant levels with respect to wind speed and direction are satisfied at a particular point of altitude, data for all variables (if available) shall be reported for that level.

**B/C25.8.7.2** Criteria for determining significant levels with respect to changes in wind speed and direction:

> \(a) The direction and speed curves (in function of the log of pressure or altitude) can be reproduced with their prominent characteristics;
>
> \(b) These curves can be reproduced with the accuracy of at least 10 degrees true for direction and five metres per second for speed.
>
> Note: To satisfy these criteria, the following method of successive approximations is recommended, but other methods of attaining equivalent results may suit some national practices better and may be used:
>
> \(i) The surface level and highest level for which wind data are available constitute the first and the last significant levels. The deviation from the linearly interpolated values between these two levels is then considered. If no direction deviates by more than 10 degrees true and no speed by more than five metres per second, no other significant level need be reported. Whenever one parameter deviates by more than the limit specified in paragraph (b) above the level of greatest deviation becomes a supplementary significant level for both parameters;
>
> \(ii) The additional significant levels so introduced divide the sounding into two layers. In each separate layer, the deviation from the linearly interpolated values between the base and the top are then considered. The process used in paragraph (i) above is repeated and yields other significant levels. These additional levels in turn modify the layer distribution, and the method is applied again until any level is approximated to the above-mentioned specified values.
>
> \[35.3.2.1\], \[32.3.1.1\]

**B/C25.8.8 Beginning and end of missing temperature data**

**B/C25.8.8.1** A layer for which temperature data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 20 hPa thick. The boundary levels are the levels closest to the bottom and the top of the layer for which temperature data are available. The boundary levels are not required to meet "significant temperature level" criteria. \[35.3.1.6\]

**B/C25.8.9 Beginning and end of missing humidity data**

**B/C25.8.9.1** A layer for which dewpoint temperature data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 20 hPa thick. The boundary levels are the levels closest to the bottom and the top of the layer for which dewpoint temperature data are available. The boundary levels are not required to meet "significant humidity level" criteria. \[35.3.1.6\]

**B/C25.8.10 Beginning and end of missing wind data**

**B/C25.8.10.1** A layer for which wind data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 50 hPa thick. The boundary levels are the levels closest to the bottom and the top of the layer for which the observed data are available. The boundary levels are not required to meet "significant wind level" criteria. \[35.3.2.2\]

**B/C25.9 Wind shear data**

**B/C25.9.1 Number and order of levels for which wind shear is reported**

**B/C25.9.1.1** The number of levels with wind shear **data** shall be indicated by Delayed descriptor replication factor 0 31 001 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.

> Notes:
>
> \(1) The number of **levels** with wind shear **data** shall never be set to a missing value.
>
> \(2) The number of **levels** with wind shear **data** shall be set to a positive value in a NIL report.
>
> \(3) The number of **levels** with wind shear **data** shall be set to zero if data for vertical wind shear are not computed and required. \[35.2.4.4\]
>
> \(4) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C25.9.1.2** Whenever wind shear data are reported for more than one level, these maximum wind levels shall be included in the same order as in the sequence \<3 03 054\>, i.e. in descending order with respect to pressure.

**B/C25.9.2 Wind shear data at a pressure level with radiosonde position \<3 03 051\>**

**B/C25.9.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C25.3, and shall be reported in seconds if available.

**B/C25.9.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> A level, for which wind shear data are reported, shall be indicated by vertical sounding significance 0 08 042 -- bit No. 4 set to 1 (maximum wind level) and by bit No. 7 set to 1 (level significant with respect to wind). Moreover, if the top of the wind sounding corresponds to the highest wind speed observed throughout the ascent, this level shall be indicated also by bit No. 14 set to 1 (top of wind sounding).

**B/C25.9.2.3 Pressure**

> Pressure (0 07 004) shall be reported in pascals with precision in tens of pascals.

**\
**

**B/C25.9.2.4 Latitude and longitude displacements**

> Latitude displacement (0 05 015) represents the latitude offset from the latitude of the launch site specified in Regulation B/C25.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site specified in Regulation B/C25.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available.

**B/C25.9.2.5 Wind shear data**

> Absolute wind shear **in 1 km layer below (0 11 061) and a**bsolute wind shear **in 1‑km layer above (0 11 062)** shall be reported in metres per second (with precision in tenths of a metre per second)**, if** data for vertical wind shear are computed and required. \[35.2.4.4\]

**B/C25.10 Data required by regional or national reporting practices**

> If regional or national reporting practices require inclusion of temperature, humidity and/or wind data at additional levels, these data shall be reported using sequence \<3 03 054\> for Temperature, dewpoint, wind at a pressure level. Regulation B/C25.7 shall apply.
>
> Notes:
>
> \(1) A level determined by regional decision shall be indicated by Extended vertical sounding significance 0 08 042 -- bit No. 15 set to 1.
>
> \(2) A level determined by national decision shall be indicated by Extended vertical sounding significance 0 08 042 -- all bits set to 0.

**B/C25.10.1 Additional data required by reporting practices in RA I**

> Temperature, dewpoint, wind data at additional levels shall be reported in compliance with Regulation B/C25.10.

**B/C25.10.2 Additional data required by reporting practices in RA II**

**B/C25.10.2.1** No additional data are required by regional reporting practices in RA II.

**B/C25.10.2.2** The inclusion of wind shear data shall be left to national decision. Members are recommended to include these data as often as possible. \[2/35.2\]

**B/C25.10.3 Additional data required by reporting practices in RA III**

> No regional requirements are indicated for reporting TEMP, TEMP SHIP and TEMP MOBIL data in RA III.

**B/C25.10.4 Additional data required by reporting practices in RA IV**

**B/C25.10.4.1** When available, temperature, dewpoint, wind data for levels 7, 5, 3, 2 and 1 hPa shall be reported in compliance with Regulation B/C25.10. \[4/35.2.1\]

**B/C25.10.4.2** When required, additional information shall be reported using RA IV BUFR template for data representation of TEMP, TEMP SHIP and TEMP MOBIL data as shown in Annex I to Part B/C25. \[4/35.1\], \[4/35.2.2\]

**B/C25.10.5 Additional data required by reporting practices in RA V**

> No regional requirements are indicated for reporting TEMP, TEMP SHIP and TEMP MOBIL data in RA V.

**B/C25.10.6 Additional data required by reporting practices in RA VI**

**B/C25.10.6.1** The inclusion of wind shear data shall be left to national decision. Members are recommended to include these data as often as possible. \[6/35.1\]

**B/C25.10.6.2** Wind direction and speed shall be reported:

> \(i) For 900 or 1 000 metres above the surface;
>
> \(ii) For 800 hPa level;
>
> \(iii) For 600 hPa level.
>
> \[6/35.2.2\]

**\
**

**ANNEX I TO B/C25** -- **Regional regulations for reporting TEMP, TEMP SHIP and TEMP MOBIL data in TDCF**

**RA IV BUFR template for TEMP, TEMP SHIP and TEMP MOBIL data**

The RA IV Regional coding procedures for TEMP and TEMP SHIP data require data representation of additional information that is specified in the *Manual on Codes* (WMO-No. 306), Volume II, by supplementary groups 101A~df~A~df~ (Code table 421 for A~df~A~df~ -- Form of additional data reported). The sequence \<3 09 052\> for representation of TEMP, TEMP SHIP and TEMP MOBIL data is supplemented by additional parameters to allow data representation of this information, if it is required.

+--------------+-----------------------------------------------------------------------------------------+-------------+
|              |                                                                                         | Unit, scale |
+==============+=========================================================================================+=============+
| **3 09 052** | **Sequence for representation of TEMP, TEMP SHIP and TEMP MOBIL observation type data** |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              |                                                                                         |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              | **Reason for no report or incomplete report**                                           |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 35 035** | Reason for termination                                                                  | Code table  |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              | **Corrected data**                                                                      |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **1 04 000** | Delayed replication of 4 descriptors                                                    |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 31 001** | Delayed descriptor replication factor                                                   | Numeric     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **2 04 001** | Add associated field (of 1 bit in length)                                               |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 31 021** | Associated field significance = 21 (indicator of correction)                            | Code table  |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              | Associated field set to 1 (corrected value)                                             |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **3 03 054** | **Temperature, dewpoint and wind data at a pressure level with radiosonde position**    |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **2 04 000** | Cancel Add associated field                                                             |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 08 042** | Extended vertical sounding significance = missing (to cancel the previous value)        | Flag table  |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              | **Stability index and mean wind data**                                                  |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 13 047** | **Modified Showalter stability index**                                                  | K           |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 11 044** | **Mean wind direction for surface -- 1** **500 m (5 000 feet)**                         | Degree true |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 11 045** | **Mean wind speed for surface -- 1** **500 m (5 000 feet)**                             | m s^--1^, 1 |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 11 054** | **Mean wind direction for 1** **500 m -- 3** **000 m**                                  | Degree true |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 11 055** | **Mean wind speed for 1** **500 m -- 3** **000 m**                                      | m s^--1^, 1 |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              | **Doubtful data**                                                                       |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **1 12 000** | Delayed replication of 12 descriptors                                                   |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 31 001** | Delayed descriptor replication factor                                                   | Numeric     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **1 11 002** | Replicate 11 descriptors 2 times                                                        |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 04 086** | Long time period or displacement (since launch time)                                    | Second      |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 08 040** | Flight level significance                                                               | Code table  |
|              |                                                                                         |             |
|              | In the 1st replication = 4 (Begin doubtful temperature, height data)                    |             |
|              |                                                                                         |             |
|              | In the 2nd replication = 9 (End doubtful temperature, height data)                      |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 07 004** | Pressure                                                                                | Pa, --1     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 05 015** | Latitude displacement (high accuracy) -- since launch site                              | Degree, 5   |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 06 015** | Longitude displacement (high accuracy) -- since launch site                             | Degree, 5   |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **1 01 000** | Delayed replication of 1 descriptor                                                     |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 31 000** | Short delayed descriptor replication factor                                             | Numeric     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 10 009** | Geopotential height                                                                     | gpm         |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **1 01 000** | Delayed replication of 1 descriptor                                                     |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 31 000** | Short delayed descriptor replication factor                                             | Numeric     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 12 101** | Temperature/air temperature                                                             | K, 2        |
+--------------+-----------------------------------------------------------------------------------------+-------------+
|              | **Extrapolated geopotential data**                                                      |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **1 08 000** | Delayed replication of 8 descriptors                                                    |             |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 31 001** | Delayed descriptor replication factor                                                   | Numeric     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 04 086** | Long time period or displacement (since launch time)                                    | Second      |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 08 040** | Flight level significance = 31 (Incremented height level (generated))                   | Code table  |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 07 004** | Pressure                                                                                | Pa, --1     |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 05 015** | Latitude displacement (high accuracy) -- since launch site                              | Degree, 5   |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 06 015** | Longitude displacement (high accuracy) -- since launch site                             | Degree, 5   |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 10 009** | Geopotential height                                                                     | gpm         |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 11 001** | **Wind direction**                                                                      | Degree true |
+--------------+-----------------------------------------------------------------------------------------+-------------+
| **0 11 002** | **Wind speed**                                                                          | m s^--1^, 1 |
+--------------+-----------------------------------------------------------------------------------------+-------------+

Note: The "Modified Showalter stability index" 0 13 047 is defined as the temperature difference between the ambient 500 hPa temperature and the temperature a parcel of air, initially at a selected base level, would have if brought from its condensation level to the 500 hPa surface by a moist adiabatic process. Positive values denote stable conditions, while negative values denote unstable conditions. The base level is 850 hPa, 800hPa or 750 hPa, if the station elevation is less than 1 000, 1 000 to 1 400 or 1 401 to 2 000 gpm above mean sea level, respectively.

**ANNEX II TO B/C25 -- List of parameters for representation of additional information on sounding instrumentation**

Additional information on radiosonde ascent

                        (Additional information on radiosonde ascent)
  ---------- ---------- -------------------------------------------------
  3 01 128   0 01 081   Radiosonde serial number
             0 01 082   Radiosonde ascension number
             0 01 083   Radiosonde release number
             0 01 095   Observer identification
             0 02 015   Radiosonde completeness
             0 02 016   Radiosonde configuration
             0 02 017   Correction algorithms for humidity measurements
             0 02 066   Radiosonde ground receiving system
             0 02 067   Radiosonde operating frequency
             0 02 080   Balloon manufacturer
             0 02 081   Type of balloon
             0 02 082   Weight of balloon
             0 02 083   Type of balloon shelter
             0 02 084   Type of gas used in balloon
             0 02 085   Amount of gas used in balloon
             0 02 086   Balloon flight train length
             0 02 095   Type of pressure sensor
             0 02 096   Type of temperature sensor
             0 02 097   Type of humidity sensor
             0 02 103   Radome
             0 02 191   Geopotential height calculation
             0 25 061   Software identification and version number
             0 35 035   Reason for termination

--------------------------
