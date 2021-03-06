**B/C26** -- **Regulations for reporting TEMP DROP data in TDCF**

**TM 309053 -- BUFR template for P, T, U and wind vertical profiles suitable for TEMP DROP observation data**

  -------------- -------------- --------------------------------------------------------------------------------------
                                **Sequence for representation TEMP DROP observation type data**
  **3 09 053**   **3 01 112**   **Identification of launch point and instrumentation of dropsonde**
                 **3 01 113**   **Date/time of launch**
                 **3 01 114**   **Horizontal and vertical coordinates of launch site**
                 **1 01 000**   **Delayed replication of 1 descriptor**
                 **0 31 002**   **Extended delayed descriptor replication factor**
                 **3 03 054**   **Temperature, dewpoint and wind data at a pressure level with radiosonde position**
                 1 01 000       **Delayed replication of 1 descriptor**
                 0 31 001       **Delayed descriptor replication factor**
                 **3 03 051**   **Wind shear data at a pressure level with radiosonde position**
  -------------- -------------- --------------------------------------------------------------------------------------

This BUFR template for P, T, U and wind profiles further expands as follows:

  -------------------------------------------------------------------------------------------------------------
                                                                                                  Unit, scale
  -------------- ---------- --------------------------------------------------------------------- -------------
                            **Identification of launch point and instrumentation of dropsonde**   

  **3 01 112**   0 01 006   Aircraft flight number                                                CCITT IA5

                 0 02 011   Radiosonde type                                                       Code table

                 0 02 013   Solar and infrared radiation correction                               Code table

                 0 02 014   Tracking technique/status of system used                              Code table

                 0 02 003   Type of measuring equipment used                                      Code table

                            **Date/time of launch**                                               

  **3 01 113**   0 08 021   Time significance (= 18 Launch time)                                  Code table

                 3 01 011   Year                                                                  Year

                            Month                                                                 Month

                            Day                                                                   Day

                 3 01 013   Hour                                                                  Hour

                            Minute                                                                Minute

                            Second                                                                Second

                            **Horizontal and vertical coordinates of launch site**                

  **3 01 114**   3 01 021   Latitude/longitude (high accuracy)                                    Degree, 5

                 0 07 030   Height of station ground above mean sea level                         m, 1

                 0 07 031   Height of barometer above mean sea level                              m, 1

                 0 07 007   Height (of release of sonde above mean sea level)                     m

                 0 33 024   Station elevation quality mark (for mobile stations)                  Code table

                            **Temperature, dewpoint and wind data at pressure levels**            

  **1 01 000**              Delayed replication of 1 descriptor                                   

  **0 31 002**              Extended delayed descriptor replication factor                        Numeric

                            *Temperature, dewpoint and wind data at a pressure\                   
                            level with radiosonde position*                                       

  **3 03 054**   0 04 086   Long time period or displacement (since launch time)                  Second

                 0 08 042   Extended vertical sounding significance                               Flag table

                 0 07 004   Pressure                                                              Pa, --1

                 0 10 009   Geopotential height                                                   gpm

                 0 05 015   Latitude displacement (high accuracy) -- since launch site            Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site           Degree, 5

                 0 12 101   Temperature/air temperature                                           K, 2

                 0 12 103   Dewpoint temperature                                                  K, 2

                 0 11 001   Wind direction                                                        Degree true

                 0 11 002   Wind speed                                                            m s^--1^, 1

                            **Wind shear data**                                                   

  **1 01 000**              Delayed replication of 1 descriptor                                   

  **0 31 001**              Delayed descriptor replication factor                                 Numeric

                            *Wind shear data at a pressure level* ***with radiosonde\             
                            position***                                                           

  **3 03 051**   0 04 086   Long time period or displacement (since launch time)                  Second

                 0 08 042   Extended vertical sounding significance                               Flag table

                 0 07 004   Pressure                                                              Pa, --1

                 0 05 015   Latitude displacement (high accuracy) -- since launch site            Degree, 5

                 0 06 015   Longitude displacement (high accuracy) -- since launch site           Degree, 5

                 0 11 061   Absolute wind shear in 1 km layer below                               m s^--1^, 1

                 0 11 062   Absolute wind shear in 1 km layer above                               m s^--1^, 1
  -------------------------------------------------------------------------------------------------------------

