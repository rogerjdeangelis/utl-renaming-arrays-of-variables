# utl-renaming-arrays-of-variables
Renaming arrays of variables
Renaming arrays of variables

inspird by
https://tinyurl.com/ce6u6xzw
https://communities.sas.com/t5/SAS-Programming/Setting-weekly-variables-in-relation-to-the-birth-of-a-child/m-p/725760

 Problem
    y_1501 to week_0
    y_1502 to week-1
    ...        ...
*_                   _
(_)_ __  _ __  _   _| |_
| | '_ \| '_ \| | | | __|
| | | | | |_) | |_| | |_
|_|_| |_| .__/ \__,_|\__|
        |_|
;
data have;
 input pnr $ week y_1501 y_1502 y_1503 y_1504;
cards4;
X 1 1 2 3 4 5 6
Y 2 1 2 3 4 5 6
;;;;
run;quit;
*
 _ __  _ __ ___   ___ ___  ___ ___
| '_ \| '__/ _ \ / __/ _ \/ __/ __|
| |_) | | | (_) | (_|  __/\__ \__ \
| .__/|_|  \___/ \___\___||___/___/
|_|
;

data want;
  set have(rename=(  y_1501- y_1504  = week_0 - week_3));
run;quit;

*            _               _
  ___  _   _| |_ _ __  _   _| |_
 / _ \| | | | __| '_ \| | | | __|
| (_) | |_| | |_| |_) | |_| | |_
 \___/ \__,_|\__| .__/ \__,_|\__|
                |_|
;

Up to 40 obs from WANT total obs=2

Obs    PNR    WEEK    WEEK_0    WEEK_1    WEEK_2    WEEK_3

 1      X       1        1         2         3         4
 2      Y       2        1         2         3         4
