**CREX Table D** *-- List of common sequences*

> F X Category of sequences
>
> D 00 CREX table entries sequences
>
> D 01 Location and identification sequences
>
> D 02 Meteorological sequences common to surface data
>
> D 03 Meteorological sequences common to vertical soundings data
>
> D 04 Meteorological sequences common to satellite observations (*not to be used in CREX for\
> transmission*)
>
> D 05 Meteorological or hydrological sequences common to hydrological observations
>
> D 06 Meteorological or oceanographic sequences common to oceanographic observations
>
> D 07 Surface report sequences (land)
>
> D 08 Surface report sequences (sea)
>
> D 09 Vertical sounding sequences (conventional data)
>
> D 10 Vertical sounding sequences (satellite data) (*not to be used in CREX for transmission*)
>
> D 11 Single level report sequences (conventional data)
>
> D 12 Single level report sequences (satellite data) (*not to be used in CREX for transmission*)
>
> D 13 Sequences common to image data (*not to be used in CREX for transmission*)
>
> D 14 Reserved
>
> D 15 Oceanographic report sequences
>
> D 16 Synoptic feature sequences
>
> D 18 Radiological report sequences
>
> D 21 Radar report sequences (*not to be used in CREX for transmission*)
>
> D 22 Chemical and aerosol sequences
>
> D 35 Monitoring information

Notes:

\(1) From a conceptual point of view, Table D is *not necessary*:

> \(a) The Data description section can fully and completely describe the data using only element descriptors, operator descriptors and the rules of description;
>
> \(b) Such a means of defining the data would involve considerable overheads in terms of the length of the\
> Data description section. Table D is a device to reduce these overheads;
>
> \(c) Each entry within Table D contains a list of descriptors. Each sequence descriptor that references to\
> Table D may be "expanded" by replacing it with the list corresponding to that entry. The process of "expansion" is well defined, provided it results in a set of element descriptors and operator descriptors;
>
> \(d) Descriptors listed in entries to Table D may themselves refer to Table D, provided no circularity results on repeated expansion;
>
> \(e) The initial Table D has been limited to lists of descriptors likely to be used frequently. Every attempt has been made not to produce initial tables that are too comprehensive. *Minor differences of reporting practice can be accommodated by not endeavouring to reduce each observation type to a single descriptor.* Indeed, much more flexibility is retained if the Data description section is envisaged as containing three or four descriptors.

\(2) It should be noted that, initially, effort has been concentrated on the requirements for observational data. Extensions forecast data, time series data, products, etc., follow logically and can be added at an appropriate future date.

\(4) Underwater soundings are included, with some minor omissions, to illustrate the facility to describe data of slightly different contents.

\(7) Categories 48 to 63 are reserved for local use; all other categories are reserved for future development.

\(8) Entries 192 to 255 within all categories are reserved for local use.

*Editorial note: Notes are numbered so as to be consistent with the BUFR Table D for convenience.*

**Category 00 -- *CREX table entries sequences***

+----------+------------+----------------------------------------------+---------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                 | ELEMENT DESCRIPTION |
|          |            |                                              |                     |
|          | REFERENCES |                                              |                     |
+==========+============+==============================================+=====================+
|          | F X Y      |                                              |                     |
+----------+------------+----------------------------------------------+---------------------+
| D 00 010 | D 00 003   | F, X, Y of descriptor to be added or defined |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor          |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | B 00 030   | Descriptor defining sequence                 |                     |
+----------+------------+----------------------------------------------+---------------------+
|          |            |                                              |                     |
+----------+------------+----------------------------------------------+---------------------+
|          |            | (Code table definition)                      |                     |
+----------+------------+----------------------------------------------+---------------------+
| D 00 015 | B 00 030   | Descriptor defining sequence                 |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | R 02 000   | Delayed replication of 2 descriptors         | Up to 9999 entries  |
+----------+------------+----------------------------------------------+---------------------+
|          | B 00 024   | Code figure                                  |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | B 00 025   | Code figure meaning                          |                     |
+----------+------------+----------------------------------------------+---------------------+
|          |            |                                              |                     |
+----------+------------+----------------------------------------------+---------------------+
|          |            | (Flag table definition)                      |                     |
+----------+------------+----------------------------------------------+---------------------+
| D 00 016 | B 00 030   | Descriptor defining sequence                 |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | R 02 000   | Delayed replication of 2 descriptors         |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | B 00 026   | Bit number                                   |                     |
+----------+------------+----------------------------------------------+---------------------+
|          | B 00 027   | Bit number meaning                           |                     |
+----------+------------+----------------------------------------------+---------------------+

Notes:

\(1) These entries include the facility to update the Table A code figure and data description.

\(2) It is better to use different Class 00 descriptors for the defining and defined elements, in the same way as different descriptors correspond to pressure considered as a coordinate and pressure measured at a given point; otherwise special rules would be needed to interpret such message. Entries B 00 010 to B 00 012 define F, X and Y for Tables B and D; entry B 00 030 is a descriptor used as data and provides the F, X and Y values defining a sequence for Table D entries.

\(3) It could be argued that, as only additions are possible, only complete lines should be allowed; but it is conceivable that local areas will require changes as well as additions, so it is better and in any case clearer to provide descriptions for all the fields.

**Category 01 -- *Location and identification sequences***

+----------+------------+-------------------------------------------------------------------------------+-------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                  | ELEMENT DESCRIPTION     |
|          |            |                                                                               |                         |
|          | REFERENCES |                                                                               |                         |
+==========+============+===============================================================================+=========================+
|          | F X Y      |                                                                               |                         |
+----------+------------+-------------------------------------------------------------------------------+-------------------------+
|          |            | (Description of a feature in 3-D or 2-D)                                      |                         |
+----------+------------+-------------------------------------------------------------------------------+-------------------------+
| D 01 027 | B 08 007   | Dimensional significance                                                      | = 0 Point, = 1 Line,\   |
|          |            |                                                                               | = 2 Area, = 3 Volume    |
+----------+------------+-------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor (see Note 5)                              |                         |
+----------+------------+-------------------------------------------------------------------------------+-------------------------+
|          | D 01 028   | Horizontal section of a feature described as a polygon, circle, line or point |                         |
+----------+------------+-------------------------------------------------------------------------------+-------------------------+
|          | B 08 007   | Dimensional significance                                                      | Set to missing (cancel) |
+----------+------------+-------------------------------------------------------------------------------+-------------------------+

Note:

\(5) This replication factor shall have a value of "1" when a 2-D feature is being described, whereas 3-D features may be described via any one of the following methods:

> \(a) Via two or more horizontal sections in successive ascending flight levels. In this case, each section shall be described by an identical number of latitude/longitude points listed in identical order (i.e. where each point x of section n is to be joined via a straight line to point x of section n+1), in order to ensure that the overall shape of the 3-D feature is unambiguously described. In this case, all values reported for B 33 042 shall be "missing".
>
> \(b) Via a single horizontal section with an appropriate value reported for B 33 042, as follows. In all such cases, the corresponding horizontal section description applies throughout the entire region.
>
> \(i) A value of "0" to indicate a region above (but not including) the reported flight level and with unspecified upper bound.
>
> \(ii) A value of "1" to indicate a region above (and including) the reported flight level and with unspecified upper bound.
>
> \(iii) A value of "2" to indicate a region below (but not including) the reported flight level and extending to the surface.
>
> \(iv) A value of "3" to indicate a region below (and including) the reported flight level and extending to the surface.
>
> \(c) Via two replications of the same horizontal section at the same reported flight level, in order to indicate a region extending both below and above (and including!) the reported flight level. In this case, the values reported for the two replications of B 33 042 shall be as follows:
>
> \(i) Values of "3" and "1", respectively, to indicate a region beginning from below a reported flight level, but continuing through that level upward to some unspecified point above (e.g. TOP ABV FL100).
>
> \(ii) Values of "1" and "3", respectively, to indicate a region beginning from above a reported flight level, but continuing through that level downward to some unspecified point below (e.g. CIGS BLW FL010).

**Category 02 -- *Meteorological sequences common to surface data***

+----------+------------+------------------------------------------------------------------+--------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                     | ELEMENT DESCRIPTION            |
|          |            |                                                                  |                                |
|          | REFERENCES |                                                                  |                                |
+==========+============+==================================================================+================================+
|          | F X Y      |                                                                  |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            | (Basic surface report)                                           |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
| D 02 013 | D 02 006   | Pressure and 24-hour pressure change                             |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 003   | Wind, temperature, humidity, visibility, weather                 |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                              |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 005   | Cloud layer                                                      |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            |                                                                  |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            | (Basic synoptic "instantaneous" data)                            |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
| D 02 035 | D 02 032   | Temperature and humidity data                                    |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 033   | Visibility data                                                  |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 034   | Precipitation past 24 hours                                      |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 07 032   | Height of sensor above local ground (or deck of marine platform) | Set to missing (cancel)        |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 004   | General cloud information                                        |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                              |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 005   | Cloud layer                                                      | Individual cloud layer or mass |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            |                                                                  |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            | (Clouds with bases below station level)                          |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
| D 02 036 | R 05 000   | Delayed replication of 5 descriptors                             |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 08 002   | Vertical significance (surface observations)                     |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 20 011   | Cloud amount                                                     |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 20 012   | Cloud type                                                       |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 20 014   | Height of top of cloud                                           |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 20 017   | Cloud top description                                            |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            |                                                                  |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            | (Ship "instantaneous" data)                                      |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
| D 02 054 | D 02 052   | Ship temperature and humidity data                               |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 053   | Ship visibility data                                             |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 07 033   | Height of sensor above water surface                             | Set to missing (cancel)        |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 034   | Precipitation past 24 hours                                      |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 07 032   | Height of sensor above local ground (or deck of marine platform) | Set to missing (cancel)        |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 004   | General cloud information                                        |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                              |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 005   | Cloud layer                                                      |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            |                                                                  |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          |            | ("Instantaneous" data of sequence D 07 096)                      |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
| D 02 084 | D 02 031   | Pressure information                                             |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 02 072   | Temperature and humidity data                                    |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | R 03 000   | Delayed replication of 3 descriptors                             |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | R 01 005   | Replicate 1 descriptor 5 times                                   |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | D 07 063   | Depth below land surface and soil temperature                    |                                |
+----------+------------+------------------------------------------------------------------+--------------------------------+
|          | B 07 061   | Depth below land surface                                         | Set to missing (cancel)        |
+----------+------------+------------------------------------------------------------------+--------------------------------+

*(continued)*

*\
(Category 02 -- continued)*

+---------------+------------+------------------------------------------------------------------+-------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                     | ELEMENT DESCRIPTION     |
|               |            |                                                                  |                         |
|               | REFERENCES |                                                                  |                         |
+===============+============+==================================================================+=========================+
|               | F X Y      |                                                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
| D 02 084      |            | *Visibility data*                                                |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
| (*continued*) | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 069   | Visibility data                                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 07 032   | Height of sensor above local ground (or deck of marine platform) | Set to missing (cancel) |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 07 033   | Height of sensor above water surface                             | Set to missing (cancel) |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | *Marine data*                                                    |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 05 000   | Delayed replication of 5 descriptors                             |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 20 031   | Ice deposit (thickness)                                          |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 20 032   | Rate of ice accretion (estimated)                                |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 02 038   | Method of water temperature and/or salinity\                     |                         |
|               |            | measurement                                                      |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 22 043   | Sea/water temperature                                            | Scale: 2                |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 021   | Waves                                                            |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | *State of ground and snow depth measurement*                     |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 078   | State of ground and snow depth measurement                       |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 12 113   | Ground minimum temperature, past 12 hours                        | Scale: 2                |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | *Cloud data*                                                     |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 004   | General cloud information                                        |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 05 000   | Delayed replication of 5 descriptors                             |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 08 002   | Vertical significance (surface observations)                     |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 20 011   | Cloud amount                                                     |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 20 012   | Cloud type                                                       |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 33 041   | Attribute of following value                                     |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 20 013   | Height of base of cloud                                          |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 036   | Clouds with bases below station level                            |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | *Direction of cloud drift 6D~L~D~M~D~H~*                         |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 047   | Direction of cloud drift                                         |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 08 002   | Vertical significance (surface observations)                     | Set to missing (cancel) |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | *Direction and elevation of cloud 57CD~a~e~c~*                   |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 048   | Direction and elevation of cloud                                 |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            |                                                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | ("Period" data of sequence D 07 096)                             |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               |            | *Present and past weather data*                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
| D 02 085      | R 05 000   | Delayed replication of 5 descriptors                             |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 20 003   | Present weather                                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 03 002   | Replicate 3 descriptors 2 times                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+

