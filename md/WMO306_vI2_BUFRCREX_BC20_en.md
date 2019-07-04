**B/C20** -- **Regulations for reporting PILOT, PILOT SHIP and PILOT MOBIL data in TDCF**

**General**

> A BUFR (or CREX) message should be sent when the 100-hPa level is reached. In any case, a BUFR (or CREX) message shall be produced when the sounding is completed containing data from the entire sounding.

**BUFR templates for wind vertical profiles suitable for PILOT, PILOT SHIP and PILOT MOBIL observation data:**

**TM 309050 -- BUFR template for wind vertical profiles with pressure as the vertical coordinate**

  -------------- -------------- -------------------------------------------------------------------------------------------------------------------------------------
                                **Sequence for representation of PILOT, PILOT SHIP and PILOT MOBIL observation type data with pressure as the vertical coordinate**
  **3 09 050**   **3 01 110**   **Identification of launch site and instrumentation for wind measurements**
                 **3 01 113**   **Date/time of launch**
                 **3 01 114**   **Horizontal and vertical coordinates of launch site**
                 **1 01 000**   **Delayed replication of 1 descriptor**
                 **0 31 002**   **Extended delayed descriptor replication factor**
                 **3 03 050**   **Wind data at a pressure level with radiosonde position**
                 1 01 000       **Delayed replication of 1 descriptor**
                 0 31 001       **Delayed descriptor replication factor**
                 **3 03 051**   **Wind shear data at a pressure level with radiosonde position**
  -------------- -------------- -------------------------------------------------------------------------------------------------------------------------------------

**TM 309051** -- **BUFR template for wind vertical profiles with height as the vertical coordinate**

  -------------- -------------- -----------------------------------------------------------------------------------------------------------------------------------
                                **Sequence for representation of PILOT, PILOT SHIP and PILOT MOBIL observation type data with height as the vertical coordinate**
  **3 09 051**   **3 01 110**   **Identification of launch site and instrumentation for wind measurements**
                 **3 01 113**   **Date/time of launch**
                 **3 01 114**   **Horizontal and vertical coordinates of launch site**
                 **1 01 000**   **Delayed replication of 1 descriptor**
                 **0 31 002**   **Extended delayed descriptor replication factor**
                 **3 03 052**   **Wind data at a height level with radiosonde position**
                 1 01 000       **Delayed replication of 1 descriptor**
                 0 31 001       **Delayed descriptor replication factor**
                 **3 03 053**   **Wind shear data at a height level with radiosonde position**
  -------------- -------------- -----------------------------------------------------------------------------------------------------------------------------------

**BUFR template TM 309050** **for wind vertical profiles *(with pressure as the vertical coordinate)*** is further expanded as follows:

  ---------------------------------------------------------------------------------------------------------------------
                                                                                                          Unit, scale
  -------------- ---------- ----------------------------------------------------------------------------- -------------
                            **Identification of launch site and instrumentation for wind measurements**   

  **3 01 110**   3 01 001   WMO block and station numbers                                                 Numeric

                 0 01 011   Ship or mobile land station identifier                                        CCITT IA5

                 0 02 011   Radiosonde type                                                               Code table

                 0 02 014   Tracking technique/status of system used                                      Code table

                 0 02 003   Type of measuring equipment used                                              Code table

                            **Date/time of launch**                                                       

  **3 01 113**   0 08 021   Time significance (= 18 Launch time)                                          Code table

                 3 01 011   Year                                                                          Year

                            Month                                                                         Month

                            Day                                                                           Day

                 3 01 013   Hour                                                                          Hour

                            Minute                                                                        Minute

                            Second                                                                        Second

                            **Horizontal and vertical coordinates of launch site**                        

  **3 01 114**   3 01 021   Latitude/longitude (high accuracy)                                            Degree, 5

                 0 07 030   Height of station ground above mean sea level                                 m, 1

                 0 07 031   Height of barometer above mean sea level                                      m, 1

                 0 07 007   Height (of release of sonde above mean sea level)                             m

                 0 33 024   Station elevation quality mark (for mobile stations)                          Code table

                            **Wind data at pressure levels**                                              

  **1 01 000**              Delayed replication of 1 descriptor                                           

  **0 31 002**              Extended delayed descriptor replication factor                                Numeric

                            *Wind data at a pressure level with radiosonde\                               
                            position*                                                                     

  **3 03 050**   0 04 086   Long time period or displacement (since launch time)                          Second

                 0 08 042   Extended vertical sounding significance                                       Flag table

                 0 07 004   Pressure                                                                      Pa, --1

                 0 05 015   Latitude displacement (high accuracy) -- since launch site                    Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site                   Degree, 5

                 0 11 001   Wind direction                                                                Degree true

                 0 11 002   Wind speed                                                                    m s^--1^, 1

                            **Wind shear data**                                                           

  **1 01 000**              Delayed replication of 1 descriptor                                           

  **0 31 001**              Delayed descriptor replication factor                                         Numeric

                            *Wind shear data at a pressure level with radiosonde\                         
                            position*                                                                     

  **3 03 051**   0 04 086   Long time period or displacement (since launch time)                          Second

                 0 08 042   Extended vertical sounding significance                                       Flag table

                 0 07 004   Pressure                                                                      Pa, --1

                 0 05 015   Latitude displacement (high accuracy) -- since launch site                    Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site                   Degree, 5

                 0 11 061   Absolute wind shear in 1 km layer below                                       m s^--1^, 1

                 0 11 062   Absolute wind shear in 1 km layer above                                       m s^--1^, 1
  ---------------------------------------------------------------------------------------------------------------------

