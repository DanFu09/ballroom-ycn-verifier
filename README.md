# ballroom-ycn-verifier
A python script and scraper for o2cm that checks the entries of a competition against a compiled database of previous o2cm placement histories

The included pickle file right now is up to date with results as of Apr 16, 2016 from the Charlotte Dancesport Challenge starting from after Aug 03, 2007 at the Seattle Star Ball.
I don't have results from that competition or before because the post request is slightly different (event2.asp instead of event3.asp) and didn't think anyone in results before then would be registering for events they had placed out of.

##### comp_point_check.py
This file is used to check the results from a single style, level, and competitor

##### comp_res.p
The pickle file containing the compressed results of everyone with valid ycn placements that I could find on o2cm results after Seattle Star Ball 07

##### comp_res_references.p
Contains some shared helper data structures

##### comp_res_scraper.py
Scrapes results from all competitions listed on o2cm results page and outputs the comp_res.p pickle file

##### entries_scraper.py
Scrapes entries from user-specified event and cross checks it with previous ycn points earned for each person on the entries page

##### helpers.py
Helper functions shared between the entries and the results scraper


###### exclusion categories - if any of these strings are in the event name, it will not be included in the results
((Social)|(Teddy)|(Juvenile)|(Junior)|(Jr.)|(Youth)|(Yth.)|(Teen)|(Young)|(Under)|(under)|([0-9]-)|([0-9]+)|(Senior))

((T/S)|(Tea/)|(Stu/)|(Nine Dance)|(Ten Dance)|(Pro)|(Student)|(Mixed)|(WDSF)|(Scholar)|(Rookie)|(Solo)|(Lead)|(Follow)|(Club)|(Formation)|(Showdance)|(Team)|(SS-))

((Polka)|(West Coast)|(Salsa)|(Hustle)|(Salsa)|(Argentine)|(Merengue)|(Lindy)|(Blues)|(Bachata)|(2-Step)|(Country))

###### known issues
If you share a name with another competitor on o2cm, o2cm will not differentiate your results history and your combined results will be reflected in the scraped output file