Notes:

\(1) Time of launch 3 01 013 shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry for seconds shall be put to zero.

\(2) Long time displacement 0 04 086 represents the time offset from the launch time 3 01 013 (in seconds).

\(3) Latitude displacement 0 05 015 represents the latitude offset from the latitude of the launch site. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site.

**\
Regulations:**

**B/C26.1** **Section 1 of BUFR or CREX**

**B/C26.2 Identification of launch point and instrumentation of dropsonde**

**B/C26.3 Date/time of launch**

B/C26.4 Horizontal and vertical coordinates **of launch site**

**B/C26.5** Temperature, dewpoint and wind data at pressure levels

**B/C26.6** Criteria for reporting standard and significant levels

**B/C26.7** Wind shear data

**B/C26.8 Data required by regional or national reporting practices**

**B/C26.1 Section 1 of BUFR or CREX**

**B/C26.1.1 Entries required in Section 1 of BUFR**

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
> -- **Year (year of the century up to BUFR edition 3);**
>
> -- **Month (standard time);**
>
> -- **Day (standard time = YY in the** abbreviated telecommunication header **for TEMP DROP type data**);
>
> -- **Hour (standard time = GG in the** abbreviated telecommunication header **for TEMP DROP type data**);
>
> -- **Minute (standard time = 00 for TEMP DROP type data);**
>
> -- **Second (= 0) (see Note 1).**
>
> **Notes:**
>
> **(1) Inclusion of this entry is required starting with BUFR edition 4.**
>
> **(2) If required, the *international* data sub-category shall be included at all observation times as follows:**
>
> **= 007 for TEMP DROP data.**
>
> **(3) If an NMHS performs conversion of TEMP DROP data produced by another NMHS, o**riginating centre in Section 1 shall indicate **the converting centre and o**riginating sub-centre shall indicate the **producer of TEMP DROP bulletins. Producer of TEMP DROP bulletins shall be specified in Common Code table C-12 as a sub-centre of the originating centre, i.e. of the NMHS executing the conversion.**

**B/C26.1.2 Entries required in Section 1 of CREX**

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
> -- **Year (standard time) (see Note 1);**
>
> -- **Month (standard time) (see Note 1);**
>
> -- **Day (standard time = YY in the** abbreviated telecommunication header **for TEMP DROP type data**) **(see Note 1);**
>
> -- **Hour (standard time = GG in the** abbreviated telecommunication header **for TEMP DROP type data**) **(see Note 1);**
>
> -- **Minute (standard time = 00 for TEMP DROP type data) (see Note 1).**
>
> **Notes:**
>
> **(1) Inclusion of these entries is required starting with CREX edition 2.**
>
> **(2) If inclusion of international data sub-category is required, Note 2 under Regulation B/C26.1.1 applies.**
>
> **(3) If an NMHS performs conversion of TEMP DROP data produced by another NMHS, Note 3 under Regulation B/C26.1.1 applies.**

**B/C26.2 Identification of launch point and instrumentation of dropsonde \<3 01 112\>**

**B/C26.2.1 Identification of launch point of dropsonde**

> Aircraft identifier (0 01 006) shall be always reported.

**B/C26.2.2 Instrumentation for P, T, U and wind measurement**

> Radiosonde type (Code table 0 02 011), solar and infrared radiation correction (Code table 0 02 013), tracking techniques/status of system used (Code table 0 02 014) and type of measuring equipment used (Code table 0 02 003) shall be reported. \[35.2.5\]

**B/C26.3 Date/time of launch \<3 01 113\>**

> Time significance (0 08 021) shall be always set to 18 to indicate that the following entries specify the date and time of launching the dropsonde.
>
> Date of launch \<3 01 011\> and time of launch \<3 01 013\> shall be reported, i.e. year (0 04 001), month (0 04 002), day (0 04 003) and hour (0 04 004), minute (0 04 005) and second (0 04 006) of the actual time of launch shall be reported. \[35.2.5\]
>
> **Note:** Time of launch \<3 01 013\> shall be reported with the highest possible accuracy available. If the launch time is not available with second accuracy, the entry 0 04 006 for seconds shall be set to zero.