Notes:

\(1) Time of launch 3 01 013 shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry for seconds shall be put to zero.

\(2) Long time displacement 0 04 086 represents the time offset from the launch time 3 01 013 (in seconds).

\(3) Latitude displacement 0 05 015 represents the latitude offset from the latitude of the launch site. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site.

\(4) If maximum wind data and/or wind shear data are reported with height as the vertical coordinate in Parts A or C of Pilot report, while the whole vertical wind profile is reported with pressure as the vertical coordinate, the data may be converted into BUFR using sequence 3 09 050 because the maximum wind data are as significant levels also included in Parts B or D (being identified by pressure as the vertical coordinate), provided that Part B and D are available when the entire wind profile is produced in BUFR or CREX.

**BUFR template TM 309051 for wind vertical profiles *(with height as the vertical coordinate)*** is further expanded as follows:

  ---------------------------------------------------------------------------------------------------------------------
                                                                                                          Unit, scale
  -------------- ---------- ----------------------------------------------------------------------------- -------------
                            **Identification of launch site and instrumentation for wind measurements**   

  **3 01 110**   3 01 001   WMO block and station numbers                                                 Numeric

                 0 01 011   Ship or mobile land station identifier                                        CCITT IA5

                 0 02 011   Radiosonde type                                                               Code table

                 0 02 014   Tracking technique/status of system used                                      Code table

                 0 02 003   Type of measuring equipment used                                              Code table

                            **Date/time of launch**                                                       

  **3 01 113**   0 08 021   Time significance ( = 18 Launch time)                                         Code table

                 3 01 011   Year                                                                          Year

                            Month                                                                         Month

                            Day                                                                           Day

                 3 01 013   Hour                                                                          Hour

                            Minute                                                                        Minute

                            Second                                                                        Second

                            **Horizontal and vertical coordinates of launch site**                        

  **3 01 114**   3 01 021   Latitude/longitude (high accuracy)                                            Degree, 5

                 0 07 030   Height of station ground above mean sea level                                 m, 1

                 0 07 031   Height of barometer above mean sea level                                      m, 1

                 0 07 007   Height (of release of sonde above mean sea level)                             m

                 0 33 024   Station elevation quality mark (for mobile stations)                          Code table

                            **Wind data at heights**                                                      

  **1 01 000**              Delayed replication of 1 descriptor                                           

  **0 31 002**              Extended delayed descriptor replication factor                                Numeric

                            *Wind data at a height level with radiosonde position*                        

  **3 03 052**   0 04 086   Long time period or displacement (since launch time)                          Second

                 0 08 042   Extended vertical sounding significance                                       Flag table

                 0 07 009   Geopotential height                                                           gpm

                 0 05 015   Latitude displacement (high accuracy) -- since launch site                    Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site                   Degree, 5

                 0 11 001   Wind direction                                                                Degree true

                 0 11 002   Wind speed                                                                    m s^--1^, 1

                            **Wind shear data at a height level with radiosonde position**                

  **1 01 000**              Delayed replication of 1 descriptor                                           

  **0 31 001**              Delayed descriptor replication factor                                         Numeric

                            *Wind shear data at a height level with radiosonde\                           
                            position*                                                                     

  **3 03 053**   0 04 086   Long time period or displacement (since launch time)                          Second

                 0 08 042   Extended vertical sounding significance                                       Flag table

                 0 07 009   Geopotential height                                                           gpm

                 0 05 015   Latitude displacement (high accuracy) -- since launch site                    Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site                   Degree, 5

                 0 11 061   Absolute wind shear in 1 km layer below                                       m s^--1^, 1

                 0 11 062   Absolute wind shear in 1 km layer above                                       m s^--1^, 1
  ---------------------------------------------------------------------------------------------------------------------