*(continued)*

*\
(Category 02 -- continued)*

+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                         | ELEMENT DESCRIPTION                                                     |
|               |            |                                                                      |                                                                         |
|               | REFERENCES |                                                                      |                                                                         |
+===============+============+======================================================================+=========================================================================+
|               | F X Y      |                                                                      |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
| D 02 085\     | B 04 024   | Time period or displacement                                          | /see left column                                                        |
| (*continued*) |            |                                                                      |                                                                         |
|               |            | > = --1 hour in the first replication,\                              |                                                                         |
|               |            | > = --x hours in the second replication,\                            |                                                                         |
|               |            | > x corresponding to the time period of W~1~W~2~ in the SYNOP report |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 20 004   | Past weather (1)                                                     |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 20 005   | Past weather (2)                                                     |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               |            | *Intensity of precipitation, size of precipitation\                  |                                                                         |
|               |            | element*                                                             |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                  |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | D 02 175   | Intensity of precipitation, size of precipitation element            |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               |            | *Precipitation, obscuration and other phenomena*                     |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                 |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 04 025   | Time period or displacement                                          | = --10 minutes                                                          |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | D 02 076   | Precipitation, obscuration and other phenomena                       |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               |            | *Lightning data*                                                     |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                 |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 04 025   | Time period or displacement                                          | = --10 minutes                                                          |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 13 059   | Number of flashes (thunderstorm)                                     |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               |            | *Wind data*                                                          |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 07 032   | Height of sensor above local ground (or deck of marine platform)     |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 07 033   | Height of sensor above water surface                                 |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 08 021   | Time significance                                                    | = 2 Time averaged                                                       |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 04 025   | Time period or displacement                                          | = --10 minutes, or number of minutes after a significant change of wind |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 11 001   | Wind direction                                                       |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 11 002   | Wind speed                                                           |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 08 021   | Time significance                                                    | Set to missing                                                          |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | R 03 003   | Replicate 3 descriptors 3 times                                      |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 04 025   | Time period or displacement                                          | / see left column                                                       |
|               |            |                                                                      |                                                                         |
|               |            | > = --10 minutes in the first replication,\                          |                                                                         |
|               |            | > = --60 minutes in the second replication,\                         |                                                                         |
|               |            | > = --60x3 or 60x6 minutes in the third replication                  |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 11 043   | Maximum wind gust direction                                          |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 11 041   | Maximum wind gust speed                                              |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 04 025   | Time period or displacement                                          | = --10 minutes                                                          |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+
|               | B 11 016   | Extreme counterclockwise wind direction of a variable wind           |                                                                         |
+---------------+------------+----------------------------------------------------------------------+-------------------------------------------------------------------------+

*(continued)*

*\
(Category 02 -- continued)*

+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                     | ELEMENT DESCRIPTION                                       |
|               |            |                                                                  |                                                           |
|               | REFERENCES |                                                                  |                                                           |
+===============+============+==================================================================+===========================================================+
|               | F X Y      |                                                                  |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
| D 02 085      | B 11 017   | Extreme clockwise wind direction of a variable wind              |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
| (*continued*) |            | *Extreme temperature data*                                       |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 077   | Extreme temperature data                                         |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 07 033   | Height of sensor above water surface                             | Set to missing (cancel)                                   |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 041   | Extreme temperature data                                         |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               |            | *Precipitation measurement*                                      |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 06 000   | Delayed replication of 6 descriptors                             |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 07 032   | Height of sensor above local ground (or deck of marine platform) |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 02 175   | Method of precipitation measurement                              |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 02 178   | Method of liquid content measurement of precipitation            |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 02 005   | Replicate 2 descriptors 5 times                                  |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 04 024   | Time period or displacement                                      | = --1 hour in the first replication,\                     |
|               |            |                                                                  | = --3, --6, --12 and --24 hours in the other replications |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 13 011   | Total precipitation/total water equivalent                       |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 07 032   | Height of sensor above local ground (or deck of marine platform) | Set to missing (cancel)                                   |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               |            | *Evaporation data*                                               |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 03 000   | Delayed replication of 3 descriptors                             |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | B 02 185   | Method of evaporation measurement                                |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 01 002   | Replicate 1 descriptor 2 times                                   |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 044   | Evaporation data                                                 |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               |            | *Total sunshine data*                                            |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                             |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 01 002   | Replicate 1 descriptor 2 times                                   |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 039   | Sunshine data (from 1 hour and 24-hour period)                   |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               |            | *Radiation data*                                                 |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                             |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 01 002   | Replicate 1 descriptor 2 times                                   |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 045   | Radiation data (from 1 hour and 24-hour period)                  |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               |            | *Temperature change group 54g~0~s~n~d~T~*                        |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 046   | Temperature change                                               |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               |            | *First-order statistics of P, W, T, U data*                      |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+
|               | D 02 083   | First-order statistics of P, W, T, U data                        |                                                           |
+---------------+------------+------------------------------------------------------------------+-----------------------------------------------------------+

**Category 05 -- *Meteorological or hydrological sequences common to hydrological observations***

+----------+------------+-------------------------------------------+------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                              | ELEMENT DESCRIPTION                      |
|          |            |                                           |                                          |
|          | REFERENCES |                                           |                                          |
+==========+============+===========================================+==========================================+
|          | F X Y      |                                           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            | (SADC-HYCOS measurement array definition) |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
| D 05 003 | D 01 012   | Hour, minute                              | First single measurement minus increment |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 04 065   | Short time increment                      | Time interval between measurements       |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor       |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | D 05 001   | SADC-HYCOS single measurement             |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            |                                           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            | (MEDHYCOS measurement)                    |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
| D 05 006 | B 13 072   | Downstream water level                    |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 13 082   | Water temperature                         |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 13 019   | Total precipitation past 1 hour           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | C 07 005   | Units replacement                         | Kelvin                                   |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | C 01 004   | Data width replacement                    | 4 characters long                        |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 12 001   | Temperature/air temperature               |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 13 073   | Maximum water level                       |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 13 060   | Total accumulated precipitation           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            |                                           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            | (MEDHYCOS report)                         |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
| D 05 007 | D 01 029   | Identification                            |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | D 01 012   | Hour, minute                              | Time of first measurement                |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 04 065   | Short time increment                      | Time interval between measurements       |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor       |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | D 05 006   | MEDHYCOS measurement                      | Single measurement                       |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            |                                           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            | (AOCHYCOS -- Chad measurement)            |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
| D 05 008 | D 05 006   | MEDHYCOS measurement                      | Same as MEDHYCOS type measurement        |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | C 07 005   | Units replacement                         | Kelvin                                   |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | C 01 004   | Data width replacement                    | 4 characters long                        |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 12 030   | Soil temperature                          | At --50 cm                               |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            |                                           |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          |            | (AOCHYCOS -- Chad report)                 |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
| D 05 009 | D 01 029   | Identification                            |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | D 01 012   | Hour, minute                              | Time of first measurement                |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | B 04 065   | Short time increment                      | Time interval between measurements       |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor       |                                          |
+----------+------------+-------------------------------------------+------------------------------------------+
|          | D 05 008   | AOCHYCOS -- Chad measurement              | Single measurement                       |
+----------+------------+-------------------------------------------+------------------------------------------+

*(continued)*

*\
(Category 05 -- continued)*

+----------+------------+-------------------------------------------------------------+------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                | ELEMENT DESCRIPTION                |
|          |            |                                                             |                                    |
|          | REFERENCES |                                                             |                                    |
+==========+============+=============================================================+====================================+
|          | F X Y      |                                                             |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          |            | (MEDHYCOS report type 2)                                    |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
| D 05 011 | D 01 029   | Identification                                              |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | D 01 012   | Hour, minute                                                | Time of first measurement          |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | B 04 065   | Short time increment                                        | Time interval between measurements |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                         |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | D 05 010   | MEDHYCOS -- Measurement type 2                              | Single measurement                 |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          |            |                                                             |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          |            | (MEDHYCOS report with meteorology and water quality data)   |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
| D 05 018 | D 01 029   | Identification                                              |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | D 01 012   | Hour, minute                                                | Time of first measurement          |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | B 04 065   | Short time increment                                        | Hour increment                     |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | R 03 000   | Delayed replication of 3 descriptors                        |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | D 05 008   | AOCHYCOS -- Chad measurement                                | Same as AOCHYCOS type measurement  |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | D 05 016   | Meteorological parameters associated with hydrological data |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+
|          | D 05 017   | Water quality measurement                                   |                                    |
+----------+------------+-------------------------------------------------------------+------------------------------------+

**Category 06 -- *Meteorological or oceanographic sequences common to ***

***oceanographic observations***

+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                                              | ELEMENT DESCRIPTION                         |
|          |            |                                                                                                           |                                             |
|          | REFERENCES |                                                                                                           |                                             |
+==========+============+===========================================================================================================+=============================================+
|          | F X Y      |                                                                                                           |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            | (Depth, temperature)                                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 001 | B 02 032   | Indicator for digitization                                                                                |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 07 062   | Depth below sea/water surface                                                                             |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 042   | Sea/water temperature                                                                                     |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                                                           |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            | (Depth, temperature, salinity)                                                                            |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 004 | B 02 032   | Indicator for digitization                                                                                |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 02 033   | Method of salinity/depth measurement                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | R 03 000   | Delayed replication of 3 descriptors                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 07 062   | Depth below sea/water surface                                                                             |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 043   | Sea/water temperature                                                                                     |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 062   | Salinity                                                                                                  |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                                                           |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 005 | B 02 031   | Duration and time of current measurement                                                                  |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | R 03 000   | Delayed replication of 3 descriptors                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 07 062   | Depth below sea/water surface                                                                             |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 004   | Direction of current                                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 031   | Speed of current                                                                                          |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                                                           |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            | (Sequence for representation of water level and residual in the time series)                              |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 013 | D 06 012   | Sequence for representation of sensor type, significant qualifier for sensor and status of operation      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | D 01 011   | Year, month, day                                                                                          | Reference date for the time series          |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | D 01 013   | Hour, minute, second                                                                                      | Reference time for the time series          |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 120   | Tide station automated water level check                                                                  |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 121   | Tide station manual water level check                                                                     |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 04 015   | Time increment                                                                                            | Added to reset the reference time           |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 04 065   | Short time increment                                                                                      | Added to each data value in the time series |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                                                                      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 038   | Tidal elevation with respect to local chart datum                                                         |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | B 22 040   | Meteorological residual tidal elevation (surge or offset)                                                 |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                                                           |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          |            | (Sequence for representation of water level in the time series, similar to D 06 013 but with no residual) |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 014 | D 06 012   | Sequence for representation of sensor type, significant qualifier for sensor and status of operation      |                                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+
|          | D 01 011   | Year, month, day                                                                                          | Reference date for the time series          |
+----------+------------+-----------------------------------------------------------------------------------------------------------+---------------------------------------------+

*(continued)*

*\
(Category 06 -- continued)*