**B/C26.4 Horizontal and vertical coordinates of launch site \<3 01 114\>**

> **Latitude (0 05 001) and longitude** (0** **06 001) of the launch site shall be reported in degrees with precision in 10^--5^ of a degree.
>
> Height of station ground above mean sea level (0** **07 030) shall be reported as a missing value.
>
> Height of barometer above mean sea level (0** **07 031) shall be reported in metres with precision in tenths of a metre.
>
> Height of release of dropsonde above mean sea level (0** **07 007) shall be reported in metres.
>
> Station elevation quality mark (Code table 0** **33 024) shall be reported as a missing value. \[35.2.1\]

**B/C26.5 Temperature, dewpoint and wind data at pressure levels**

> Temperature, dewpoint and wind data at pressure levels obtained during the dropsonde descent shall be included in descending order with respect to pressure. Data at each pressure level shall be included only once. For example, if a significant level with respect to air temperature and relative humidity and a standard isobaric surface coincide, data for that level shall be included only once, the multiple attributes being indicated by Extended vertical sounding significance (Flag table 0 08 042) as specified in Regulation B/C26.5.2.2.
>
> **Note:** If data are produced and collected in traditional TEMP DROP code, the order of pressure levels may correspond to the order of levels in Parts A, B, C and D, when converted into BUFR or CREX. In this case, data at a level may be included more than once.

**B/C26.5.1 Number of reported pressure levels**

> The number of reported pressure levels shall be indicated by Extended delayed descriptor replication factor 0 31 002 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.
>
> Notes:
>
> \(1) The number of pressure levels shall never be set to a missing value.
>
> \(2) The number of pressure levels shall be set to a positive value in a NIL report.
>
> \(3) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C26.5.2 Temperature, dewpoint and wind data at a pressure level** **with radiosonde position \<3 03 054\>**

**B/C26.5.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C26.3, and shall be reported in seconds if available.

**B/C26.5.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> This datum shall be used to specify vertical sounding significance in the following way:
>
> \(a) Bit No. 1 set to 1 indicates a surface (see Regulation B/C26.6.1);
>
> \(b) Bit No. 2 set to 1 indicates a standard level (see Regulation B/C26.6.2);
>
> \(c) Bit No. 3 set to 1 indicates a tropopause level (see Regulation B/C26.6.3);
>
> \(d) Bit No. 4 set to 1 indicates a maximum wind level (see Regulation B/C26.6.4);
>
> \(e) Bit No. 5 set to 1 indicates a level significant with respect to temperature (see Regulation B/C26.6.5);
>
> \(f) Bit No. 6 set to 1 indicates a level significant with respect to relative humidity (see Regulation B/C26.6.6);
>
> \(g) Bit No. 7 set to 1 indicates a level significant with respect to wind (see Regulation B/C26.6.7);
>
> \(h) Bit No. 8 set to 1 indicates beginning of missing temperature data and bit No. 9 set to 1 indicates end of missing temperature data (see Regulation B/C26.6.8);
>
> \(i) Bit No. 10 set to 1 indicates beginning of missing humidity data and bit No. 11 set to 1 indicates end of missing humidity data (see Regulation B/C26.6.9);
>
> \(j) Bit No. 12 set to 1 indicates beginning of missing wind data bit No. 13 set to 1 indicates end of missing wind data (see Regulation B/C26.6.10);
>
> \(k) Bit No. 14 set to 1 indicates the top of wind sounding (the lowest level for which wind data are available);
>
> \(l) Bit No. 15 set to 1 indicates a level determined by regional decision;
>
> \(m) All bits set to 0 indicate a level determined by national decision;
>
> \(n) All bits set to 1 indicate a missing value.

**B/C26.5.2.3 Pressure**

> Pressure (0 07 004) shall be reported in pascals (with precision in tens of pascals).

**B/C26.5.2.4 Geopotential height**

> Geopotential height of the level (0 10 009) shall be reported in geopotential metres.

**B/C26.5.2.5 Radiosonde drift - latitude and longitude displacements**

> Latitude displacement (0 05 015) represents the latitude offset from the latitude of the launch site specified in Regulation B/C26.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site specified in Regulation B/C26.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available.