Notes:

\(1) Time of launch 3 01 013 shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry for seconds shall be put to zero.

\(2) Long time displacement 0 04 086 represents the time offset from the launch time 3 01 013 (in seconds).

\(3) Latitude displacement 0 05 015 represents the latitude offset from the latitude of the launch site. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site.

**\
Regulations:**

**B/C20.1 Section 1 of BUFR or CREX**

**B/C20.2 Identification of launch site and instrumentation for wind measurement**

**B/C20.3 Date/time of launch**

B/C20.4 Horizontal and vertical coordinates **of launch site**

**B/C20.5** Wind data at pressure levels

**B/C20.6** Wind data at height levels

**B/C20.7** Criteria for reporting standard and significant levels

**B/C20.8** Wind shear data at pressure levels

**B/C20.9** Wind shear data at heights

**B/C20.10 Data required by regional or national reporting practices**

**B/C20.1 Section 1 of BUFR or CREX**

**B/C20.1.1 Entries required in Section 1 of BUFR**

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
> -- **Data category (= 002 for all PILOT type data);**
>
> -- **International data sub-category (see Notes 1 and 2);**
>
> -- **Local data sub-category;**
>
> -- **Version number of master table;**
>
> -- **Version number of local tables;**
>
> -- **Year (of standard time), (year of the century up to BUFR edition 3);**
>
> -- **Month (of standard time);**
>
> -- **Day (when standard time, = YY in the** abbreviated telecommunication header **for all PILOT type data**);
>
> -- **Hour (when standard time, = GG in the** abbreviated telecommunication header**, e.g. = 00, 06, 12 or 18** **for all PILOT type data**);
>
> -- **Minute (when standard time, = 00 for all PILOT type data);**
>
> -- **Second (= 0) (see Note 1).**
>
> **Notes:**
>
> **(1) Inclusion of this entry is required starting with BUFR edition 4.**
>
> **(2) If required, the international data sub-category shall be included at all observation times as follows:**
>
> **= 001 for PILOT data;**
>
> **= 002 for PILOT SHIP data;**
>
> **= 003 for PILOT MOBIL data.**
>
> **(3) If an NMHS performs conversion of PILOT, PILOT SHIP or PILOT MOBIL data produced by another NMHS, o**riginating centre in Section 1 shall indicate **the converting centre and o**riginating sub-centre shall indicate the **producer of PILOT, PILOT SHIP or PILOT MOBIL bulletins. Producer of PILOT, PILOT SHIP or PILOT MOBIL bulletins shall be specified in Common Code table C-12 as a sub-centre of the originating centre, i.e. of the NMHS executing the conversion.**

**B/C20.1.2 Entries required in Section 1 of CREX**

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
> -- **Data category (= 002 for all PILOT type data);**
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
> -- **Day (when standard time, = YY in the** abbreviated telecommunication header **for all PILOT type data**) **(see Note 1);**
>
> -- **Hour (when standard time, = GG in the** abbreviated telecommunication header**, e.g. = 00, 06, 12 or 18** **for all PILOT type data**) **(see Note 1);**
>
> -- **Minute (when standard time, = 00 for all PILOT type data) (see Note 1).**
>
> **Notes:**
>
> **(1) Inclusion of these entries is required starting with CREX edition 2.**
>
> **(2) If inclusion of international data sub-category is required, Note 2 under B/C20.1.1 applies.**
>
> **(3) If an NMHS performs conversion of PILOT, PILOT SHIP or PILOT MOBIL data produced by another NMHS, Note 3 under B/C20.1.1 applies.**