+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                                                                      | ELEMENT DESCRIPTION                         |
|               |            |                                                                                                                   |                                             |
|               | REFERENCES |                                                                                                                   |                                             |
+===============+============+===================================================================================================================+=============================================+
|               | F X Y      |                                                                                                                   |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 014\     | D 01 013   | Hour, minute, second                                                                                              | Reference time for the time series          |
| (*continued*) |            |                                                                                                                   |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 120   | Tide station automated water level check                                                                          |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 121   | Tide station manual water level check                                                                             |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 04 015   | Time increment                                                                                                    | Added to reset the reference time           |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 04 065   | Short time increment                                                                                              | Added to each data value in the time series |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                               |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 038   | Tidal elevation with respect to local chart datum                                                                 |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               |            |                                                                                                                   |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               |            | (Tide report identification, water level checks, time increments)                                                 |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 019      | B 01 075   | Tide station identification                                                                                       | Alphanumeric                                |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | D 01 011   | Year, month, day                                                                                                  |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | D 01 012   | Hour, minute                                                                                                      |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 042   | Sea/water temperature                                                                                             |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 120   | Tide station automated water level check                                                                          |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 121   | Tide station manual water level check                                                                             |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | C 01 002   | Data width replacement                                                                                            | 2 characters long                           |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 04 015   | Time increment (see Note 1)                                                                                       |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 04 065   | Short time increment                                                                                              |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               |            |                                                                                                                   |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               |            | (Sequence for representation of DART buoy standard hourly report)                                                 |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
| D 06 030      | D 06 027   | Sequence for representation of DART buoy identi-\                                                                 |                                             |
|               |            | fication, transmitter ID, type of tsunameter and the time the message is transmitted to the ground system         |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | D 06 029   | Sequence for representation of tsunameter sampling information for water column heights in the time series report |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | R 11 000   | Delayed replication of 11 descriptors                                                                             |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 33 002   | Quality information                                                                                               | Message status                              |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | D 01 011   | Year, month, day                                                                                                  | Reference date/time for the time series     |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | D 01 013   | Hour, minute, second                                                                                              |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 25 025   | Battery voltage                                                                                                   | BPR CPU                                     |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 25 025   | Battery voltage                                                                                                   | Acoustic modem DSP                          |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 25 026   | Battery voltage (large range)                                                                                     | Acoustic modem                              |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 185   | BPR transmission count                                                                                            |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 04 015   | Time increment                                                                                                    | Added to reset the reference time           |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 04 065   | Short time increment                                                                                              | Added to each data value in the time series |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | R 01 004   | Replicate 1 descriptor 4 times                                                                                    |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+
|               | B 22 182   | Water column height                                                                                               |                                             |
+---------------+------------+-------------------------------------------------------------------------------------------------------------------+---------------------------------------------+

*(continued)*

*\
(Category 06 -- continued)*

+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                                                                                             | ELEMENT DESCRIPTION                                       |
|          |            |                                                                                                                                                          |                                                           |
|          | REFERENCES |                                                                                                                                                          |                                                           |
+==========+============+==========================================================================================================================================================+===========================================================+
|          | F X Y      |                                                                                                                                                          |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          |            | (Sequence for representation of DART buoy tsunami event reports and extended tsunami event reports)                                                      |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
| D 06 031 | D 06 027   | Sequence for representation of DART buoy identification, transmitter ID, type of tsunameter and the time the message is transmitted to the ground system |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | D 06 029   | Sequence for representation of tsunameter sampling information for water column heights in the time series report                                        |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 01 053   | Tsunameter report sequence number triggered by a tsunami event                                                                                           |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 33 002   | Quality information                                                                                                                                      | Message status                                            |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | D 01 011   | Year, month, day                                                                                                                                         | Time when tsunami is detected                             |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | D 01 013   | Hour, minute, second                                                                                                                                     |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | D 01 011   | Year, month, day                                                                                                                                         | Reference date/time for the time series                   |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | D 01 013   | Hour, minute, second                                                                                                                                     |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 185   | BPR transmission count                                                                                                                                   |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 182   | Water column height                                                                                                                                      | Determination of actual value reported in the time series |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 04 016   | Time increment                                                                                                                                           | Added to reset the reference time                         |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 04 066   | Short time increment                                                                                                                                     | Added to each data value in the time series               |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                                                                      |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 184   | Water column height deviation from the reference value                                                                                                   |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          |            |                                                                                                                                                          |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          |            | (Sequence for representation of detailed spectral wave measurements)                                                                                     |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
| D 06 040 | B 22 078   | Duration of wave record                                                                                                                                  |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 082   | Maximum non-directional spectral wave density                                                                                                            |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | R 06 000   | Delayed replication of 6 descriptors                                                                                                                     | Number of frequency bins                                  |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 080   | Waveband central frequency                                                                                                                               |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 069   | Spectral wave density                                                                                                                                    |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 086   | Mean direction from which waves are coming                                                                                                               |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 087   | Principal direction from which waves are coming                                                                                                          |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 088   | First normalized polar coordinate from Fourier coefficients                                                                                              |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
|          | B 22 089   | Second normalized polar coordinate from Fourier coefficients                                                                                             |                                                           |
+----------+------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+

*(continued)*

*\
(Category 06 -- continued)*

+----------+------------+------------------------------------------------+-------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                   | ELEMENT DESCRIPTION     |
|          |            |                                                |                         |
|          | REFERENCES |                                                |                         |
+==========+============+================================================+=========================+
|          | F X Y      |                                                |                         |
+----------+------------+------------------------------------------------+-------------------------+
|          |            | (Depth and temperature profile (high accuracy\ |                         |
|          |            | /precision))                                   |                         |
+----------+------------+------------------------------------------------+-------------------------+
| D 06 041 | B 02 032   | Indicator for digitization                     | = 0 Fixed sensor depths |
+----------+------------+------------------------------------------------+-------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors           | Number of depths        |
+----------+------------+------------------------------------------------+-------------------------+
|          | B 07 062   | Depth below sea/water surface                  |                         |
+----------+------------+------------------------------------------------+-------------------------+
|          | B 22 043   | Sea/water temperature                          |                         |
+----------+------------+------------------------------------------------+-------------------------+

Note:

\(1) Range of value for parameter B 04 015 limited from --99 to 99; CREX common sequence D 06 019 being the original sequence with 2 characters only for the corresponding descriptor.

**Category 07 -- *Surface report sequences (land)***