**B/C26.5.2.6 Temperature**

> Temperature (0 12 101) shall be reported in kelvin (with precision in hundredths of a kelvin); if produced in CREX, in degrees Celsius (with precision in hundredths of a degree Celsius). Temperature data shall be reported with precision in hundredths of a degree even if they are measured with the accuracy in tenths of a degree.
>
> Notes:
>
> \(1) This requirement is based on the fact that conversion from the Kelvin to the Celsius scale has often resulted into distortion of the data values.
>
> \(2) Temperature t (in degrees Celsius) shall be converted into temperature T (in kelvin) using equation: T = t + 273.15.

**B/C26.5.2.7 Dewpoint temperature**

> Dewpoint temperature (0 12 103) shall be reported in kelvin (with precision in hundredths of a kelvin); if produced in CREX, in degrees Celsius (with precision in hundredths of a degree Celsius).
>
> Note: Notes 1 and 2 under Regulation B/C26.5.2.6 shall apply.

**B/C26.5.2.7.1** Dewpoint temperature data shall be derived using the function (or a near equivalent) for a relationship between saturation vapour pressure over water and air temperature (specified in the *Technical Regulations (WMO-No. 49)*). Dewpoint temperature data shall not be reported when the air temperature is outside the range stated by WMO for the application of the function; a lesser range may be used as a national practice. \[35.3.1.1\]

**B/C26.5.2.8 Wind direction** **and speed**

> The wind direction (0 11 001) shall be reported in degrees true and the wind speed (0 11 002) shall be reported in metres per second (with precision in tenths of a metre per second).
>
> Note: Wind direction measured in sounding originated from a launch site within 1° of the North Pole or within 1° of the South Pole shall be reported in such a way that the azimuth ring shall be aligned with its zero coinciding with the Greenwich 0° meridian.

**B/C26.5.2.8.1** Only wind data obtained from the radiosonde descent by electronic means shall be included in the BUFR (or CREX) message in which data are described by the common sequence 3 09 053. Wind data obtained by means other than a radiosonde-type descent shall not be included in a message under common sequence 3 09 053. \[35.1.7\]

**B/C26.6 Criteria for reporting standard and significant levels**

**B/C26.6.1 Surface level**

> If extrapolated surface data are included in the report, the level shall be indicated by bit No. 1 of 0 08 042 set to 1.

**B/C26.6.2 Standard levels**

**B/C26.6.2.1** The standard levels of 1 000, 925, 850, 700, 500, 400, 300, 250, 200, 150, 100, 70, 50, 30, 20 and 10 hPa shall be reported in descending order with respect to pressure. \[35.2.2.1\]

**B/C26.6.2.2** When air temperature, dewpoint temperature or wind data at a standard level are not available, the corresponding entries for that level shall be reported as missing values.

**B/C26.6.2.3** Whenever it is desired to extrapolate a sounding for the computation of the geopotential at a standard level, the following rules shall apply:

> \(a) Extrapolation is permissible if, and only if, the pressure difference between the minimum pressure of the sounding and the isobaric surface for which the extrapolated value is being computed does not exceed one quarter of the pressure at which the extrapolated value is desired, provided the extrapolation does not extend through a pressure interval exceeding 25 hPa;
>
> \(b) For the purpose of geopotential calculation, and for this purpose only, the sounding will be extrapolated, using two points only of the sounding curve on a T-log p diagram, namely that at the minimum pressure reached by the sounding and that at the pressure given by the sum of this minimum pressure and the pressure difference, mentioned in (a) above.
>
> \[35.2.2.4\]

**B/C26.6.3 Tropopause level(s)**

**B/C26.6.3.1** When a tropopause (one or more) is observed, the corresponding number of levels shall be included (indicated by 0 08 042 -- bit No. 3 set to 1).

> Note: For a definition of tropopause, see the *International Meteorological Vocabulary (WMO-No. 182).*
>
> \[35.2.3.1\]

**B/C26.6.3.2** When no tropopause data are observed, no level shall be indicated by bit No. 3 of 0 08 042 set to 1. \[35.2.3.2\]

**B/C26.6.4 Maximum wind level(s)**