**B/C20.2 Identification of launch site and instrumentation for wind measurement \<3 01 110\>**

**B/C20.2.1 Identification of launch site**

> WMO block number (0 01 001) and WMO station number (0 01 002) shall be always reported as a non-missing value in reports from a fixed land station. WMO block and station number may be included in reports from a fixed sea station if available.
>
> Ship or mobile land station identifier (0 01 011) shall be always reported not exceeding 9 characters in reports from ships or mobile stations. Ship or mobile station identifier 0 01 011 shall be always set to a missing value in reports from a fixed land station. \[32.2.1\]

**B/C20.2.2 Instrumentation for wind measurement**

> Radiosonde type (Code table 0 02 011), tracking techniques/status of system used (Code table 0 02 014) and type of measuring equipment used (Code table 0 02 003) shall be reported.

**B/C20.3 Date/time of launch \<3 01 113\>**

> Time significance (0 08 021) shall be always set to 18 to indicate that the following entries specify the date and time of launching the radiosonde.
>
> Date of launch \<3 01 011\> and time of launch \<3 01 013\> shall be reported, i.e. year (0 04 001), month (0 04 002), day (0 04 003) and hour (0 04 004), minute (0 04 005) and second (0 04 006) of the actual time of launch shall be reported.
>
> Note: Time of launch \<3 01 013\> shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry 0 04 006 for seconds shall be set to zero.

**B/C20.4 Horizontal and vertical coordinates of launch site \<3 01 114\>**

> **Latitude (0** **05 001) and longitude** (0 06 001) of the launch site shall be reported in degrees with precision in 10^--5^ of a degree.
>
> Height of station ground above mean sea level (0 07 030) and height of barometer above mean sea level (0 07 031) shall be reported in metres with precision in tenths of a metre.
>
> Height of release of sonde above mean sea level (0 07 007) shall be reported in metres.
>
> Station elevation quality mark (Code table 0 33 024) shall be reported to indicate the accuracy of the vertical coordinates of the mobile land station. Fixed land stations and sea stations shall report this datum as a missing value. \[32.2.1\]
>
> Note: The official altitude of the aerodrome (HA in Volume A) shall not be used to report Height of station ground above mean sea level 0 07 030 in BUFR or CREX messages from aerodromes. Those are two different vertical coordinates. "Height of station ground above mean sea level" for each station should be made available to the encoding centre concerned, which may be a centre within the same NMHS or other NMC/RTH.

**B/C20.5 Wind data at pressure levels**

> Wind data at pressure levels shall be always reported using *template TM 309050* and shall be included in descending order with respect to pressure. Data at each pressure level shall be included only once. For example, if a significant level with respect to wind and a standard level coincide, data for that level shall be included only once, the multiple attributes being indicated by Extended vertical sounding significance (Flag table 0 08 042) as specified in Regulation B/C20.5.2.2.
>
> Note: If data are produced and collected in traditional PILOT codes, the order of pressure levels may correspond to the order of levels in Parts A, B, C and D, when converted into BUFR or CREX. In this case, data at a level may be included more than once.

**B/C20.5.1 Number of reported pressure levels**

> The number of reported pressure levels shall be indicated by Extended delayed descriptor replication factor 0 31 002 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.
>
> Notes:
>
> \(1) The number of pressure levels shall never be set to a missing value.
>
> \(2) The number of pressure levels shall be set to a positive value in a NIL report.
>
> \(3) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C20.5.1.1** All required data from the entire ascent shall be reported in a BUFR (or CREX) message that shall be produced when the sounding is completed. In interest of timely data delivery, however, a BUFR (or CREX) message should be sent when level 100 hPa is reached.

**B/C20.5.2 Wind data at a pressure level with radiosonde position \<3 03 050\>**

**B/C20.5.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C20.3, and shall be reported in seconds if available.