+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                    | ELEMENT DESCRIPTION                         |
|          |            |                                                                 |                                             |
|          | REFERENCES |                                                                 |                                             |
+==========+============+=================================================================+=============================================+
|          | F X Y      |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Low altitude station)                                          |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 003 | D 07 001   | Low altitude station                                            | Location (high accuracy) and basic report   |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                             |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | D 02 005   | Cloud layer                                                     |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Low altitude station)                                          |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 004 | D 07 002   | Low altitude station                                            | Location (coarse accuracy) and basic report |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                             |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | D 02 005   | Cloud layer                                                     |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Horizontal visibility)                                         |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 012 | R 03 000   | Delayed replication of 3 descriptors                            | Up to 3                                     |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 08 023   | First-order statistics                                          |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 05 021   | Bearing or azimuth                                              | Direction of visibility observed            |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 001   | Horizontal visibility                                           | VVVV                                        |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Runway visual range)                                           |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 013 | R 06 000   | Delayed replication of 6 descriptors                            | Up to 4                                     |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 01 064   | Runway designator                                               | D~R~D~R~                                    |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 08 014   | Qualifier for runway visual range                               |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 061   | Runway visual range (RVR)                                       | V~R~V~R~V~R~V~R~                            |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 08 014   | Qualifier for runway visual range                               |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 061   | Runway visual range (RVR)                                       | V~R~V~R~V~R~V~R~                            |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 018   | Tendency of runway visual range                                 | i                                           |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Significant present or forecast weather)                       |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 014 | R 01 000   | Delayed replication of 1 descriptor                             | Up to 3                                     |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 019   | Significant present or forecast weather                         | w´w´                                        |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Clouds group(s))                                               |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 015 | R 01 000   | Delayed replication of 1 descriptor                             |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | D 02 005   | Cloud layer                                                     | N~s~N~s~N~s~, CC, h~s~h~s~h~s~              |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 002   | Vertical visibility                                             | VVh~s~h~s~h~s~                              |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Significant recent weather phenomena)                          |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 016 | R 01 000   | Delayed replication of 1 descriptor                             | Up to 3                                     |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 20 020   | Significant recent weather phenomena                            | REw´w´                                      |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            |                                                                 |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          |            | (Wind shear on runway(s))                                       |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
| D 07 017 | R 01 000   | Delayed replication of 1 descriptor                             |                                             |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+
|          | B 11 070   | Designator of the runway affected by wind shear (including ALL) | WS RWYD~R~D~R~                              |
+----------+------------+-----------------------------------------------------------------+---------------------------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                       | ELEMENT DESCRIPTION                           |
|          |            |                                                                    |                                               |
|          | REFERENCES |                                                                    |                                               |
+==========+============+====================================================================+===============================================+
|          | F X Y      |                                                                    |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            | (Trend-type landing forecast)                                      |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
| D 07 018 | B 08 016   | Change qualifier of a trend-type forecast or an aerodrome forecast | TTTTT                                         |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                               | Up to 2                                       |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 08 017   | Qualifier of the time when the forecast change                     | FM, TL, AT                                    |
|          |            |                                                                    |                                               |
|          |            | is expected                                                        |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | D 01 012   | Hour, minute                                                       | GG, gg                                        |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | R 04 000   | Delayed replication of 4 descriptors                               | Up to 1                                       |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 07 006   | Height above station                                               |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 11 001   | Wind direction                                                     | ddd                                           |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 11 002   | Wind speed                                                         | ff                                            |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 11 041   | Maximum wind gust speed                                            | f~m~f~m~                                      |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 009   | General weather indicator (TAF/METAR)                              |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                | Up to 1                                       |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 001   | Horizontal visibility                                              | VVVV                                          |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | D 07 014   | Significant present or forecast weather                            | w´w´                                          |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            |                                                                    |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            | (METAR/SPECI visibility)                                           |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
| D 07 046 | B 20 060   | Prevailing horizontal visibility                                   | VVVV or VVVVNDV                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                               | Up to 2                                       |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 05 021   | Bearing or azimuth                                                 | Direction of minimum visibility observed D~v~ |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 059   | Minimum horizontal visibility                                      | V~N~V~N~V~N~V~N~                              |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            |                                                                    |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            | (METAR/SPECI/TAF clouds), replacing D 07 015                       |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
| D 07 047 | R 05 000   | Delayed replication of 5 descriptors                               |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 08 002   | Vertical significance (surface observations)                       |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 011   | Cloud amount                                                       | N~s~N~s~N~s~                                  |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 012   | Cloud type                                                         | CC                                            |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 013   | Height of base of cloud                                            | h~s~h~s~h~s~ -- m                             |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 092   | Height of base of cloud                                            | h~s~h~s~h~s~ -- ft                            |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 002   | Vertical visibility                                                | VVh~s~h~s~h~s~ -- m                           |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 20 091   | Vertical visibility                                                | VVh~s~h~s~h~s~ -- ft                          |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            |                                                                    |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          |            | (Trend type forecast), replacing D 07 018                          |                                               |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
| D 07 048 | B 08 016   | Change qualifier of a trend-type forecast or an aerodrome forecast | TTTTT NOSIG                                   |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                               | = 0, 1 or 2                                   |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 08 017   | Qualifier of the time when the forecast change is expected         | TT                                            |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | D 01 012   | Hour, minute                                                       | GGgg                                          |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | R 12 000   | Delayed replication of 12 descriptors                              | = 0 or 1                                      |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 07 032   | Height of sensor above local ground (or deck of marine platform)   | = 10 m (if the actual value is not available) |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 11 001   | Wind direction                                                     | ddd                                           |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+
|          | B 08 054   | Qualifier for wind speed or wind gusts                             | P                                             |
+----------+------------+--------------------------------------------------------------------+-----------------------------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+---------------+------------+------------------------------------------------------------------+--------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                     | ELEMENT DESCRIPTION                  |
|               |            |                                                                  |                                      |
|               | REFERENCES |                                                                  |                                      |
+===============+============+==================================================================+======================================+
|               | F X Y      |                                                                  |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
| D 07 048      | B 11 083   | Wind speed (see Note 5)                                          | ff -- km/h                           |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
| (*continued*) | B 11 084   | Wind speed (see Note 5)                                          | ff -- kt                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 11 002   | Wind speed (see Note 5)                                          | ff -- m/s                            |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 08 054   | Qualifier for wind speed or wind gusts                           | P                                    |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 11 085   | Maximum wind gust speed (see Note 6)                             | f~m~f~m~ -- km/h                     |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 11 086   | Maximum wind gust speed (see Note 6)                             | f~m~f~m~ -- kt                       |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 11 041   | Maximum wind gust speed (see Note 6)                             | f~m~f~m~ -- m/s                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 08 054   | Qualifier for wind speed or wind gusts                           | Set to missing (cancel)              |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 07 032   | Height of sensor above local ground (or deck of marine platform) | Set to missing (cancel)              |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 009   | General weather indicator (TAF/METAR)                            | CAVOK NSW NSC                        |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              | = 0 or 1                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 060   | Prevailing horizontal visibility                                 | VVVV                                 |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 014   | Significant present and forecast weather                         | Weather intensity and phenomena w´w´ |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 047   | METAR/SPECI/TAF clouds, replacing D 07 015                       | N~s~N~s~N~s~h~s~h~s~h~s~             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               |            |                                                                  |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               |            | (Sea conditions)                                                 |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
| D 07 049      | R 02 000   | Delayed replication of 2 descriptors                             | = 0 or 1                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 22 043   | Sea/water temperature                                            | T~s~T~s~                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 22 021   | Height of waves                                                  | S´                                   |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               |            |                                                                  |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               |            | (Runway state)                                                   |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
| D 07 050      | R 01 000   | Delayed replication of 1 descriptor                              | = 0 or 1                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 085   | General condition of runway                                      | SNOCLO                               |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                             |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 01 064   | Runway designator                                                | D~R~D~R~                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 085   | General condition of runway                                      | CLRD//                               |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | R 05 000   | Delayed replication of 5 descriptors                             |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 01 064   | Runway designator                                                | D~R~D~R~                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 086   | Runway deposits                                                  | E~R~                                 |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 087   | Runway contamination                                             | C~R~                                 |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 088   | Depth of runway deposits                                         | e~R~e~R~                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | B 20 089   | Runway friction coefficient                                      | B~R~B~R~                             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               |            |                                                                  |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               |            | (Full METAR/SPECI), replacing D 07 021                           |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
| D 07 051      | D 07 045   | Main part of METAR/SPECI, replacing D 07 011                     |                                      |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 046   | METAR/SPECI visibility                                           | VVVV or\                             |
|               |            |                                                                  | VVVVNDV V~N~V~N~V~N~V~N~D~V~         |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 013   | Runway visual range                                              | RD~R~D~R~/V~R~V~R~V~R~V~R~           |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 014   | Significant present and forecast weather                         | Weather intensity and phenomena w´w´ |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 047   | METAR/SPECI/TAF clouds, replacing D 07 015                       | N~s~N~s~N~s~h~s~h~s~h~s~             |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 016   | Significant recent weather phenomena                             | REw´w´                               |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+
|               | D 07 017   | Wind shear on runway(s)                                          | WS RD~R~D~R~                         |
+---------------+------------+------------------------------------------------------------------+--------------------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                                                                                                   | ELEMENT DESCRIPTION                                                             |
|               |            |                                                                                                                                                |                                                                                 |
|               | REFERENCES |                                                                                                                                                |                                                                                 |
+===============+============+================================================================================================================================================+=================================================================================+
|               | F X Y      |                                                                                                                                                |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
| D 07 051      | D 07 049   | Sea conditions                                                                                                                                 | WT~s~T~s~/SS´                                                                   |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
| (*continued*) | D 07 050   | Runway state                                                                                                                                   | RD~R~D~R~/E~R~C~R~e~R~e~R~B~R~B~R~                                              |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            | = 0 to 3 normally                                                               |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 07 048   | Trend type forecast, replacing D 07 018                                                                                                        |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               |            |                                                                                                                                                |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               |            | (Aerodrome forecast -- full TAF)                                                                                                               |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
| D 07 056      | D 07 052   | Aerodrome forecast identification and time interval                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 07 053   | Forecast weather at an aerodrome                                                                                                               |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 07 054   | Forecast of extreme temperatures                                                                                                               |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 07 055   | Change indicator and forecast changes                                                                                                          |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               |            |                                                                                                                                                |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               |            | (Sequence for representation of synoptic reports from fixed land stations suitable for SYNOP data and for maritime data from coastal stations) |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
| D 07 079      | D 01 090   | Surface station identification; time, horizontal and vertical coordinates                                                                      |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 031   | Pressure information                                                                                                                           |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 035   | Basic synoptic "instantaneous" data                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 036   | Clouds with bases below station level                                                                                                          |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 047   | Direction of cloud drift                                                                                                                       |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | B 08 002   | Vertical significance (surface observations)                                                                                                   |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 048   | Direction and elevation of cloud                                                                                                               |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 037   | State of ground, snow depth, ground minimum temperature                                                                                        |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                                                                                           |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | B 22 061   | State of the sea                                                                                                                               |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | B 20 058   | Visibility seawards from a coastal station                                                                                                     |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 056   | Sea/water temperature                                                                                                                          | Sea/water surface temperature, method of measurement, depth below water surface |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 055   | Icing and ice                                                                                                                                  |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 043   | Basic synoptic "period" data                                                                                                                   |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 044   | Evaporation data                                                                                                                               |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 045   | Radiation data (from 1 hour and 24-hour period)                                                                                                |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                            |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+
|               | D 02 046   | Temperature change                                                                                                                             |                                                                                 |
+---------------+------------+------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                                                                                        | ELEMENT DESCRIPTION                                             |
|          |            |                                                                                                                                                     |                                                                 |
|          | REFERENCES |                                                                                                                                                     |                                                                 |
+==========+============+=====================================================================================================================================================+=================================================================+
|          | F X Y      |                                                                                                                                                     |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          |            | (Sequence for representation of synoptic reports from a fixed land station suitable for SYNOP data in compliance with reporting practices in RA IV) |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
| D 07 084 | D 01 090   | Surface station identification; time, horizontal and vertical coordinates                                                                           |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 031   | Pressure information                                                                                                                                |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 035   | Basic synoptic "instantaneous" data                                                                                                                 |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 036   | Clouds with bases below station level                                                                                                               |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 047   | Direction of cloud drift                                                                                                                            |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 08 002   | Vertical significance (surface observations)                                                                                                        | Set to missing (cancel)                                         |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 048   | Direction and elevation of cloud                                                                                                                    |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 037   | State of ground, snow depth, ground minimum temperature                                                                                             |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 20 055   | State of sky in the tropics                                                                                                                         |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                                                                 |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | C 05 001   | Character insertion                                                                                                                                 | Character field of 1 character                                  |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 043   | Basic synoptic "period" data                                                                                                                        |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 044   | Evaporation data                                                                                                                                    |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | R 01 002   | Replicate 1 descriptor 2 times                                                                                                                      |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 045   | Radiation data (from 1 hour and 24-hour period)                                                                                                     |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 046   | Temperature change                                                                                                                                  |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          |            |                                                                                                                                                     |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          |            | ("Instantaneous" parameters of sequence D 07 089)                                                                                                   |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          |            | *Surface station identification, time, horizontal and\                                                                                              |                                                                 |
|          |            | vertical coordinates*                                                                                                                               |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
| D 07 087 | D 01 001   | WMO block and station number                                                                                                                        | IIiii                                                           |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 02 001   | Type of station                                                                                                                                     | i~x~                                                            |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 01 011   | Year, month, day                                                                                                                                    | YY                                                              |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 01 012   | Hour, minute                                                                                                                                        | GG, gg                                                          |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 01 023   | Latitude/longitude (coarse accuracy)                                                                                                                |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 07 030   | Height of station ground above mean sea level                                                                                                       |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 07 031   | Height of barometer above mean sea level                                                                                                            |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          |            | *Pressure data*                                                                                                                                     |                                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | D 02 001   | Pressure and 3-hour pressure change                                                                                                                 | P~o~P~o~P~o~P~o~, PPPP, ppp,\                                   |
|          |            |                                                                                                                                                     | a                                                               |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 10 062   | 24-hour pressure change                                                                                                                             | p~24~p~24~p~24~                                                 |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 07 004   | Pressure                                                                                                                                            | Standard level a~3\                                             |
|          |            |                                                                                                                                                     | ~= 925, 850, 700, .. hPa \| Set to missing for lowland stations |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
|          | B 10 009   | Geopotential height                                                                                                                                 | Standard level hhh \|\                                          |
|          |            |                                                                                                                                                     | Set to missing for lowland stations                             |
+----------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | ELEMENT DESCRIPTION          |
|               |            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                              |
|               | REFERENCES |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                              |
+===============+============+======================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+==============================+
|               | F X Y      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
| D 07 087      |            | *Temperature and humidity*                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
| (*continued*) | B 07 032   | Height of sensor above local ground (or deck of marine platform)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Temperature measurement      |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | B 12 101   | Temperature/air temperature                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | s~n~TTT \| Scale: 2          |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | B 12 103   | Dewpoint temperature                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | s~n~T~d~T~d~T~d~ \| Scale: 2 |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | B 13 003   | Relative humidity                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | B 07 032   | Height of sensor above local ground (or deck of marine platform)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Set to missing (cancel)      |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               |            | *Visibility*                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | B 20 001   | Horizontal visibility                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | VV                           |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               |            | *Cloud data*                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | D 02 004   | General cloud information                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | /see left column             |
|               |            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                              |
|               |            | > Cloud cover (total) N:\                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                              |
|               |            | > If N = 9, then B 20 010 = 113, if N = /, then B 20 010 = missing **\|** Vertical significance: If C~L~ are observed, then B 08 002 = 7 **\|** Low cloud:\                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                              |
|               |            | > If C~L~ are not observed and C~M~ are observed, then B 08 002 = 8 **\|** Middle cloud: If only C~H~ are observed, B 08 002 = 0, if N = 9, then B 08 002 = 5, if N = 0, then B 08 002 = 62, if N = /, then B 08 002 = missing **\|** Cloud amount (of low or middle clouds) N~h~: If N = 0, then B 20 011 = 0, if N = 9, then B 20 011 = 9, if N = /, then B 20 011 = missing **\|** Height of base of cloud h: If N = 0 or /, then B 20 013 = missing **\|** Cloud type (low clouds) C~L~: B 20 012 = C~L~ + 30, if N = 0, then B 20 012 = 30, if N = 9 or /, then B 20 012 = 62 **\|** Cloud type (middle clouds) C~M~: B 20 012 = C~M~ + 20, if N = 0, then B 20 012 = 20, if N = 9 or / or C~M~ = /, then B 20 012 = 61 **\|**\ |                              |
|               |            | > Cloud type (high clouds) C~H~: B 20 012 = C~H~ + 10, if N = 0, then B 20 012 = 10, if N = 9 or / or C~H~ = /, then B 20 012 = 60                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
|               | D 02 005   | Cloud layer                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | /see left column             |
|               |            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                              |
|               |            | > Vertical significance: In any Cb layer, B 08 002 = 4, else in the first replication, if N = 9, then B 08 002 = 5, if N = /, then B 08 002 = missing, else B 08 002 = 1, in the other replications B 08 002 = 2, 3, 4 **\|**\                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                              |
|               |            | > Cloud amount N~s~: In the first replication, if N = /, then B 20 011 = missing, else B 20 011 = N~s~, in the other replications B 20 011 = N~s~ **\|** Cloud type C:\                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                              |
|               |            | > If N = 9 or /, then B 20 012 = missing, else B 20 012 = C **\|** Height of base of cloud h~s~h~s~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                              |
+---------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                                               | ELEMENT DESCRIPTION     |
|          |            |                                                                                                            |                         |
|          | REFERENCES |                                                                                                            |                         |
+==========+============+============================================================================================================+=========================+
|          | F X Y      |                                                                                                            |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          |            | (CREX template for surface observations from one-hour period with national and WMO station identification) |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
| D 07 091 | D 01 089   | National station identification                                                                            |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 01 090   | Surface station identification; time, horizontal and vertical coordinates                                  |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 08 010   | Surface qualifier (temperature data)                                                                       |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 01 091   | Surface station instrumentation                                                                            |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 001   | Pressure and 3-hour pressure change                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 07 004   | Pressure                                                                                                   | Standard level          |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 10 009   | Geopotential height                                                                                        | Standard level          |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 072   | Temperature and humidity data                                                                              |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 03 000   | Delayed replication of 3 descriptors                                                                       |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 005   | Replicate 1 descriptor 5 times                                                                             |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 07 063   | Depth below land surface and soil temperature                                                              |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 07 061   | Depth below land surface                                                                                   | Set to missing (cancel) |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 069   | Visibility data                                                                                            |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 07 032   | Height of sensor above local ground (or deck of marine platform)                                           | Set to missing (cancel) |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 07 033   | Height of sensor above water surface                                                                       | Set to missing (cancel) |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 05 000   | Delayed replication of 5 descriptors                                                                       |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 20 031   | Ice deposit (thickness)                                                                                    |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 20 032   | Rate of ice accretion (estimated)                                                                          |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 02 038   | Method of water temperature and/or salinity measurement                                                    |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 22 043   | Sea/water temperature                                                                                      | Scale: 2                |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 021   | Waves                                                                                                      |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 078   | State of ground and snow depth measurement                                                                 |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 073   | Cloud data                                                                                                 |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 074   | Present and past weather                                                                                   |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 175   | Intensity of precipitation, size of precipitation element                                                  |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                                                                       |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 04 025   | Time period or displacement                                                                                | = --10 (minutes)        |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 076   | Precipitation, obscuration and other phenomena                                                             |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 071   | Wind data from one-hour period                                                                             |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | D 02 077   | Extreme temperature data                                                                                   |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | B 07 033   | Height of sensor above water surface                                                                       | Set to missing (cancel) |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                        |                         |
+----------+------------+------------------------------------------------------------------------------------------------------------+-------------------------+