**B/C26.6.4.1** When a maximum wind level (one or more) is reported, the corresponding number of levels shall be included in the report indicated by 0 08 042 -- bit No. 4 set to 1*.*

> Notes:
>
> \(1) Criteria for determining maximum wind levels are given in Regulations B/C26.6.4.3 and B/C26.6.4.4 below. \[35.2.4.1\]
>
> \(2) As a maximum wind level is also a level significant with respect to wind, bit No. 7 as well as bit No. 4 shall be set to 1 in the Extended vertical sounding significance 0 08 042.

**B/C26.6.4.2** When no maximum wind level is observed, no level shall be indicated by bit No. 4 of 0 08 042 set to 1. \[35.2.4.2\]

**B/C26.6.4.3** A maximum wind level:

> \(a) Shall be determined by consideration of the list of significant levels for wind speed, as obtained by means of the relevant recommended or equivalent national method (see the Note under Regulation B/C26.6.7.2) and *not* by consideration of the original wind-speed curve;
>
> \(b) Shall be located above the 500-hPa isobaric surface and shall correspond to a speed of more than 30 metres per second.
>
> Note: A maximum wind level is defined as a level at which the wind speed is greater than that observed immediately above and below that level.
>
> \[35.2.4.1\], \[32.2.3.1\]

**B/C26.6.4.4** Whenever more than one maximum wind level exists, these levels shall be reported as follows:

> \(a) The level of greatest maximum wind speed shall be always included;
>
> \(b) The other levels shall be included in the report only if their speed exceeds those of the two adjacent minima by at least 10 metres per second.
>
> \[35.2.4.1\], \[32.2.3.2\]

**B/C26.6.4.5** If the top of the wind sounding corresponds to the highest wind speed observed throughout the descent, this level shall be indicated by 0 08 042 -- bit No. 4 set to 1 (maximum wind level), bit No. 7 set to 1 (level significant with respect to wind) and bit No. 14 set to 1 (top of wind sounding).

> Notes:
>
> \(1) For the purpose of the above regulation, the "top of the wind sounding" is to be understood as the lowest level (termination level of the sounding) for which wind data are available. \[35.2.4.3\]
>
> \(2) Although not very probable, the situation described in the above regulation cannot be excluded.

**B/C26.6.5 Levels significant with respect to temperature**

**B/C26.6.5.1** The reported significant levels *alone* shall make it possible to reconstruct the air temperature profile within the limits of the criteria specified.

> If the criteria for determination of significant levels with respect to air temperature are satisfied at a particular point of altitude, data for all variables (if available) shall be reported for that level.
>
> \[35.3.1.1\]

**B/C26.6.5.2** The following shall be included as "mandatory" significant temperature levels:

> \(a) Aircraft reference level and termination level of the sounding (the lowest level of the sounding);
>
> \(b) A level between 110 and 100 hPa;
>
> \(c) Bases and tops of inversions and isothermal layers which are at least 20 hPa thick, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher;
>
> \(d) Bases and tops of inversion layers which are characterized by a change in temperature of at least 2.5 ºC, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher.
>
> Note: The inversion layers of (c) and (d) may be comprised of several thinner inversion layers separated by thin layers of temperature lapse. To allow for this situation, the tops of the inversion layers of (c) and (d) shall each be at a level such that no further inversion layers, whether thick or thin, shall occur for at least 20 hPa above the level.
>
> \[35.3.1.2\]

**B/C26.6.5.3** The following shall be included as "additional" significant levels. They shall be selected in the order given, thereby giving priority to representing the temperature profile. As far as possible, these additional levels shall be the actual levels at which prominent changes in the lapse rate of air temperature occur:

> \(a) Levels which are necessary to ensure that the temperature obtained by linear interpolation (on a T-log P or essentially similar diagram) between adjacent significant levels shall not depart from the observed temperature by more than 1 ºC below the first significant level reported above the 300-hPa level or the first tropopause, whichever level is the lower, or by more than 2 ºC thereafter;
>
> \(b) Levels which are necessary to limit the interpolation error on diagrams other than T-log P. These levels shall be such that the pressure at one significant level divided by the pressure of the preceding significant layer shall exceed 0.6 for levels up to the first tropopause and shall be determined by use of the method for selecting additional levels but with application of tighter criteria.
>
> \[35.3.1.3\]