**B/C20.5.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> This datum shall be used to specify vertical sounding significance in the following way:
>
> \(a) Bit No. 1 set to 1 indicates surface (see Regulation B/C20.7.1);
>
> \(b) Bit No. 2 set to 1 indicates a standard level (see Regulation B/C20.7.2);
>
> \(c) Bit No. 4 set to 1 indicates a maximum wind level (see Regulation B/C20.7.3);
>
> \(d) Bit No. 7 set to 1 indicates a level significant with respect to wind (see Regulation B/C20.7.4);
>
> \(e) Bit No. 12 set to 1 indicates beginning of missing wind data bit No. 13 set to 1 indicates end of missing wind data (see Regulation B/C20.7.5);
>
> \(f) Bit No. 14 set to 1 indicates the top of wind sounding;
>
> \(g) Bit No. 15 set to 1 indicates a level determined by regional decision;
>
> \(h) Bit No. 17 set to 1 indicates a pressure level originally identified by height as the vertical coordinate;
>
> \(i) All bits set to 0 indicate a level determined by national decision;
>
> \(j) All bits set to 1 indicate a missing value.

**B/C20.5.2.3 Pressure**

> Pressure (0 07 004) shall be reported in pascals (with precision in tens of pascals).
>
> Notes:
>
> \(1) Pressure as the vertical coordinate shall be used when template TM 309050 is applied.
>
> \(2) Pressure as the only vertical coordinate shall be used in a report. \[32.3.1.4\]

**B/C20.5.2.4 Latitude and longitude displacements**

> Latitude displacement (0 05 015) represents the latitude offset from the latitude of the launch site specified in Regulation B/C20.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site specified in Regulation B/C20.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available.

**B/C20.5.2.5 Wind direction** **and speed**

> The wind direction (0 11 001) shall be reported in degrees true and the wind speed (0 11 002) shall be reported in metres per second (with precision in tenths of a metre per second).
>
> Note: Wind direction measured at a station within 1° of the North Pole or within 1° of the South Pole shall be reported in such a way that the azimuth ring shall be aligned with its zero coinciding with the Greenwich 0° meridian.

**B/C20.6 Wind data at height levels**

> Wind data at height levels shall be always reported using *template TM 309051* and shall be included in ascending order with respect to altitude. Data at each height level shall be included only once. For example, if a significant level with respect to wind and a standard level coincide, data for that level shall be included only once, the multiple attributes being indicated by Extended vertical sounding significance (Flag table 0 08 042) as specified in Regulation B/C20.5.2.2.
>
> Note: If data are produced and collected in traditional PILOT codes, the order of height levels may correspond to the order of levels in Parts A, B, C and D, when converted into BUFR or CREX. In this case, data at a level may be included more than once.

**B/C20.6.1 Number of reported height levels**

> The number of reported height levels shall be indicated by Extended delayed descriptor replication factor 0 31 002 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.
>
> Notes:
>
> \(1) The number of height levels shall never be set to a missing value.
>
> \(2) The number of height levels shall be set to a positive value in a NIL report.
>
> \(3) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C20.6.1.1** Regulation B/C20.5.1.1 shall apply.

**B/C20.6.2 Wind data at a height level with radiosonde position \<3 03 052\>**

**B/C20.6.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C20.3, and shall be reported in seconds if available.

**B/C20.6.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> Regulation B/C20.5.2.2 shall apply.

**B/C20.6.2.3 Geopotential height**

> Geopotential height of the level (0 07 009) shall be reported in geopotential metres.
>
> Notes:
>
> \(1) Geopotential height as the vertical coordinate shall be used when template TM 309051 is applied.
>
> \(2) Geopotential height as the only vertical coordinate shall be used in a report. \[32.3.1.4\]

**B/C20.6.2.4 Latitude and longitude displacements**

> Regulation B/C20.5.2.4 shall apply.

**B/C20.6.2.5 Wind direction** **and speed**

> Regulation B/C20.5.2.5 shall apply.

**B/C20.7 Criteria for reporting standard and significant levels**

**B/C20.7.1 Surface**