*(continued)*

*\
(Category 07 -- continued)*

+---------------+------------+------------------------------------------------------------------+-------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                     | ELEMENT DESCRIPTION     |
|               |            |                                                                  |                         |
|               | REFERENCES |                                                                  |                         |
+===============+============+==================================================================+=========================+
|               | F X Y      |                                                                  |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
| D 07 091      | D 02 079   | Precipitation measurement                                        |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
| (*continued*) | B 07 032   | Height of sensor above local ground (or deck of marine platform) | Set to missing (cancel) |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 080   | Evaporation measurement                                          |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 081   | Total sunshine data                                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 082   | Radiation data                                                   |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                             |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 04 025   | Time period or displacement                                      | = --10 (minutes)        |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 13 059   | Number of flashes (thunderstorm)                                 |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                              |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | D 02 083   | First-order statistics of P, W, T, U data                        |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 33 005   | Quality information (AWS data)                                   |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+
|               | B 33 006   | Internal measurement status information (AWS)                    |                         |
+---------------+------------+------------------------------------------------------------------+-------------------------+

Notes:

*(5) Within D 07 045, D 07 048 and D 07 053, wind speed shall be reported in the same units as in the original TAC data and:*

*B 11 083 shall be set to missing, if wind speed is reported in knots or m s^--1^ in TAC data,*

*B 11 084 shall be set to missing, if wind speed is reported in km h^--1^ or m s^--1^ in TAC data.*

*(6) Within D 07 045, D 07 048 and D 07 053, maximum wind speed (gusts) shall be reported in the same units as in the original TAC data and:*

*B 11 085 shall be set to missing, if maximum wind speed is reported in knots or m s^--1^ in TAC data,*

*B 11 086 shall be set to missing, if maximum wind speed is reported in km h^--1^ or m s^--1^ in TAC data.*

**Category 08 -- *Surface report sequences (sea)***

+----------+------------+-----------------------------------------+---------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                            | ELEMENT DESCRIPTION |
|          |            |                                         |                     |
|          | REFERENCES |                                         |                     |
+==========+============+=========================================+=====================+
|          | F X Y      |                                         |                     |
+----------+------------+-----------------------------------------+---------------------+
|          |            | (TRACKOB template)                      |                     |
+----------+------------+-----------------------------------------+---------------------+
| D 08 010 | B 01 011   | Ship or mobile land station identifier  |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | R 13 000   | Delayed replication of 13 descriptors   |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | D 01 011   | Year, month, day                        |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | D 01 012   | Hour, minute                            |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | D 01 021   | Latitude/longitude (high accuracy)      |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 04 080   | Averaging period for following value    |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 22 049   | Sea-surface temperature                 |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 04 080   | Averaging period for following value    |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 22 059   | Sea-surface salinity                    |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 04 080   | Averaging period for following value    |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 22 005   | Direction of sea-surface current        |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 02 042   | Indicator for sea-surface current speed |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 22 032   | Speed of sea-surface current            |                     |
+----------+------------+-----------------------------------------+---------------------+
|          | B 02 042   | Indicator for sea-surface current speed | Cancel              |
+----------+------------+-----------------------------------------+---------------------+
|          | B 04 080   | Averaging period for following value    | Cancel              |
+----------+------------+-----------------------------------------+---------------------+

**Category 09 -- *Vertical sounding sequences (conventional data)***

+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                            | ELEMENT DESCRIPTION                                           |
|          |            |                                                                         |                                                               |
|          | REFERENCES |                                                                         |                                                               |
+==========+============+=========================================================================+===============================================================+
|          | F X Y      |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 001 | D 01 037   | Land station for vertical soundings                                     | Identification, etc. (land station, high accuracy position)   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 011   | Wind at height                                                          |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 002 | D 01 038   | Land station for vertical soundings                                     | Identification, etc. (land station, coarse accuracy position) |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 011   | Wind at height                                                          |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 003 | D 01 037   | Land station for vertical soundings                                     | Identification, etc. (land station, high accuracy position)   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 012   | Wind at pressure level                                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 004 | D 01 038   | Land station for vertical soundings                                     | Identification, etc. (land station, coarse accuracy position) |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 012   | Wind at pressure level                                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical sounding with relative humidity)                              |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 005 | D 01 037   | Land station for vertical soundings                                     | Identification, etc. (land station, high accuracy position)   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 02 004   | General cloud information                                               | Significant cloud layer                                       |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 013   | Geopotential, temperature, humidity, wind at pressure level             |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical sounding with relative humidity)                              |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 006 | D 01 038   | Land station for vertical soundings                                     | Identification, etc. (land station, coarse accuracy position) |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 02 004   | General cloud information                                               | Significant cloud layer                                       |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 013   | Geopotential, temperature, humidity, wind at pressure level             |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical sounding with dewpoint data)                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 007 | D 01 037   | Land station for vertical soundings                                     | Identification, etc. (land station, high accuracy position)   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 02 004   | General cloud information                                               | Significant cloud layer                                       |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 014   | Geopotential, temperature, dewpoint temperature, wind at pressure level |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+

*(continued)*

*\
(Category 09 -- continued)*

+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                            | ELEMENT DESCRIPTION                                           |
|          |            |                                                                         |                                                               |
|          | REFERENCES |                                                                         |                                                               |
+==========+============+=========================================================================+===============================================================+
|          | F X Y      |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical sounding with dewpoint data)                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 008 | D 01 038   | Land station for vertical soundings                                     | Identification, etc. (land station, coarse accuracy position) |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 02 004   | General cloud information                                               | Significant cloud layer                                       |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 014   | Geopotential, temperature, dewpoint temperature, wind at pressure level |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 011 | D 01 039   | Ship for vertical soundings                                             | Ship's identification, etc.                                   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 011   | Wind at height                                                          |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 012 | D 01 039   | Ship for vertical soundings                                             | Ship's identification, etc.                                   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 012   | Wind at pressure level                                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical sounding with relative humidity)                              |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 013 | D 01 039   | Ship for vertical soundings                                             | Ship's identification, etc.                                   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 02 004   | General cloud information                                               | Significant cloud layer                                       |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 013   | Geopotential, temperature, humidity, wind at pressure level             |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical sounding with dewpoint data)                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 014 | D 01 039   | Ship for vertical soundings                                             | Ship's identification, etc.                                   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 02 004   | General cloud information                                               | Significant cloud layer                                       |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 014   | Geopotential, temperature, dewpoint temperature, wind at pressure level |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 015 | D 01 040   | Ship for vertical soundings                                             | Ship's identification, etc.                                   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 011   | Wind at height                                                          |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            |                                                                         |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          |            | (Vertical wind profile)                                                 |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
| D 09 016 | D 01 040   | Ship for vertical soundings                                             | Ship's identification, etc.                                   |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                     |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+
|          | D 03 012   | Wind at pressure level                                                  |                                                               |
+----------+------------+-------------------------------------------------------------------------+---------------------------------------------------------------+

*(continued)*

*\
(Category 09 -- continued)*

+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                               | ELEMENT DESCRIPTION                      |
|          |            |                                                                                            |                                          |
|          | REFERENCES |                                                                                            |                                          |
+==========+============+============================================================================================+==========================================+
|          | F X Y      |                                                                                            |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            | (Vertical sounding with relative humidity)                                                 |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| D 09 017 | D 01 040   | Ship for vertical soundings                                                                | Ship's identification, etc.              |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | D 02 004   | General cloud information                                                                  | Significant cloud layer                  |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                        |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | D 03 013   | Geopotential, temperature, humidity, wind at pressure level                                |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            |                                                                                            |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            | (Vertical sounding with dewpoint data)                                                     |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| D 09 018 | D 01 040   | Ship for vertical soundings                                                                | Ship's identification, etc.              |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | D 02 004   | General cloud information                                                                  | Significant cloud layer                  |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                        |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | D 03 014   | Geopotential, temperature, dewpoint temperature, wind at pressure level                    |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            |                                                                                            |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            | (Wind profiler -- wind data sounding)                                                      |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| D 09 019 | D 01 031   | Identification and type of station, date/time, location (high accuracy), height of station |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 02 003   | Type of measuring equipment used                                                           |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                        |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | D 03 011   | Wind at height                                                                             |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            |                                                                                            |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            | (Wind profiler -- Cartesian coordinates)                                                   |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| D 09 020 | D 01 031   | Identification and type of station, date/time, location (high accuracy), height of station |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 02 003   | Type of measuring equipment used                                                           |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | R 04 000   | Delayed replication of 4 descriptors                                                       |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 07 003   | Geopotential                                                                               |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 11 003   | u-component                                                                                |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 11 004   | v-component                                                                                |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 11 005   | w-component                                                                                |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            |                                                                                            |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            | (Ozone sonde flight data) (see Note 1)                                                     |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| D 09 030 | B 15 004   | Ozone sounding correction factor (CF)                                                      |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 15 005   | Ozone p                                                                                    |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | R 04 000   | Delayed replication of 4 descriptors                                                       |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 04 015   | Time increment                                                                             | Since launch time, if needed, in minutes |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 08 006   | Ozone vertical sounding significance                                                       |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 07 004   | Pressure                                                                                   |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 15 003   | Measured ozone partial pressure (sounding)                                                 |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            |                                                                                            |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          |            | (Ozone sonde flight data)                                                                  |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
| D 09 031 | B 15 004   | Ozone sounding correction factor (CF)                                                      |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 15 005   | Ozone p                                                                                    |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | R 04 000   | Delayed replication of 4 descriptors                                                       |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 04 025   | Time period or displacement                                                                | Since launch time in minutes             |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 08 006   | Ozone vertical sounding significance                                                       |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 07 004   | Pressure                                                                                   |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+
|          | B 15 003   | Measured ozone partial pressure (sounding)                                                 |                                          |
+----------+------------+--------------------------------------------------------------------------------------------+------------------------------------------+

*(continued)*

*\
(Category 09 -- continued)*