**B/C26.6.5.4** When a significant level with respect to air temperature and a standard level coincide, data for that level shall be reported only once.

**B/C26.6.6 Levels significant with respect to relative humidity**

**B/C26.6.6.1** The reported significant levels *alone* shall make it possible to reconstruct the relative humidity profiles within the limits of the criteria specified.

> If the criteria for determination of significant levels with respect to relative humidity are satisfied at a particular point of altitude, data for all variables (if available) shall be reported for that level.
>
> \[35.3.1.1\]

**B/C26.6.6.2** The following shall be included as "mandatory" significant humidity levels:

> \(a) Aircraft reference level and termination level of the sounding (the lowest level of the sounding);
>
> \(b) A level between 110 and 100 hPa;
>
> \(c) Bases and tops of inversions and isothermal layers which are at least 20 hPa thick, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher;
>
> \(d) Bases and tops of inversion layers which are characterized by a change in relative humidity of at least 20 per cent, provided that the base of the layer occurs below the 300-hPa level or the first tropopause, whichever is the higher.
>
> Note: The Note under Regulation B/C26.6.5.2 shall apply.
>
> \[35.3.1.2\]

**B/C26.6.6.3** The following shall be included as "additional" significant levels. They shall be selected in the order given, thereby giving priority to representing the temperature profile. As far as possible, these additional levels shall be the actual levels at which prominent changes in the lapse rate of air temperature occur:

> \(a) Levels which are necessary to ensure that the relative humidity obtained by linear interpolation between adjacent significant levels shall not depart by more than 15 per cent from the observed values (The criterion of 15 per cent refers to an amount of relative humidity and NOT to the percentage of the observed value, e.g. if an observed value is 50 per cent, the interpolated value shall lie between 35 per cent and 65 per cent.);
>
> \(b) Levels which are necessary to limit the interpolation error on diagrams other than T-log P. These levels shall be such that the pressure at one significant level divided by the pressure of the preceding significant layer shall exceed 0.6 for levels up to the first tropopause and shall be determined by use of the method for selecting additional levels but with application of tighter criteria.
>
> \[35.3.1.3\]

**B/C26.6.6.4** When a significant layer with respect to relative humidity and a standard level coincide, data for that level shall be reported only once.

**B/C26.6.7 Levels significant with respect to wind**

**B/C26.6.7.1** Significant wind levels shall be chosen so that the data from them *alone* shall make it possible to reconstruct the wind profile with sufficient accuracy for practical use. \[35.3.2.1\]

> If the criteria for determination of significant levels with respect to wind speed and direction are satisfied at a particular point of altitude, data for all variables (if available) shall be reported for that level.

**B/C26.6.7.2** Criteria for determining significant levels with respect to changes in wind speed and direction:

> \(a) The direction and speed curves (in function of the log of pressure or altitude) can be reproduced with their prominent characteristics;
>
> \(b) These curves can be reproduced with the accuracy of at least 10 degrees true for direction and five metres per second for speed.
>
> Note: To satisfy these criteria, the following method of successive approximations is recommended, but other methods of attaining equivalent results may suit some national practices better and may be used:
>
> \(i) The lowest level for which wind data are available and the aircraft reference level constitute the first and the last significant levels. The deviation from the linearly interpolated values between these two levels is then considered. If no direction deviates by more than 10 degrees true and no speed by more than five metres per second, no other significant level need be reported. Whenever one parameter deviates by more than the limit specified in paragraph (b) above the level of greatest deviation becomes a supplementary significant level for both parameters;
>
> \(ii) The additional significant levels so introduced divide the sounding into two layers. In each separate layer, the deviation from the linearly interpolated values between the base and the top are then considered. The process used in paragraph (i) above is repeated and yields other significant levels. These additional levels in turn modify the layer distribution, and the method is applied again until any level is approximated to the above-mentioned specified values.
>
> \[35.3.2.1\], \[32.3.1.1\]

**B/C26.6.8 Beginning and end of missing temperature data**

**B/C26.6.8.1** A layer for which temperature data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 20 hPa thick. The boundary levels are the levels closest to the bottom (beginning of the missing data) and the top (end of the missing data) of the layer for which temperature data are available. The boundary levels are not required to meet "significant temperature level" criteria. \[35.3.1.6\]