> The surface level shall be always reported.
>
> Note: The value of Extended vertical sounding significance 0 08 042 at the surface level shall indicate that this level is also a level significant with respect to wind, i.e. bit No. 1 and also bit No. 7 shall be set to 1.

**B/C20.7.2 Standard levels**

**B/C20.7.2.1** The standard levels of 850, 700, 500, 400, 300, 250, 200, 150, 100, 70, 50, 30, 20 and 10 hPa shall be reported in descending order with respect to pressure (in ascending order with respect to altitude). \[32.2.2.1\]

**B/C20.7.2.2** When pressure measurements are not available, wind data shall be reported using geopotential approximations to the standard isobaric surfaces. \[32.2.2.2\]

**B/C20.7.2.3** When wind data at a standard level are not available, the corresponding entries for that level shall be reported as missing values. \[32.2.2.3\]

**B/C20.7.2.4** When the standard levels are located by means of pressure equipment and if the pressure element failed during the ascent, the remaining standard levels to be reported shall be indicated by 0 08 042 -- bit No. 2 set to 1 (standard level) and by bit No. 17 set to 1 (a pressure level originally identified by height as the vertical coordinate). \[32.2.2.4\]

**B/C20.7.3 Maximum wind level(s)**

**B/C20.7.3.1** When a maximum wind level (one or more) is reported, the corresponding number of levels shall be included in the report indicated by 0 08 042 -- bit No. 4 set to 1*.* \[32.2.3.3\]

> Notes:
>
> \(1) Criteria for determining maximum wind levels are given in Regulations B/C20.7.3.3 and B/C20.7.3.4 below.
>
> \(2) As a maximum wind level is also a level significant with respect to wind, bit No. 7 as well as bit No. 4 shall be set to 1 in the Extended vertical sounding significance 0 08 042.

**B/C20.7.3.2** When no maximum wind level is observed, no level shall be indicated by bit No. 4 of 0 08 042 set to 1. \[32.2.3.4.5\]

**B/C20.7.3.3** A maximum wind level:

> \(a) Shall be determined by consideration of the list of significant levels for wind speed, as obtained by means of the relevant recommended or equivalent national method (see Note under Regulation B/C20.7.4.2) and *not* by consideration of the original wind-speed curve;
>
> \(b) Shall be located above the 500-hPa isobaric surface and shall correspond to a speed of more than 30 metres per second.
>
> Note: A maximum wind level is defined as a level at which the wind speed is greater than that observed immediately above and below that level.
>
> \[32.2.3.1\]

**B/C20.7.3.4** Whenever more than one maximum wind level exists, these levels shall be reported as follows:

> \(a) The level of greatest maximum wind speed shall be always included;
>
> \(b) The other levels shall be included in the report only if their speed exceeds those of the two adjacent minima by at least 10 metres per second;
>
> \(c) Furthermore, the highest level attained by the sounding shall be indicated as a maximum wind level, provided:
>
> \(i) It satisfies the criteria set forth in Regulation B/C20.7.3.3 above;
>
> \(ii) It constitutes the level of the greatest speed of the whole sounding.
>
> \[32.2.3.2\]

**B/C20.7.3.5** When the greatest wind speed observed throughout the sounding occurred at the top of the sounding, this level shall be indicated by 0 08 042 -- bit No. 4 set to 1 (maximum wind level), bit No. 7 set to 1 (level significant with respect to wind) and bit No. 14 set to 1 (top of wind sounding). \[32.2.3.4.3\], \[32.2.3.4.4\]

**B/C20.7.3.6** In compliance with Regulation B/C20.5.2.3 or B/C20.6.2.3, maximum wind level data shall be reported with the same vertical coordinate as the other data in the profile, using template TM 309050 or template TM 309051 for the entire sounding.

> Note: If data are produced and collected in traditional PILOT codes, maximum wind data may be reported with height as the vertical coordinate in Parts A or C of Pilot report, while the whole vertical wind profile is reported with pressure as the vertical coordinate. Even in this case, the maximum wind data may be converted into BUFR using sequence 3 09 050 because the maximum wind data were selected from the list of significant levels with respect to wind. And these significant levels are included in Parts B or D of Pilot report, identified by pressure as the vertical coordinate. \[32.3.1.4\]