+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                               | ELEMENT DESCRIPTION                   |
|          |            |                                                                            |                                       |
|          | REFERENCES |                                                                            |                                       |
+==========+============+============================================================================+=======================================+
|          | F X Y      |                                                                            |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          |            | (Sequence for representation of CLIMAT TEMP and CLIMAT TEMP SHIP data)     |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
| D 09 054 | D 01 001   | WMO block and station numbers                                              | Identification of launch site         |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 01 011   | Ship or mobile land station identifier                                     | Ship's call sign                      |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | D 01 011   | Year, month, day                                                           |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | D 01 012   | Hour, minute                                                               |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | D 01 021   | Latitude/longitude (high accuracy)                                         |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 07 030   | Height of station ground above mean sea level                              |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 07 031   | Height of barometer above mean sea level                                   |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 07 007   | Height                                                                     | Release of sonde above mean sea level |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          |            | *Monthly mean data*                                                        |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 04 023   | Time period or displacement                                                | Number of days in the month           |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 04 059   | Times of observation used to compute the reported mean values              |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | R 15 000   | Delayed replication of 15 descriptors                                      |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 001   | Vertical sounding significance                                             |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 023   | First-order statistics                                                     | = 4 Mean value                        |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 07 004   | Pressure                                                                   |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 10 009   | Geopotential height                                                        |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 12 101   | Temperature/air temperature                                                |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 12 103   | Dewpoint temperature                                                       |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 023   | First-order statistics                                                     | = 32 Vector mean                      |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 11 001   | Wind direction                                                             |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 11 002   | Wind speed                                                                 |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 023   | First-order statistics                                                     | Set to missing                        |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 11 019   | Steadiness of wind                                                         |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 050   | Qualifier for number of missing values in calculation of statistic         | = 2 Temperature                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 020   | Total number of missing entities (with respect to accumulation or average) | Days                                  |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 050   | Qualifier for number of missing values in calculation of statistic         | = 9 Wind                              |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 08 020   | Total number of missing entities (with respect to accumulation or average) | Days                                  |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          |            |                                                                            |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          |            | (Sequence for representation of PILOT in the area of ASECNA)               |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
| D 09 071 | D 01 001   | WMO block and station numbers                                              |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 02 014   | Tracking technique/status of system used                                   |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 02 003   | Type of measuring equipment used                                           |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | D 01 113   | Date/time of launch                                                        |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | D 01 114   | Horizontal and vertical coordinates of launch site                         |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | D 01 023   | Latitude/longitude (coarse accuracy)                                       |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 07 030   | Height of station ground above mean sea level                              |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | B 07 007   | Height                                                                     | Release of balloon                    |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+
|          | R 03 000   | Delayed replication of 3 descriptors                                       |                                       |
+----------+------------+----------------------------------------------------------------------------+---------------------------------------+

*(continued)*

*\
(Category 09 -- continued)*

+---------------+------------+---------------------+---------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME        | ELEMENT DESCRIPTION |
|               |            |                     |                     |
|               | REFERENCES |                     |                     |
+===============+============+=====================+=====================+
|               | F X Y      |                     |                     |
+---------------+------------+---------------------+---------------------+
| D 09 071      | B 07 009   | Geopotential height |                     |
+---------------+------------+---------------------+---------------------+
| (*continued*) | B 11 001   | Wind direction      |                     |
+---------------+------------+---------------------+---------------------+
|               | B 11 002   | Wind speed          |                     |
+---------------+------------+---------------------+---------------------+

Note:

\(1) Sequence D 09 030 is deprecated because of incorrect usage of descriptor B 04 015; sequence D 09 031 should be used instead.

**Category 11 -- *Single level report sequences (conventional data)***

+----------+------------+--------------------------------------------------------------------------------------+---------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                         | ELEMENT DESCRIPTION |
|          |            |                                                                                      |                     |
|          | REFERENCES |                                                                                      |                     |
+==========+============+======================================================================================+=====================+
|          | F X Y      |                                                                                      |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          |            | (ACARS supplementary reported variables)                                             |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
| D 11 004 | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 11 034   | Vertical gust velocity                                                               |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 11 035   | Vertical gust acceleration                                                           |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 11 075   | Mean turbulence intensity (eddy dissipation rate)                                    |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 11 076   | Peak turbulence intensity (eddy dissipation rate)                                    |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 33 025   | ACARS interpolated values indicator                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 33 026   | Moisture quality                                                                     |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          |            |                                                                                      |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          |            | (Aircraft ascent/descent profile without latitude/longitude indicated at each level) |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
| D 11 008 | B 01 008   | Aircraft registration number or other identification                                 |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 01 011   | Year, month, day                                                                     |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 01 013   | Hour, minute, second                                                                 |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 01 021   | Latitude/longitude (high accuracy)                                                   |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 08 004   | Phase of aircraft flight                                                             |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 11 006   | AMDAR data or aircraft data for one level without latitude/longitude                 |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          |            |                                                                                      |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          |            | (Aircraft ascent/descent profile with latitude/longitude given for each level)       |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
| D 11 009 | B 01 008   | Aircraft registration number or other identification                                 |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 01 011   | Year, month, day                                                                     |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 01 013   | Hour, minute, second                                                                 |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 01 021   | Latitude/longitude (high accuracy)                                                   |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | B 08 004   | Phase of aircraft flight                                                             |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                  |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+
|          | D 11 007   | Aircraft data for one level with latitude/longitude indicated                        |                     |
+----------+------------+--------------------------------------------------------------------------------------+---------------------+

**Category 15 -- *Oceanographic report sequences***

+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                                                                                                 | ELEMENT DESCRIPTION                                 |
|          |            |                                                                                                                                                              |                                                     |
|          | REFERENCES |                                                                                                                                                              |                                                     |
+==========+============+==============================================================================================================================================================+=====================================================+
|          | F X Y      |                                                                                                                                                              |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | (Sequence for representation of data derived from a ship-based lowered instrument measuring subsurface sea/water temperature, salinity and current profiles) |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
| D 15 007 | D 01 003   | Ship's call sign and motion                                                                                                                                  |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Extended identification*                                                                                                                                    |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 019   | Long station or site name                                                                                                                                    |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 103   | IMO Number. Unique Lloyd\'s register                                                                                                                         | Values are restricted to between 0 and 9999999      |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 087   | WMO marine observing platform extended identifier                                                                                                            | Set to missing, if ship\'s call sign is reported    |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Cruise/ship line information*                                                                                                                               |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 036   | Agency in charge of operating the observing platform                                                                                                         |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 115   | Identifier of the cruise or mission under which the data were collected                                                                                      | Set to missing, if no cruise identifier is reported |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 080   | Ship line number according to SOOP                                                                                                                           |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 05 036   | Ship transect number according to SOOP                                                                                                                       |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 01 011   | Year, month, day                                                                                                                                             |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 01 012   | Hour, minute                                                                                                                                                 |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 01 021   | Latitude/longitude (high accuracy)                                                                                                                           |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Profile information*                                                                                                                                        |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 079   | Unique identifier for the profile                                                                                                                            |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 01 023   | Observation sequence number                                                                                                                                  | Cast/station number along the line/transect         |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 22 063   | Total water depth                                                                                                                                            |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Surface pressure*                                                                                                                                           |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                                                                          |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 02 001   | Pressure and 3-hour pressure change                                                                                                                          |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Waves*                                                                                                                                                      |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                                                                          |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 02 021   | Waves                                                                                                                                                        |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Temperature and humidity data*                                                                                                                              |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                                                                          |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 02 052   | Ship temperature and humidity data                                                                                                                           |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Wind data*                                                                                                                                                  |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                                                                                                          |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 02 059   | Ship wind data                                                                                                                                               |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          |            | *Surface temperature, salinity and current*                                                                                                                  |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 22 067   | Instrument type for water temperature/salinity profile measurement                                                                                           |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | B 02 171   | Instrument serial number for water temperature profile measurement                                                                                           |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 02 090   | Sea/water temperature high precision                                                                                                                         | Surface temperature                                 |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 06 033   | Surface salinity                                                                                                                                             |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
|          | D 06 034   | Surface current                                                                                                                                              |                                                     |
+----------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+

*(continued)*

*\
(Category 15 -- continued)*

+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
| SEQUENCE               | TABLE      | ELEMENT NAME                                                                                         | ELEMENT DESCRIPTION                                                                                     |
|                        |            |                                                                                                      |                                                                                                         |
|                        | REFERENCES |                                                                                                      |                                                                                                         |
+========================+============+======================================================================================================+=========================================================================================================+
|                        | F X Y      |                                                                                                      |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
| D 15 007 (*continued*) | B 02 171   | Instrument serial number for water temperature profile measurement                                   | Set to missing (cancel)                                                                                 |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 22 067   | Instrument type for water temperature/salinity profile measurement                                   | Set to missing (cancel)                                                                                 |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            | *Temperature and salinity profile data*                                                              |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 038   | Method of water temperature and/or salinity measurement                                              |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 22 067   | Instrument type for water temperature/salinity profile measurement                                   |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 22 068   | Water temperature profile recorder types                                                             |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 171   | Instrument serial number for water temperature profile measurement                                   |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 033   | Method of salinity/depth measurement                                                                 |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 032   | Indicator for digitization                                                                           |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 22 056   | Direction of profile                                                                                 |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 03 011   | Method of depth calculation                                                                          |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | D 06 035   | Temperature and salinity profile                                                                     |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            | *Current profile data*                                                                               |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | R 07 000   | Delayed replication of 7 descriptors                                                                 |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 032   | Indicator for digitization                                                                           |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 03 010   | Method of sea/water current measurement                                                              |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 031   | Duration and time of current measurement                                                             |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 040   | Method of removing velocity and motion of platform from current                                      |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 22 056   | Direction of profile                                                                                 |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 03 011   | Method of depth calculation                                                                          |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | D 06 036   | Current profile                                                                                      |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            | *Dissolved oxygen profile data*                                                                      |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | R 04 000   | Delayed replication of 4 descriptors                                                                 |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 02 032   | Indicator for digitization                                                                           |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 03 012   | Instrument type/sensor for dissolved oxygen measurement                                              |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | B 03 011   | Method of depth calculation                                                                          |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | D 06 037   | Dissolved oxygen profile data                                                                        |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            |                                                                                                      |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            | (Sequence for the representation of data from moored buoys)                                          |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            | *Buoy identification and location*                                                                   |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
| D 15 008               | D 01 126   | Sequence for representation of moored buoy identification                                            |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        |            | *Standard meteorological data*                                                                       |                                                                                                         |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
|                        | D 06 038   | Sequence for representation of standard surface marine meteorological observations from moored buoys | For buoys equipped with more than 1 anemometer the height of sensor should relate to the one being used |
+------------------------+------------+------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+

*(continued)*

*\
(Category 15 -- continued)*

+---------------+------------+----------------------------------------------------------------------+---------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                         | ELEMENT DESCRIPTION |
|               |            |                                                                      |                     |
|               | REFERENCES |                                                                      |                     |
+===============+============+======================================================================+=====================+
|               | F X Y      |                                                                      |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
| D 15 008      |            | *Optional ancillary meteorological data*                             |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
| (*continued*) | R 01 000   | Delayed replication of 1 descriptor                                  |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 02 091   | Sequence for representation of ancillary meteorological observations |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               |            | *Optional radiation measurements*                                    |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                  |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 02 082   | Radiation data                                                       |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               |            | *Optional basic wave measurements*                                   |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                  |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 06 039   | Sequence for representation of basic wave measurements               |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               |            | *Optional spectral wave measurements*                                |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                  |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 06 040   | Sequence for representation of detailed spectral wave measurements   |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               |            | *Optional temperature profile measurements*                          |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                 |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | B 02 005   | Precision of temperature observation                                 |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 06 041   | Depth and temperature profile (high accuracy/\                       |                     |
|               |            | precision)                                                           |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               |            | *Optional temperature and salinity profile\                          |                     |
|               |            | measurements*                                                        |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                 |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | B 02 005   | Precision of temperature observation                                 |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 06 004   | Depth, temperature, salinity                                         |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               |            | *Optional subsurface current measurements*                           |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                                  |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+
|               | D 06 005   | Subsurface current measurements                                      |                     |
+---------------+------------+----------------------------------------------------------------------+---------------------+

