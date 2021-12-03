PEW RESEARCH CENTER
2020 Census Survey
Dates: January 3-13, 2020
Mode: Web
Language: English and Spanish
N=3,535 U.S. adults

***************************************************************************************************************************

Weights:

WEIGHT is the weight for the sample. Data for all Pew Research Center reports are analyzed using this weight.

***************************************************************************************************************************

This dataset contains two different measures of race and ethnicity. In the report titled "Most Adults Aware of 2020 Census and 
Ready to Respond, but Don’t Know Key Details," racial/ethnic categories are based on the variable PPETHM, which is based on the 
race/ethnicity the respondent provided to Ipsos at the time of their panel recruitment. In the report titled "Black and Hispanic 
Americans See Their Origins as Central to Who They Are, Less So for White Adults," racial/ethnic categories are based on the 
variable CENSUSRACETHN, which is a composite variable based on respondents' answers to the questions CENHISPAN2020 and CENRACE2020 
asked in this survey.

***************************************************************************************************************************

Ipsos collects demographic information on its panelists periodically; see Methodology for a list of variables that were collected 
by Ipsos and were not asked on this survey.

Variables detailing the order of randomized questions, the interview start and finish times, and the respondent's device type 
are available upon request.

***************************************************************************************************************************

Releases from this survey:

February 20, 2020 "Most Adults Aware of 2020 Census and Ready to Respond, but Don’t Know Key Details"
https://www.pewsocialtrends.org/2020/02/20/most-adults-aware-of-2020-census-and-ready-to-respond-but-dont-know-key-details/

May 14, 2021 "Black and Hispanic Americans See Their Origins as Central to Who They Are, Less So for White Adults"
https://www.pewresearch.org/social-trends/2021/05/14/black-and-hispanic-americans-see-their-origins-as-central-to-who-they-are-less-so-for-white-adults/

***************************************************************************************************************************

Syntax:

count racnum=CENRACE2020_1(1), CENRACE2020_2(1), CENRACE2020_3(1), CENRACE2020_4(1), CENRACE2020_5(1), CENRACE2020_6(1), CENRACE2020_7(1), CENRACE2020_8(1), 
CENRACE2020_9(1), CENRACE2020_10(1), CENRACE2020_11(1), CENRACE2020_12(1), CENRACE2020_13(1), CENRACE2020_14(1), CENRACE2020_15(1).
variable labels racnum 'Number of races selected'.

compute censusracethn=99.
if CENHISPAN2020_1=1 & CENRACE2020_1=1 & racnum=1 censusracethn=1.
if CENHISPAN2020_1=1 & CENRACE2020_2=1 & racnum=1 censusracethn=2.
if CENHISPAN2020_2=1 | CENHISPAN2020_3=1 | CENHISPAN2020_4=1 | CENHISPAN2020_5=1 censusracethn=3.
if CENHISPAN2020_1=1 & (CENRACE2020_3=1 | CENRACE2020_4=1 | CENRACE2020_5=1 | CENRACE2020_6=1 | CENRACE2020_7=1 | CENRACE2020_8=1 | CENRACE2020_9=1 | 
CENRACE2020_10=1 | CENRACE2020_11=1 | CENRACE2020_12=1 | CENRACE2020_13=1 | CENRACE2020_14=1 | CENRACE2020_15=1 | racnum>1) censusracethn=4.
Variable labels censusracethn 'Race/ethnicity from 2020 census questions'.
Value labels censusracethn 1 'White non-Hispanic' 2 'Black non-Hispanic' 3 'Hispanic' 4 'Non-Hispanic Other/Multiracial' 99 'Refused'.

count knowledgecount=CENREQUIRED(1), CENREPS(1), CENIMMS(2), CENFUNDS(1), CENQS_a(1), CENQS_b(1), CENQS_c(2), CENQS_d(2).
variable labels knowledgecount 'Number of correct knowledge questions, out of 8'.

***************************************************************************************************************************