**B/C20.7.4 Levels significant with respect to wind**

**B/C20.7.4.1** Significant wind levels shall be chosen so that the data from them *alone* shall make it possible to reconstruct the wind profile with sufficient accuracy for practical use. \[32.3.1.1\]

**B/C20.7.4.2** Criteria for determining significant levels with respect to changes in wind speed and direction:

> \(a) The direction and speed curves (in function of the log of pressure or altitude) can be reproduced with their prominent characteristics;
>
> \(b) These curves can be reproduced with the accuracy of at least 10 degrees true for direction and five metres per second for speed.
>
> Note: To satisfy these criteria, the following method of successive approximations is recommended, but other methods of attaining equivalent results may suit some national practices better and may be used:
>
> \(i) The surface level and highest level for which wind data are available constitute the first and the last significant levels. The deviation from the linearly interpolated values between these two levels is then considered. If no direction deviates by more than 10 degrees true and no speed by more than five metres per second, no other significant level need be reported. Whenever one parameter deviates by more than the limit specified in paragraph (b) above the level of greatest deviation becomes a supplementary significant level for both parameters.
>
> \(ii) The additional significant levels so introduced divide the sounding into two layers. In each separate layer, the deviation from the linearly interpolated values between the base and the top are then considered. The process used in paragraph (i) above is repeated and yields other significant levels. These additional levels in turn modify the layer distribution, and the method is applied again until any level is approximated to the above-mentioned specified values.
>
> \[32.3.1.1\]

**B/C20.7.5 Beginning and end of missing wind data**

**B/C20.7.5.1** If wind profile data are reported with pressure as the vertical coordinate, a layer for which wind data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 50 hPa thick. The boundary levels are the levels closest to the bottom and the top of the layer for which the observed data are available. The boundary levels are not required to meet "significant wind level" criteria. \[32.3.1.5.2\]

**B/C20.7.5.2** If wind profile data are reported with height as the vertical coordinate, a layer for which wind data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 1 500 geopotential metres thick. The boundary levels are the levels closest to the bottom and the top of the layer for which the observed data are available. The boundary levels are not required to meet "significant wind level" criteria. \[32.3.1.5.1\]

**B/C20.8 Wind shear data at pressure levels**

**B/C20.8.1 Number and order of levels for which wind shear is reported**

**B/C20.8.1.1** The number of levels with wind shear **data** shall be indicated by Delayed descriptor replication factor 0 31 001 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.

> Notes:
>
> \(1) The number of **levels** with wind shear **data** shall never be set to a missing value.
>
> \(2) The number of **levels** with wind shear **data** shall be set to a positive value in a NIL report.
>
> \(3) The number of **levels** with wind shear **data** shall be set to zero if data for vertical wind shear are not computed and required. \[32.2.3.5\]
>
> \(4) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C20.8.1.2** Whenever wind shear data are reported for more than one level, these maximum wind levels shall be included in the same order as in the sequence \<3 03 050\>, i.e. in descending order with respect to pressure.

**B/C20.8.2 Wind shear data at a pressure level with radiosonde position \<3 03 051\>**

**B/C20.8.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C20.3, and shall be reported in seconds if available.

**B/C20.8.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> A level, for which wind shear data are reported, shall be indicated by vertical sounding significance 0 08 042 -- bit No. 4 set to 1 (maximum wind level) and by bit No. 7 set to 1 (level significant with respect to wind). Moreover, if the top of the wind sounding corresponds to the highest wind speed observed throughout the ascent, this level shall be indicated also by bit No. 14 set to 1 (top of wind sounding).

**B/C20.8.2.3 Pressure**

> Pressure (0 07 004) shall be reported in pascals with precision in tens of pascals.

**B/C20.8.2.4 Latitude and longitude displacements**

> Latitude displacement (0 05 015) represents the latitude offset from the latitude of the launch site specified in Regulation B/C20.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site specified in Regulation B/C20.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available.

**B/C20.8.2.5 Wind shear data**

> Absolute wind shear **in 1 km layer below (0 11 061) and a**bsolute wind shear **in 1‑km layer above (0 11 062)** shall be reported in metres per second (with precision in tenths of a metre per second)**, if** data for vertical wind shear are computed and required. \[32.2.3.5\]