**Category 16 -- *Synoptic feature sequences***

+----------+------------+---------------------------------------+-------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                          | ELEMENT DESCRIPTION           |
|          |            |                                       |                               |
|          | REFERENCES |                                       |                               |
+==========+============+=======================================+===============================+
|          | F X Y      |                                       |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          |            | (Jet stream)                          |                               |
+----------+------------+---------------------------------------+-------------------------------+
| D 16 003 | R 09 000   | Delayed replication of 9 descriptors  |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 011   | Meteorological feature                | Jet stream value              |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Value for line                |
+----------+------------+---------------------------------------+-------------------------------+
|          | R 04 000   | Delayed replication of 4 descriptors  |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 05 002   | Latitude (coarse accuracy)            |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 06 002   | Longitude (coarse accuracy)           |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 10 002   | Height                                | Flight level                  |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 11 002   | Wind speed                            |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Cancel                        |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 011   | Meteorological feature                | Cancel \| End of object       |
+----------+------------+---------------------------------------+-------------------------------+
|          |            |                                       |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          |            | (Turbulence)                          |                               |
+----------+------------+---------------------------------------+-------------------------------+
| D 16 004 | R 10 000   | Delayed replication of 10 descriptors |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 011   | Meteorological feature                | Value for turbulence          |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Value for area                |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 07 002   | Height or altitude                    | Flight level (base of layer)  |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 07 002   | Height or altitude                    | Flight level (top of layer)   |
+----------+------------+---------------------------------------+-------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors  |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 05 002   | Latitude (coarse accuracy)            |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 06 002   | Longitude (coarse accuracy)           |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 11 031   | Degree of turbulence (see Note 1)     |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Cancel                        |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 011   | Meteorological feature                | Cancel \| End of object       |
+----------+------------+---------------------------------------+-------------------------------+
|          |            |                                       |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          |            | (Storm)                               |                               |
+----------+------------+---------------------------------------+-------------------------------+
| D 16 005 | R 08 000   | Delayed replication of 8 descriptors  |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 005   | Meteorological attribute significance | Storm centre                  |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Value for point               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 05 002   | Latitude (coarse accuracy)            |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 06 002   | Longitude (coarse accuracy)           |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 01 026   | WMO storm name                        | Use "UNKNOWN" for a sandstorm |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 19 001   | Type of synoptic feature              | Value for type of storm       |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Cancel                        |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 005   | Meteorological attribute significance | Cancel \| End of object       |
+----------+------------+---------------------------------------+-------------------------------+
|          |            |                                       |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          |            | (Cloud)                               |                               |
+----------+------------+---------------------------------------+-------------------------------+
| D 16 006 | R 11 000   | Delayed replication of 11 descriptors |                               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 011   | Meteorological feature                | Value for cloud               |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 08 007   | Dimensional significance              | Value for area                |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 07 002   | Height or altitude                    | Flight level (base of layer)  |
+----------+------------+---------------------------------------+-------------------------------+
|          | B 07 002   | Height or altitude                    | Flight level (top of layer)   |
+----------+------------+---------------------------------------+-------------------------------+

*(continued)*

*\
(Category 16 -- continued)*

+---------------+------------+---------------------------------------+------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                          | ELEMENT DESCRIPTION          |
|               |            |                                       |                              |
|               | REFERENCES |                                       |                              |
+===============+============+=======================================+==============================+
|               | F X Y      |                                       |                              |
+---------------+------------+---------------------------------------+------------------------------+
| D 16 006      | R 02 000   | Delayed replication of 2 descriptors  |                              |
+---------------+------------+---------------------------------------+------------------------------+
| (*continued*) | B 05 002   | Latitude (coarse accuracy)            |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 06 002   | Longitude (coarse accuracy)           |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 20 011   | Cloud amount (see Note 2)             |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 20 012   | Cloud type                            |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Cancel                       |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 011   | Meteorological feature                | Cancel \| End of object      |
+---------------+------------+---------------------------------------+------------------------------+
|               |            |                                       |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               |            | (Front)                               |                              |
+---------------+------------+---------------------------------------+------------------------------+
| D 16 007      | R 09 000   | Delayed replication of 9 descriptors  |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 011   | Meteorological feature (see Note 3)   | Value for type of front      |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Value for line               |
+---------------+------------+---------------------------------------+------------------------------+
|               | R 04 000   | Delayed replication of 4 descriptors  |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 05 002   | Latitude (coarse accuracy)            |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 06 002   | Longitude (coarse accuracy)           |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 19 005   | Direction of motion of feature        |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 19 006   | Speed of motion of feature            |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Cancel                       |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 011   | Meteorological feature                | Cancel \| End of object      |
+---------------+------------+---------------------------------------+------------------------------+
|               |            |                                       |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               |            | (Tropopause)                          |                              |
+---------------+------------+---------------------------------------+------------------------------+
| D 16 008      | R 10 000   | Delayed replication of 10 descriptors |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 001   | Vertical sounding significance        | Bit 3 set for tropopause     |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Value for point              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 023   | First-order statistics (see Note 4)   | Type of tropopause value     |
+---------------+------------+---------------------------------------+------------------------------+
|               | R 03 000   | Delayed replication of 3 descriptors  |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 05 002   | Latitude (coarse accuracy)            |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 06 002   | Longitude (coarse accuracy)           |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 10 002   | Height                                |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 023   | First-order statistics                | Cancel                       |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Cancel                       |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 001   | Vertical sounding significance        | Cancel \| End of object      |
+---------------+------------+---------------------------------------+------------------------------+
|               |            |                                       |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               |            | (Airframe icing area)                 |                              |
+---------------+------------+---------------------------------------+------------------------------+
| D 16 009      | R 10 000   | Delayed replication of 10 descriptors |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 011   | Meteorological feature                | Value for airframe icing     |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Value for area               |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 07 002   | Height or altitude                    | Flight level (base of layer) |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 07 002   | Height or altitude                    | Flight level (top of layer)  |
+---------------+------------+---------------------------------------+------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors  |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 05 002   | Latitude (coarse accuracy)            |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 06 002   | Longitude (coarse accuracy)           |                              |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 20 041   | Airframe icing                        | Type of airframe icing       |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 007   | Dimensional significance              | Cancel                       |
+---------------+------------+---------------------------------------+------------------------------+
|               | B 08 011   | Meteorological feature                | Cancel \| End of object      |
+---------------+------------+---------------------------------------+------------------------------+

*(continued)*

*\
(Category 16 -- continued)*

+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                               | ELEMENT DESCRIPTION                                      |
|          |            |                                                            |                                                          |
|          | REFERENCES |                                                            |                                                          |
+==========+============+============================================================+==========================================================+
|          | F X Y      |                                                            |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          |            | (Name of feature)                                          |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
| D 16 010 | R 07 000   | Delayed replication of 7 descriptors                       |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 011   | Meteorological feature                                     |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 007   | Dimensional significance                                   | Value for point                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 01 022   | Name of feature                                            |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 05 002   | Latitude (coarse accuracy)                                 |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 06 002   | Longitude (coarse accuracy)                                |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 007   | Dimensional significance                                   | Cancel                                                   |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 011   | Meteorological feature                                     | Cancel \| End of object                                  |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          |            |                                                            |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          |            | (Volcano erupting)                                         |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
| D 16 011 | R 16 000   | Delayed replication of 16 descriptors                      |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 011   | Meteorological feature                                     | Value for special clouds                                 |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 01 022   | Name of feature                                            | Volcano name                                             |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 007   | Dimensional significance                                   | Value for point                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | R 02 000   | Delayed replication of 2 descriptors                       |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 05 002   | Latitude (coarse accuracy)                                 |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 06 002   | Longitude (coarse accuracy)                                |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 021   | Time significance                                          | Eruption starting time                                   |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 04 001   | Year                                                       |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 04 002   | Month                                                      |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 04 003   | Day                                                        |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 04 004   | Hour                                                       |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 04 005   | Minute                                                     |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 20 090   | Special clouds                                             | Clouds from volcanic eruptions                           |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 021   | Time significance                                          | Cancel                                                   |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 007   | Dimensional significance                                   | Cancel                                                   |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 011   | Meteorological feature                                     | Cancel \| End of object                                  |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          |            |                                                            |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          |            | (Forecast data)                                            |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
| D 16 022 | B 01 032   | Generating application                                     | NWP model name, etc. code table defined by originating/\ |
|          |            |                                                            | generating centre                                        |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 02 041   | Method for estimating reports related to synoptic features |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 19 001   | Type of synoptic feature                                   |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 19 010   | Method for tracking the centre of synoptic feature         |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | R 18 000   | Delayed replication of 18 descriptors                      |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 021   | Time significance                                          | Forecast                                                 |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 04 014   | Time increment                                             | Hours                                                    |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | B 08 005   | Meteorological attribute significance                      | Surface synoptic feature                                 |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+
|          | D 01 023   | Latitude/longitude (coarse accuracy)                       |                                                          |
+----------+------------+------------------------------------------------------------+----------------------------------------------------------+

*(continued)*

*\
(Category 16 -- continued)*

+---------------+------------+--------------------------------------------------------------+----------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                 | ELEMENT DESCRIPTION                    |
|               |            |                                                              |                                        |
|               | REFERENCES |                                                              |                                        |
+===============+============+==============================================================+========================================+
|               | F X Y      |                                                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
| D 16 022      | B 19 005   | Direction of motion of feature                               |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
| (*continued*) | B 19 006   | Speed of motion of feature                                   |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 10 004   | Pressure                                                     |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 11 041   | Maximum wind gust speed                                      | For example, used in the United States |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 021   | Time significance                                            | Forecast time averaged                 |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 04 075   | Short time period or displacement                            | Minutes                                |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 11 040   | Maximum wind speed (mean wind)                               |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 19 008   | Vertical extent of circulation                               |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | R 05 004   | Replicate 5 descriptors 4 times                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 05 021   | Bearing or azimuth                                           | Starting                               |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 05 021   | Bearing or azimuth                                           | Ending                                 |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | R 02 002   | Replicate 2 descriptors 2 times                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 19 003   | Wind speed threshold                                         |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 19 004   | Effective radius with respect to wind speeds above threshold |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               |            |                                                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               |            | (SIGMET, Outlook)                                            |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
| D 16 033      | B 08 021   | Time significance                                            | = 4 Forecast                           |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 01 011   | Year, month, day                                             |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 01 012   | Hour, minute                                                 |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                          |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 01 027   | Description of a feature in 3-D or 2-D                       |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 021   | Time significance                                            | Set to missing (cancel)                |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               |            |                                                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               |            | (Volcanic Ash SIGMET)                                        |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
| D 16 034      | B 08 079   | Product status                                               | = 0 Normal issue,                      |
|               |            |                                                              |                                        |
|               |            |                                                              | = 1 Correction                         |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 16 030   | SIGMET header                                                |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 011   | Meteorological feature                                       | = 17 Volcano                           |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 01 022   | Name of feature                                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 007   | Dimensional significance                                     | = 0 Point                              |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 01 023   | Latitude/longitude (coarse accuracy)                         |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 007   | Dimensional significance                                     | Set to missing (cancel)                |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 20 090   | Special clouds                                               | = 5 Clouds from volcanic eruptions     |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 16 031   | SIGMET, Observed or forecast location and motion             |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                          |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 16 032   | SIGMET, Forecast position                                    |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | R 01 000   | Delayed replication of 1 descriptor                          |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | D 16 033   | SIGMET, Outlook                                              |                                        |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 011   | Meteorological feature                                       | Set to missing (cancel)                |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+
|               | B 08 079   | Product status                                               | Set to missing (cancel)                |
+---------------+------------+--------------------------------------------------------------+----------------------------------------+

*(continued)*

*\
(Category 16 -- continued)*