**B/C26.6.9 Beginning and end of missing humidity data**

**B/C26.6.9.1** A layer for which dewpoint temperature data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 20 hPa thick. The boundary levels are the levels closest to the bottom (beginning of the missing data) and the top (end of the missing data) of the layer for which dewpoint temperature data are available. The boundary levels are not required to meet "significant humidity level" criteria. \[35.3.1.6\]

**B/C26.6.10 Beginning and end of missing wind data**

**B/C26.6.10.1** A layer for which wind data are missing shall be indicated by reporting the boundary levels of the layer, provided that the layer is at least 50 hPa thick. The boundary levels are the levels closest to the bottom (beginning of the missing data) and the top (end of the missing data) of the layer for which the observed data are available. The boundary levels are not required to meet "significant wind level" criteria. \[35.3.2.2\]

**B/C26.7 Wind shear data**

**B/C26.7.1 Number and order of levels for which wind shear is reported**

**B/C26.7.1.1** The number of levels with wind shear **data** shall be indicated by Delayed descriptor replication factor 0 31 001 in BUFR and by a four-digit number in the Data Section corresponding to the position of the replication descriptor in the Data Description Section of CREX.

> Notes:
>
> \(1) The number of **levels** with wind shear **data** shall never be set to a missing value.
>
> \(2) The number of **levels** with wind shear **data** shall be set to a positive value in a NIL report.
>
> \(3) The number of **levels** with wind shear **data** shall be set to zero if data for vertical wind shear are not computed and required. \[35.2.4.4\]
>
> \(4) If data compression is to be used, BUFR Regulation 94.6.3, Note 2, sub-note ix shall apply.

**B/C26.7.1.2** Whenever wind shear data are reported for more than one level, these maximum wind levels shall be included in the same order as in the sequence \<3 03 054\>, i.e. in descending order with respect to pressure.

**B/C26.7.2 Wind shear data at a pressure level with radiosonde position \<3 03 051\>**

**B/C26.7.2.1 Long time displacement (since launch time)**

> Long time displacement (0 04 086) represents the time offset from the launch time specified in Regulation B/C26.3, and shall be reported in seconds if available.

**B/C26.7.2.2 Extended vertical sounding significance** -- Flag table 0 08 042

> A level, for which wind shear data are reported, shall be indicated by vertical sounding significance 0 08 042 -- bit No. 4 set to 1 (maximum wind level) and by bit No. 7 set to 1 (level significant with respect to wind).

**B/C26.7.2.3 Pressure**

> Pressure (0 07 004) shall be reported in pascals with precision in tens of pascals.

**B/C26.7.2.4 Latitude and longitude displacements**

> Latitude displacement (0 05 015) represents the latitude offset from the latitude of the launch site specified in Regulation B/C26.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available. Longitude displacement 0 06 015 represents the longitude offset from the longitude of the launch site specified in Regulation B/C26.4, and shall be reported in degrees with precision in 10^--5^ of a degree if available.

**B/C26.7.2.5 Wind shear data**

> Absolute wind shear **in 1 km layer below (0 11 061) and a**bsolute wind shear **in 1‑km layer above (0 11 062)** shall be reported in metres per second (with precision in tenths of a metre per second)**, if** data for vertical wind shear are computed and required. \[35.2.4.4\]

**B/C26.8 Data required by regional or national reporting practices**

> If regional or national reporting practices require inclusion of temperature, humidity and/or wind data at additional levels, these data shall be reported using sequence \<3** **03 054\> for Temperature, dewpoint, wind at a pressure level. Regulation B/C26.5 shall apply.
>
> Notes:
>
> \(1) A level determined by regional decision shall be indicated by Extended vertical sounding significance 0 08 042 -- bit No. 15 set to 1.
>
> \(2) A level determined by national decision shall be indicated by Extended vertical sounding significance 0 08 042 -- all bits set to 0.

**B/C26.8.1 Additional data required by reporting practices**

> No regional requirements are indicated for reporting TEMP DROP data in the *Manual on Codes* (WMO-No. 306), Volume II.
>
> \_\_\_\_\_\_\_\_\_\_\_\_\_