**B/C20.9 Wind shear data at heights**

**B/C20.9.1 Number and order of levels for which wind shear is reported**

**B/C20.9.1.1** Regulation B/C20.8.1.1 shall apply.

**B/C20.9.1.2** Whenever wind shear data are reported for more than one level, these maximum wind levels shall be included in the same order as in the sequence \<3 03 052\>, i.e. in ascending order with respect to altitude.

**B/C20.9.2 Wind shear data at a height level with radiosonde position \<3 03 053\>**

**B/C20.9.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C20.3, and shall be reported in seconds if available.

**B/C20.9.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> Regulation B/C20.8.2.2 shall apply.

**B/C20.9.2.3 Geopotential height**

> Geopotential height of the level (0 07 009) shall be reported in geopotential metres.

**B/C20.9.2.4 Latitude and longitude displacements**

> Regulation B/C20.8.2.4 shall apply.

**B/C20.9.2.5 Wind shear data**

> Regulation B/C20.8.2.5 shall apply.

**B/C20.10 Data required by regional or national reporting practices**

> If regional or national reporting practices require inclusion of wind data at additional levels, these data shall be reported using sequence \<3 03 050\> for wind data at a pressure level or sequence \<3 03 052\> for wind data at a height level. Regulation B/C20.5 or Regulation B/C20.6 shall apply.
>
> Notes:
>
> \(1) A level determined by regional decision shall be indicated by Extended vertical sounding significance 0 08 042 -- bit No. 15 set to 1.
>
> \(2) A level determined by national decision shall be indicated by Extended vertical sounding significance 0 08 042 -- all bits set to 0.

**B/C20.10.1 Additional data required by reporting practices in RA I**

> Wind data at additional levels 600, 900, 2 100, 3 900, 4 500, 5 100, 21 000 m, and all successive levels at 3 000 m intervals, shall be reported in compliance with Regulation B/C20.10 and Note 1 under this regulation. \[1/32.2\], \[1/32.4.1\]

**B/C20.10.2 Additional data required by reporting practices in RA II**

**B/C20.10.2.1** Wind data at additional levels 300, 600, 900, 2 100, 3 600, 4 500, 6 000 m shall be reported in compliance with Regulation B/C20.10 and Note 1 under this regulation. \[2/32.3\]

**B/C20.10.2.2** The inclusion of wind shear data shall be left to national decision. Members are recommended to include these data as often as possible. \[2/32.2\]

**B/C20.10.3 Additional data required by reporting practices in RA III**

> Wind data at additional levels 300, 600, 900, 2 100, 2 400, 4 200, 6 000, 8 100, 33 000 m, and all successive levels at 3 000 m intervals, shall be reported in compliance with Regulation B/C20.10 and Note 1 under this regulation. \[3/32.2\], \[3/32.4.1\]

**B/C20.10.4 Additional data required by reporting practices in RA IV**

> Wind data at additional levels 300, 600, 900, 1 200, 1 800, 2 100, 2 400, 2 700, 3 600, 4 200, 4 800, 6 000, 7 500, 9 000, 15 000 m, and all successive levels at 3 000 m intervals, shall be reported in compliance with Regulation B/C20.10 and Note 1 under this regulation. \[4/32.2\], \[4/32.4.1\]

**B/C20.10.5 Additional data required by reporting practices in RA V**

> Wind data at additional levels 900, 2 100, 4 200 m shall be reported in compliance with Regulation B/C20.10 and Note 1 under this regulation. \[5/32.3\]

**B/C20.10.6 Additional data required by reporting practices in RA VI**

**B/C20.10.6.1** Wind data at additional levels 900, 800, 600 hPa (with pressure as the vertical coordinate) and at levels 1 000, 2 000, 4 000 m or 900, 2 100, 4 200 m (with height as the vertical coordinate), shall be reported in compliance with Regulation B/C20.10 and Note 1 under this regulation. \[6/32.3.1\]

**B/C20.10.6.2** The inclusion of wind shear data shall be left to national decision. Members are recommended to include these data as often as possible. \[6/32.2\], \[6/32.5\]

\_\_\_\_\_\_\_\_\_\_\_\_\_