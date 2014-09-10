library
--------
*Stock prices and values;
data portfolio;
infile 'M:\ sas\stocks.txt';
input Symbol $ Price Number;
Value = Number*Price;
run;
title "Listing of Portfolio";
proc print data=portfolio noobs;
run;
* averages prices and sums;
title "Means and Sums of Portfolio Variables";
proc means data=portfolio n mean sum maxdec=0;
var Price Number;
run;