+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                                                      | ELEMENT DESCRIPTION     |
|          |            |                                                                                   |                         |
|          | REFERENCES |                                                                                   |                         |
+==========+============+===================================================================================+=========================+
|          | F X Y      |                                                                                   |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          |            | (Tropical cyclone SIGMET)                                                         |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
| D 16 036 | B 08 079   | Product status                                                                    | = 0 Normal issue,\      |
|          |            |                                                                                   | = 1 Correction          |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | D 16 030   | SIGMET header                                                                     |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 08 011   | Meteorological feature                                                            | = 22 Tropical cyclone   |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 01 027   | WMO long storm name                                                               |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | D 16 031   | SIGMET, Observed or forecast location and motion                                  |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                               |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | D 16 032   | SIGMET, Forecast position                                                         |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | R 01 000   | Delayed replication of 1 descriptor                                               |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | D 16 033   | SIGMET, Outlook                                                                   |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 08 011   | Meteorological feature                                                            | Set to missing (cancel) |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 08 079   | Product status                                                                    | Set to missing (cancel) |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          |            |                                                                                   |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          |            | (SAREP template -- Part A: Information on tropical cyclone)                       |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
| D 16 052 | D 01 005   | Originating centre/sub-centre                                                     |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | D 01 011   | Year, month, day                                                                  |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | D 01 012   | Hour, minute                                                                      |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 01 007   | Satellite identifier                                                              |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 25 150   | Method of tropical cyclone intensity analysis using satellite data                |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | R 22 000   | Delayed replication of 22 descriptors                                             |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 01 027   | WMO long storm name                                                               |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 150   | Typhoon International Common Number (Typhoon Committee)                           |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 106   | Identification number of tropical cyclone                                         |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 08 005   | Meteorological attribute significance                                             | = 1                     |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 05 002   | Latitude (coarse accuracy)                                                        |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 06 002   | Longitude (coarse accuracy)                                                       |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 08 005   | Meteorological attribute significance                                             | Cancel                  |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 107   | Time interval over which the movement of the tropical cyclone has been calculated |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 005   | Direction of motion of feature                                                    |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 006   | Speed of motion of feature                                                        |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 108   | Accuracy of geographical position of the tropical cyclone                         |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 109   | Mean diameter of the overcast cloud of the tropical cyclone                       |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 110   | Apparent 24-hour change in intensity of the tropical cyclone                      |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 111   | Current Intensity (CI) number of the tropical cyclone                             |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 112   | Data Tropical (DT) number of the tropical cyclone                                 |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 113   | Cloud pattern type of the DT-number                                               |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+
|          | B 19 114   | Model Expected Tropical (MET) number of the tropical cyclone                      |                         |
+----------+------------+-----------------------------------------------------------------------------------+-------------------------+

*(continued)*

*\
(Category 16 -- continued)*

+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                                                                                      | ELEMENT DESCRIPTION        |
|               |            |                                                                                                                                   |                            |
|               | REFERENCES |                                                                                                                                   |                            |
+===============+============+===================================================================================================================================+============================+
|               | F X Y      |                                                                                                                                   |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
| D 16 052\     | B 19 115   | Trend of the past 24-hour change (+: Developed, --: Weakened)                                                                     |                            |
| (*continued*) |            |                                                                                                                                   |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 19 116   | Pattern Tropical (PT) number of the tropical cyclone                                                                              |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 19 117   | Cloud picture type of the PT-number                                                                                               |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 19 118   | Final Tropical (T) number of the tropical cyclone                                                                                 |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 19 119   | Type of the final T-number                                                                                                        |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               |            |                                                                                                                                   |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               |            | (Definition of squall line (by centre and several points: North points and South points) and forecasted trajectory and evolution) |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
| D 16 061      | D 01 011   | Year, month, day                                                                                                                  |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | D 01 012   | Hour, minute                                                                                                                      |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               |            | *Position of squall line centre*                                                                                                  |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 05 002   | Latitude (coarse accuracy)                                                                                                        |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 06 002   | Longitude (coarse accuracy)                                                                                                       |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 19 005   | Direction of motion of feature                                                                                                    |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 19 006   | Speed of motion of feature                                                                                                        |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               |            | *Amplitude of feature from most external points to\                                                                               |                            |
|               |            | centre point -- North points*                                                                                                     |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                                                                              |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 05 002   | Latitude (coarse accuracy)                                                                                                        |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 06 002   | Longitude (coarse accuracy)                                                                                                       |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               |            | *Amplitude of feature from most external points to\                                                                               |                            |
|               |            | centre point -- South points*                                                                                                     |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                                                                                              |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 05 002   | Latitude (coarse accuracy)                                                                                                        |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 06 002   | Longitude (coarse accuracy)                                                                                                       |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               |            | *Amplitude of feature from most external points to\                                                                               |                            |
|               |            | centre point -- Evolution*                                                                                                        |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 04 074   | Short time period or displacement                                                                                                 | Period of validity         |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 20 048   | Evolution of feature                                                                                                              |                            |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 11 041   | Maximum wind gust speed                                                                                                           | Maximum burst expected     |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+
|               | B 13 055   | Intensity of precipitation                                                                                                        | Intensity of rain expected |
+---------------+------------+-----------------------------------------------------------------------------------------------------------------------------------+----------------------------+

Notes:

\(1) For MOD OCNL SEV code as 12 (extreme in clear air) or 13 (extreme in cloud).

\(2) Code table values:

FRQ = code figure 8 (8 oktas)

OCNL EMBD = code figure 6 (6 oktas)

ISOL = code figure 2 (2 oktas) when the cloud = Cb.

\(3) Front direction (towards which the front is moving) must always be given as it is needed for plotting purposes. A front direction with a front speed of zero would indicate a slow front. A value in the code table exists to represent a quasi-stationary front.

*(continued)*

*\
(Category 16 -- continued)*

\(4) The statistic is to determine whether the following tropopause levels are minimum, maximum or spot values (missing code value).

\(5) Decibel (dB) is a logarithmic measure of the relative power, or of the relative values of two flux densities, especially of sound intensities and radio and radar power densities. In radar meteorology, the logarithmic scale (dBZ) is used for measuring radar reflectivity factor (obtained from the American Meteorological Society *Glossary of Meteorology*).

**Category 22 -- *Chemical and aerosol sequences***

+----------+------------+---------------------------------------------------+---------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                      | ELEMENT DESCRIPTION |
|          |            |                                                   |                     |
|          | REFERENCES |                                                   |                     |
+==========+============+===================================================+=====================+
|          | F X Y      |                                                   |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          |            | (METOP GOME--2)                                   |                     |
+----------+------------+---------------------------------------------------+---------------------+
| D 22 028 | B 01 007   | Satellite identifier                              |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 02 019   | Satellite instruments                             |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 04 001   | Year                                              |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 04 002   | Month                                             |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 04 003   | Day                                               |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 04 004   | Hour                                              |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 04 005   | Minute                                            |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 04 006   | Second                                            |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 05 001   | Latitude (high accuracy)                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 06 001   | Longitude (high accuracy)                         |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 27 001   | Latitude (high accuracy)                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 28 001   | Longitude (high accuracy)                         |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 27 001   | Latitude (high accuracy)                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 28 001   | Longitude (high accuracy)                         |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 27 001   | Latitude (high accuracy)                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 28 001   | Longitude (high accuracy)                         |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 27 001   | Latitude (high accuracy)                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 28 001   | Longitude (high accuracy)                         |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 10 001   | Height of land surface                            |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 14 019   | Surface albedo                                    |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 07 025   | Solar zenith angle                                |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 10 080   | Viewing zenith angle                              |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 05 023   | Sun to satellite azimuth difference               |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 20 010   | Cloud cover (total)                               |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 08 003   | Vertical significance (satellite observations)    |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 07 004   | Pressure                                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 14 026   | Albedo at the top of clouds                       |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 20 014   | Height of top of cloud                            |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 13 093   | Cloud optical thickness                           |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | R 05 000   | Delayed replication of 5 descriptors              |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 07 004   | Pressure                                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 07 004   | Pressure                                          |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 08 043   | Atmospheric chemical or physical constituent type |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 08 044   | CAS registry number                               |                     |
+----------+------------+---------------------------------------------------+---------------------+
|          | B 15 021   | Integrated mass density                           |                     |
+----------+------------+---------------------------------------------------+---------------------+

**Category 35 -- *Monitoring information***

+----------+------------+----------------------------------------------------------+----------------------------------------------+
| SEQUENCE | TABLE      | ELEMENT NAME                                             | ELEMENT DESCRIPTION                          |
|          |            |                                                          |                                              |
|          | REFERENCES |                                                          |                                              |
+==========+============+==========================================================+==============================================+
|          | F X Y      |                                                          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            | (Specify monitoring station)                             |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
| D 35 001 | B 08 035   | Type of monitoring exercise                              |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 35 001   | Time frame for monitoring                                |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 08 036   | Type of centre or station performing monitoring          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | D 01 001   | WMO block and station numbers                            |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            |                                                          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            | (Specify monitoring centre)                              |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
| D 35 002 | B 08 035   | Type of monitoring exercise                              |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 35 001   | Time frame for monitoring                                |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 08 036   | Type of centre or station performing monitoring          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 01 033   | Identification of originating/generating centre          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            |                                                          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            | (Specify monitoring period)                              |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
| D 35 003 | B 08 021   | Time significance                                        | \(23) Monitoring period                      |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 001   | Year                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 002   | Month                                                    |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 003   | Day                                                      |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 004   | Hour                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 073   | Short time period or displacement                        |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            |                                                          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            | (Specify report type and single station being monitored) |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
| D 35 004 | B 08 021   | Time significance                                        | \(24) Agreed time limit for report reception |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 004   | Hour                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 08 021   | Time significance                                        | \(25) Nominal reporting time                 |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 004   | Hour                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 35 000   | FM and regional code number                              |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | D 01 001   | WMO block and station numbers                            |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 35 011   | Number of reports actually received                      |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            |                                                          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            | (Specify report type and WMO block being monitored)      |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
| D 35 005 | B 08 021   | Time significance                                        | \(24) Agreed time limit for report reception |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 004   | Hour                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 08 021   | Time significance                                        | \(25) Nominal reporting time                 |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 004   | Hour                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 35 000   | FM and regional code number                              |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 01 001   | WMO block number                                         |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 35 011   | Number of reports actually received                      |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            |                                                          |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          |            | (Specify report type and WMO Region being monitored)     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
| D 35 006 | B 08 021   | Time significance                                        | \(24) Agreed time limit for report reception |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 04 004   | Hour                                                     |                                              |
+----------+------------+----------------------------------------------------------+----------------------------------------------+
|          | B 08 021   | Time significance                                        | \(25) Nominal reporting time                 |
+----------+------------+----------------------------------------------------------+----------------------------------------------+

*(continued)*

*\
(Category 35 -- continued)*

+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
| SEQUENCE      | TABLE      | ELEMENT NAME                                                       | ELEMENT DESCRIPTION                          |
|               |            |                                                                    |                                              |
|               | REFERENCES |                                                                    |                                              |
+===============+============+====================================================================+==============================================+
|               | F X Y      |                                                                    |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
| D 35 006      | B 04 004   | Hour                                                               |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
| (*continued*) | B 35 000   | FM and regional code number                                        |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 01 003   | WMO Region number/geographical area                                |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 35 011   | Number of reports actually received                                |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               |            |                                                                    |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               |            | (Report type and multiple stations from one block being monitored) |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
| D 35 007      | B 08 021   | Time significance                                                  | \(24) Agreed time limit for report reception |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 04 004   | Hour                                                               |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 08 021   | Time significance                                                  | \(25) Nominal reporting time                 |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 04 004   | Hour                                                               |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 35 000   | FM and regional code number                                        |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 01 001   | WMO block number                                                   |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | R 02 000   | Delayed replication of 2 descriptors                               | Count of stations                            |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 01 002   | WMO station number                                                 |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | B 35 011   | Number of reports actually received                                |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               |            |                                                                    |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               |            | (Monitoring a report type from multiple stations)                  |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
| D 35 010      | D 35 002   | Specify monitoring centre                                          |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | D 35 003   | Specify monitoring period                                          |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+
|               | D 35 007   | Report type and multiple stations from one block being monitored   |                                              |
+---------------+------------+--------------------------------------------------------------------+----------------------------------------------+