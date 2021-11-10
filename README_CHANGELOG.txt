Use to get and write Message field to CSV file
input is Jobname [OPTION] in XrefCode
input include xrf file to get Description Segment and Element
input include XrefCode.txt file to get Option for Message
==============================================
1.Structured:
[Trans]_[Name][Ver]_[Seg][Elm(2)][Sub-Elm(2)]-[O/M]-[Qual]_[Option]_[Val1]_[Val2]
----------------------------------------------
[Trans]: Required
[Name][Ver]: Required
[Seg]: Required
[Elm(2)]: optional
[Sub-Elm(2)]: optional
[O/M]: optional, default:O 
[Qual]: optional, it not equal O or M, default get qualifier is Seg01
[Option]: Required
[Val1]: optional
[Val2]: optional
Ex:
856_FULLCOMPASS4030_BSN01_EQUAL_00
856_FULLCOMPASS4030_NAD0102-O-ST_DBCHECK
INVOIC_FULLCOMPASS4030_NAD0102-M_DBCHECK_BLANK
==============================================
2.Option
----------------------------------------------
2.1 EQUAL
Equal with Val1 and Val2
Ex:
856_FULLCOMPASS4030_BSN01-M_EQUAL_00
856_FULLCOMPASS4030_BSN01-M_EQUAL_00_01
856_FULLCOMPASS4030_BSN01-M_EQUAL_LIST_BSN01

=>In EQUAL: if Val1=LIST then Val2 = Lookup in XRefCode.txt use Val2 in Section
----------------------------------------------
2.2 LEN
Ex:
856_FULLCOMPASS4030_BSN01-M_LEN_1
856_FULLCOMPASS4030_BSN01-O_LEN_1_5
----------------------------------------------
2.3 MAX
Ex:
856_FULLCOMPASS4030_PO1_MAX_1
----------------------------------------------

2.4 REQUIRED
Ex:
856_FULLCOMPASS4030_PO1_REQUIRED
----------------------------------------------
2.5 DBCHECK
Ex:
856_FULLCOMPASS4030_NAD0102-O-ST_DBCHECK
INVOIC_FULLCOMPASS4030_NAD0102-M_DBCHECK_BLANK
----------------------------------------------
2.6 NOT
Expected with Val1 and Val2
Ex:
856_FULLCOMPASS4030_N101-M_NOT_ST_SF

=>In NOT: if Val1=LIST then Val2 = Lookup in XRefCode.txt use Val2 in Section
==============================================