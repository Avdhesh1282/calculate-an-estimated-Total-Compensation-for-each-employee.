import numpy as np
import pandas as pd

train_data = pd.read_csv("/content/train_set.csv")

train_data.head()

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	Community Health 	DPH 	Public Health 	250 	SEIU - Health Workers, Local 1021 	Med Therapy & Auxiliary 	Morgue Attendant 	6725.0 	12196.0 	0.0 	0.00 	Calendar 	16158.0
1 	2013 	4 	Community Health 	DPH 	Public Health 	39 	Stationary Engineers, Local 39 	Journeyman Trade 	Stationary Engineer 	25058.0 	74639.0 	2820.0 	12703.31 	Fiscal 	115784.0
2 	2015 	6 	General Administration & Finance 	ASR 	Assessor/Recorder 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Appraisal & Taxation 	Senior Real Property Appraiser 	46108.0 	100554.0 	0.0 	12424.50 	Calendar 	144708.0
3 	2016 	1 	Public Protection 	POL 	Police 	911 	Police Officers' Association 	Police Services 	Sergeant 3 	33369.0 	140164.0 	52754.0 	13043.87 	Fiscal 	242323.0
4 	2013 	2 	Public Works, Transportation & Commerce 	HHP 	PUC Hetch Hetchy 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Information Systems 	IS Engineer-Journey 	28684.0 	58813.0 	0.0 	7655.28 	Calendar 	82106.0

for cols in train_data:
  print(train_data[cols].value_counts())

2014    10581
2013    10049
2015     9619
2016     4614
Name: Year, dtype: int64
2    11023
4     7653
1     6616
5     3227
3     3225
6     3096
7       23
Name: OGC, dtype: int64
Public Works, Transportation & Commerce     11030
Community Health                             7640
Public Protection                            6625
Culture & Recreation                         3217
Human Welfare & Neighborhood Development     3216
General Administration & Finance             3112
General City Responsibilities                  23
Name: OG, dtype: int64
DPH    7641
MTA    5170
DSS    2870
POL    2831
REC    1950
AIR    1636
FIR    1416
DPW    1346
ADM     882
SHF     869
LIB     827
PUC     776
WTR     696
CWP     480
CRT     464
HHP     340
CAT     279
ECD     272
DBI     265
HRD     255
JUV     253
FAM     247
CON     246
DAT     246
TIS     236
CPC     224
PRT     214
REG     207
TTX     206
ASR     175
PDR     142
ADP     130
ENV     117
BOS     110
ECN     101
RET      95
MYR      95
CSS      88
WAR      80
HSS      76
AAM      67
CHF      62
RNT      32
ART      29
HRC      24
UNA      23
ETH      18
SCI      16
WOM      11
CFC      11
PAB       6
CSC       4
CII       4
LLB       3
Name: DC, dtype: int64
Public Health                             7644
Municipal Transportation Agency           5164
Human Services                            2873
Police                                    2834
Recreation and Park Commission            1949
Airport Commission                        1629
Fire Department                           1415
General Services Agency - Public Works    1342
General Services Agency - City Admin       880
Sheriff                                    869
Public Library                             827
PUC Public Utilities Commission            782
PUC Water Department                       706
PUC Wastewater Enterprise                  482
Superior Court                             464
PUC Hetch Hetchy                           337
City Attorney                              280
Department of Emergency Management         271
Department of Building Inspection          264
Human Resources                            258
Juvenile Probation                         252
Fine Arts Museum                           246
Controller                                 246
District Attorney                          245
General Services Agency - Technology       235
City Planning                              226
Port                                       218
Elections                                  207
Treasurer/Tax Collector                    203
Assessor/Recorder                          175
Public Defender                            143
Adult Probation                            130
Environment                                117
Board of Supervisors                       110
Economic and Workforce Development         101
Mayor                                       95
Retirement System                           94
Child Support Services                      89
War Memorial                                80
Health Service System                       76
Asian Art Museum                            67
Children, Youth & Their Families            59
Rent Arbitration Board                      31
Arts Commission                             29
Human Rights Commission                     24
General Fund Unallocated                    23
Ethics Commission                           18
Academy of Sciences                         16
Department of the Status of Women           11
Children and Families Commission            10
Board of Appeals                             6
Community Investment & Infrastructure        4
Civil Service Commission                     4
Law Library                                  3
Name: Dept, dtype: int64
790    9961
21     4278
791    2652
911    2354
253    2161
       ... 
428       1
364       1
699       1
140       1
171       1
Name: UC, Length: 272, dtype: int64
SEIU - Miscellaneous, Local 1021                      10009
Prof & Tech Engineers - Miscellaneous, Local 21        4318
SEIU - Staff and Per Diem Nurses, Local 1021           2669
Police Officers' Association                           2366
Transport Workers - Transit Operators, Local 250-A     2166
                                                      ...  
Court Unrepresented Managers                              3
Elected Officials                                         2
Municipal Executive Association - Police                  2
Laborers Int, Local 261                                   2
Carpet, Linoleum and Soft Tile Workers, Local 12          1
Name: Union, Length: 67, dtype: int64
Nursing                           3698
Street Transit                    2890
Police Services                   2365
Journeyman Trade                  2051
Public Service Aide               1885
Human Services                    1789
Clerical, Secretarial & Steno     1654
Fire Services                     1353
Housekeeping & Laundry            1098
Management                        1073
Professional Engineering          1022
Recreation                        1013
Protection & Apprehension          996
Budget, Admn & Stats Analysis      938
Correction & Detention             911
Information Systems                766
Legal & Court                      761
Med Therapy & Auxiliary            730
Payroll, Billing & Accounting      727
Library                            691
Lab, Pharmacy & Med Techs          586
SF Superior Court                  478
Personnel                          465
Sub-Professional Engineering       459
Semi-Skilled & General Labor       453
Agriculture & Horticulture         391
Supervisory-Labor & Trade          338
Airport Operation                  316
Skilled Labor                      284
Medical & Dental                   245
Community Development              242
Dietary & Food                     221
Appraisal & Taxation               186
Purchasing & Storekeeping          171
Construction Inspection            152
Public Health                      147
Probation & Parole                 145
Energy & Environment               142
Computer Operatns & Repro Svcs     135
Pub Relations & Spec Assts         135
Hospital Administration            135
Public Safety Inspection           107
Health & Sanitation Inspection      98
Park & Zoo                          95
Revenue                             79
Museum & Cultural Affairs           66
Construction Project Mgmt           65
Administrative-DPW/PUC              41
Administrative-Labor & Trades       16
Port Operation                      12
Emergency Services                  11
Property Administration             11
Administrative Secretarial          10
Administrative & Mgmt (Unrep)        6
SF Redevelopment Agency              3
Publi                                1
Name: JF, dtype: int64
Transit Operator                  2170
Special Nurse                     1282
Registered Nurse                  1090
Public Svc Aide-Public Works       760
Police Officer 3                   721
                                  ... 
Accountant I                         1
Treasurer                            1
Feasibility Analyst, Port            1
Industrial Injury Investigator       1
Supervising Purchaser                1
Name: Job, Length: 972, dtype: int64
21426.0    6
44295.0    6
28540.0    6
22910.0    6
23817.0    5
          ..
39361.0    1
11122.0    1
26764.0    1
32591.0    1
14336.0    1
Name: EI, Length: 25159, dtype: int64
0.0         399
112703.0    116
118898.0     65
56531.0      60
123471.0     52
           ... 
143272.0      1
87087.0       1
91036.0       1
64024.0       1
1578.0        1
Name: Salaries, Length: 25360, dtype: int64
0.0        19666
4.0           20
41.0          19
25.0          19
44.0          18
           ...  
6258.0         1
17649.0        1
4040.0         1
8400.0         1
5639.0         1
Name: Overtime, Length: 9632, dtype: int64
0.000000        1595
13054.940000    1350
12424.500000    1282
12918.240000    1126
12512.550000     890
                ... 
5649.057026        1
9340.220000        1
5128.430000        1
12294.850000       1
7534.080000        1
Name: H/D, Length: 17667, dtype: int64
Fiscal      17514
Calendar    17348
Name: YT, dtype: int64
7644.0      8
3295.0      8
1693.0      8
11158.0     7
1290.0      7
           ..
174425.0    1
92207.0     1
243950.0    1
64087.0     1
38896.0     1
Name: Total_Compensation, Length: 31711, dtype: int64

train_data.isnull().sum()

Year                   0
OGC                    0
OG                     0
DC                     0
Dept                   0
UC                     0
Union                 36
JF                    38
Job                    0
EI                     0
Salaries               0
Overtime               0
H/D                    0
YT                     0
Total_Compensation     0
dtype: int64

train_data.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 287836 entries, 0 to 287835
Data columns (total 15 columns):
 #   Column              Non-Null Count   Dtype  
---  ------              --------------   -----  
 0   Year                287836 non-null  int64  
 1   OGC                 287836 non-null  int64  
 2   OG                  287836 non-null  object 
 3   DC                  287836 non-null  object 
 4   Dept                287836 non-null  object 
 5   UC                  287836 non-null  int64  
 6   Union               287800 non-null  object 
 7   JF                  287798 non-null  object 
 8   Job                 287836 non-null  object 
 9   EI                  287836 non-null  int64  
 10  Salaries            287836 non-null  int64  
 11  Overtime            287836 non-null  int64  
 12  H/D                 287836 non-null  float64
 13  YT                  287836 non-null  object 
 14  Total_Compensation  287836 non-null  int64  
dtypes: float64(1), int64(7), object(7)
memory usage: 32.9+ MB

train_data.dropna(inplace=True)

train_data.isnull().sum()

Year                  0
OGC                   0
OG                    0
DC                    0
Dept                  0
UC                    0
Union                 0
JF                    0
Job                   0
EI                    0
Salaries              0
Overtime              0
H/D                   0
YT                    0
Total_Compensation    0
dtype: int64

train_data['Union'].unique()

array(['SEIU - Health Workers, Local 1021',
       'Stationary Engineers, Local 39',
       'Prof & Tech Engineers - Miscellaneous, Local 21',
       "Police Officers' Association", 'SEIU - Miscellaneous, Local 1021',
       'SEIU - Human Services, Local 1021',
       'Automotive Machinists, Local 1414',
       'Firefighters - Chiefs/Fire Boat Workers, Local 798',
       'Firefighters - Miscellaneous, Local 798',
       'Transportation Workers, Local 200',
       'Transport Workers - Transit Operators, Local 250-A',
       'Laborers, Local 261',
       'Prof & Tech Engineers - Court Attorneys, Local 21',
       "Deputy Sheriffs' Association",
       'SEIU - Staff and Per Diem Nurses, Local 1021',
       'Transport Workers - Auto Svc Workers, Local 250-A',
       'Municipal Executive Association - Miscellaneous',
       'Teamsters - Supervising Nurses, Local 856',
       'Electrical Workers, Local 6',
       'Prof & Tech Engineers - Personnel, Local 21',
       'Plumbers and Pipefitters, Local 38',
       'Operating Engineers - Miscellaneous, Local 3',
       'Miscellaneous Unrepresented Employees',
       'Sheet Metal Workers, Local 104',
       'Management Unrepresented Employees',
       'Members of Boards and Commissions',
       'Transport Workers - Miscellaneous, Local 250-A',
       "Deputy Probation Officers' Association", 'Pile Drivers, Local 34',
       'SEIU - Court Employees, Local 1021',
       "Municipal Attorneys' Association",
       'Physicians and Dentists - Miscellaneous',
       'Members of Boards and Commissions - No Benefits',
       'Teamsters, Local 853', 'Painters, Local 1176',
       "Sheriff's Managers and Supervisors Association",
       'Court Unrepresented Bench Officers',
       'Transport Workers - Fare Inspectors, Local 250-A',
       'Carpenters, Local 22', 'Theatrical and Stage Employees, Local 16',
       "District Attorney Investigators' Association",
       'Teamsters - Miscellaneous, Local 856',
       'Members of the Board of Supervisors',
       'Physicians and Dentists - Spv Physician Specialist',
       'Court Unrepresented Professionals',
       'Firefighters Unit 1, Local 798',
       'Court Interpreters, Local 39521',
       'Roofers and Waterproofers, Local 40',
       "Building Inspectors' Association - Inspectors",
       'Bricklayers, Local 3',
       'Prof & Tech Engineers - Court Employees, Local 21',
       'Iron Workers, Local 377', 'Cement Masons, Local 300',
       'Prof & Tech Engineers - Court Reporters, Local 21',
       'Glaziers, Metal, and Glass Workers, Local 718',
       'Operating Engineers - Sup Probation Ofcrs, Local 3',
       'Municipal Executive Association - Court',
       'Law Librarian and Assistant',
       "Building Inspectors' Association - Chiefs",
       'Municipal Executive Association - Police',
       'Municipal Executive Association - Fire',
       'Hod Carriers, Local 166', 'Court Unrepresented Managers',
       'Elected Officials', 'SEIU - Firefighter Paramedics, Local 1021',
       'Carpet, Linoleum and Soft Tile Workers, Local 12',
       'Laborers Int, Local 261', 'Executive Contract Employees',
       "Institutional Police Officers' Association", 'Port Director',
       'POA', 'Management Unrepresented Employees - MTA'], dtype=object)

train_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	62828 	DPH 	Public Health 	250 	SEIU - Health Workers, Local 1021 	Med Therapy & Auxiliary 	Morgue Attendant 	6725 	12196 	0 	0.00 	Calendar 	16158
1 	2013 	4 	62828 	DPH 	Public Health 	39 	Stationary Engineers, Local 39 	Journeyman Trade 	Stationary Engineer 	25058 	74639 	2820 	12703.31 	Fiscal 	115784
2 	2015 	6 	25912 	ASR 	Assessor/Recorder 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Appraisal & Taxation 	Senior Real Property Appraiser 	46108 	100554 	0 	12424.50 	Calendar 	144708
3 	2016 	1 	54769 	POL 	Police 	911 	Police Officers' Association 	Police Services 	Sergeant 3 	33369 	140164 	52754 	13043.87 	Fiscal 	242323
4 	2013 	2 	91239 	HHP 	PUC Hetch Hetchy 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Information Systems 	IS Engineer-Journey 	28684 	58813 	0 	7655.28 	Calendar 	82106
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	DSS 	Human Services 	535 	SEIU - Human Services, Local 1021 	Human Services 	Senior Eligibility Worker 	9610 	78980 	30115 	13068.80 	Fiscal 	147079
287832 	2015 	5 	26055 	LIB 	Public Library 	790 	SEIU - Miscellaneous, Local 1021 	Library 	Librarian 1 	790 	30704 	0 	5465.57 	Calendar 	40174
287833 	2014 	2 	91239 	HHP 	PUC Hetch Hetchy 	6 	Electrical Workers, Local 6 	Journeyman Trade 	Electronic Maintenance Tech 	38352 	104451 	0 	13054.94 	Calendar 	164669
287834 	2013 	1 	54769 	JUV 	Juvenile Probation 	250 	SEIU - Health Workers, Local 1021 	Housekeeping & Laundry 	Porter 	29266 	14425 	0 	4051.90 	Calendar 	19594
287835 	2015 	4 	62828 	DPH 	Public Health 	791 	SEIU - Staff and Per Diem Nurses, Local 1021 	Nursing 	Special Nurse 	13906 	105561 	8945 	7993.89 	Fiscal 	154197

287798 rows × 15 columns

cols = ['DC','Dept','Union','JF','Job']

train_data.DC.value_counts().to_dict()
df_frequency_map = train_data.DC.value_counts().to_dict()
# train_data[cols].map(df_frequency_map)
train_data.DC = train_data.DC.map(df_frequency_map)
    

train_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	62828 	62834 	Public Health 	250 	SEIU - Health Workers, Local 1021 	Med Therapy & Auxiliary 	Morgue Attendant 	6725 	12196 	0 	0.00 	Calendar 	16158
1 	2013 	4 	62828 	62834 	Public Health 	39 	Stationary Engineers, Local 39 	Journeyman Trade 	Stationary Engineer 	25058 	74639 	2820 	12703.31 	Fiscal 	115784
2 	2015 	6 	25912 	1293 	Assessor/Recorder 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Appraisal & Taxation 	Senior Real Property Appraiser 	46108 	100554 	0 	12424.50 	Calendar 	144708
3 	2016 	1 	54769 	22896 	Police 	911 	Police Officers' Association 	Police Services 	Sergeant 3 	33369 	140164 	52754 	13043.87 	Fiscal 	242323
4 	2013 	2 	91239 	2897 	PUC Hetch Hetchy 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Information Systems 	IS Engineer-Journey 	28684 	58813 	0 	7655.28 	Calendar 	82106
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	23839 	Human Services 	535 	SEIU - Human Services, Local 1021 	Human Services 	Senior Eligibility Worker 	9610 	78980 	30115 	13068.80 	Fiscal 	147079
287832 	2015 	5 	26055 	6598 	Public Library 	790 	SEIU - Miscellaneous, Local 1021 	Library 	Librarian 1 	790 	30704 	0 	5465.57 	Calendar 	40174
287833 	2014 	2 	91239 	2897 	PUC Hetch Hetchy 	6 	Electrical Workers, Local 6 	Journeyman Trade 	Electronic Maintenance Tech 	38352 	104451 	0 	13054.94 	Calendar 	164669
287834 	2013 	1 	54769 	2363 	Juvenile Probation 	250 	SEIU - Health Workers, Local 1021 	Housekeeping & Laundry 	Porter 	29266 	14425 	0 	4051.90 	Calendar 	19594
287835 	2015 	4 	62828 	62834 	Public Health 	791 	SEIU - Staff and Per Diem Nurses, Local 1021 	Nursing 	Special Nurse 	13906 	105561 	8945 	7993.89 	Fiscal 	154197

287798 rows × 15 columns

train_data.Dept.value_counts().to_dict()
df_frequency_map = train_data.Dept.value_counts().to_dict()
# train_data[cols].map(df_frequency_map)
train_data.Dept = train_data.Dept.map(df_frequency_map)
    

train_data.head()

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	62828 	62834 	62859 	250 	SEIU - Health Workers, Local 1021 	Med Therapy & Auxiliary 	Morgue Attendant 	6725 	12196 	0 	0.00 	Calendar 	16158
1 	2013 	4 	62828 	62834 	62859 	39 	Stationary Engineers, Local 39 	Journeyman Trade 	Stationary Engineer 	25058 	74639 	2820 	12703.31 	Fiscal 	115784
2 	2015 	6 	25912 	1293 	1301 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Appraisal & Taxation 	Senior Real Property Appraiser 	46108 	100554 	0 	12424.50 	Calendar 	144708
3 	2016 	1 	54769 	22896 	22911 	911 	Police Officers' Association 	Police Services 	Sergeant 3 	33369 	140164 	52754 	13043.87 	Fiscal 	242323
4 	2013 	2 	91239 	2897 	2894 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Information Systems 	IS Engineer-Journey 	28684 	58813 	0 	7655.28 	Calendar 	82106

train_data.Union.value_counts().to_dict()
df_frequency_map = train_data.Union.value_counts().to_dict()
# train_data[cols].map(df_frequency_map)
train_data.Union = train_data.Union.map(df_frequency_map)
    

train_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	62828 	62834 	62859 	250 	16317 	Med Therapy & Auxiliary 	Morgue Attendant 	6725 	12196 	0 	0.00 	Calendar 	16158
1 	2013 	4 	62828 	62834 	62859 	39 	4602 	Journeyman Trade 	Stationary Engineer 	25058 	74639 	2820 	12703.31 	Fiscal 	115784
2 	2015 	6 	25912 	1293 	1301 	21 	36130 	Appraisal & Taxation 	Senior Real Property Appraiser 	46108 	100554 	0 	12424.50 	Calendar 	144708
3 	2016 	1 	54769 	22896 	22911 	911 	19177 	Police Services 	Sergeant 3 	33369 	140164 	52754 	13043.87 	Fiscal 	242323
4 	2013 	2 	91239 	2897 	2894 	21 	36130 	Information Systems 	IS Engineer-Journey 	28684 	58813 	0 	7655.28 	Calendar 	82106
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	23839 	23847 	535 	12752 	Human Services 	Senior Eligibility Worker 	9610 	78980 	30115 	13068.80 	Fiscal 	147079
287832 	2015 	5 	26055 	6598 	6597 	790 	81349 	Library 	Librarian 1 	790 	30704 	0 	5465.57 	Calendar 	40174
287833 	2014 	2 	91239 	2897 	2894 	6 	6059 	Journeyman Trade 	Electronic Maintenance Tech 	38352 	104451 	0 	13054.94 	Calendar 	164669
287834 	2013 	1 	54769 	2363 	2356 	250 	16317 	Housekeeping & Laundry 	Porter 	29266 	14425 	0 	4051.90 	Calendar 	19594
287835 	2015 	4 	62828 	62834 	62859 	791 	21861 	Nursing 	Special Nurse 	13906 	105561 	8945 	7993.89 	Fiscal 	154197

287798 rows × 15 columns

train_data.JF.value_counts().to_dict()
df_frequency_map = train_data.JF.value_counts().to_dict()
# train_data[cols].map(df_frequency_map)
train_data.JF = train_data.JF.map(df_frequency_map)
    

train_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	62828 	62834 	62859 	250 	16317 	5777 	Morgue Attendant 	6725 	12196 	0 	0.00 	Calendar 	16158
1 	2013 	4 	62828 	62834 	62859 	39 	4602 	17052 	Stationary Engineer 	25058 	74639 	2820 	12703.31 	Fiscal 	115784
2 	2015 	6 	25912 	1293 	1301 	21 	36130 	1357 	Senior Real Property Appraiser 	46108 	100554 	0 	12424.50 	Calendar 	144708
3 	2016 	1 	54769 	22896 	22911 	911 	19177 	19170 	Sergeant 3 	33369 	140164 	52754 	13043.87 	Fiscal 	242323
4 	2013 	2 	91239 	2897 	2894 	21 	36130 	6423 	IS Engineer-Journey 	28684 	58813 	0 	7655.28 	Calendar 	82106
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	23839 	23847 	535 	12752 	14869 	Senior Eligibility Worker 	9610 	78980 	30115 	13068.80 	Fiscal 	147079
287832 	2015 	5 	26055 	6598 	6597 	790 	81349 	5380 	Librarian 1 	790 	30704 	0 	5465.57 	Calendar 	40174
287833 	2014 	2 	91239 	2897 	2894 	6 	6059 	17052 	Electronic Maintenance Tech 	38352 	104451 	0 	13054.94 	Calendar 	164669
287834 	2013 	1 	54769 	2363 	2356 	250 	16317 	9370 	Porter 	29266 	14425 	0 	4051.90 	Calendar 	19594
287835 	2015 	4 	62828 	62834 	62859 	791 	21861 	30047 	Special Nurse 	13906 	105561 	8945 	7993.89 	Fiscal 	154197

287798 rows × 15 columns

train_data.Job.value_counts().to_dict()
df_frequency_map = train_data.Job.value_counts().to_dict()
# train_data[cols].map(df_frequency_map)
train_data.Job = train_data.Job.map(df_frequency_map)
    

train_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation
0 	2015 	4 	62828 	62834 	62859 	250 	16317 	5777 	37 	6725 	12196 	0 	0.00 	Calendar 	16158
1 	2013 	4 	62828 	62834 	62859 	39 	4602 	17052 	1620 	25058 	74639 	2820 	12703.31 	Fiscal 	115784
2 	2015 	6 	25912 	1293 	1301 	21 	36130 	1357 	88 	46108 	100554 	0 	12424.50 	Calendar 	144708
3 	2016 	1 	54769 	22896 	22911 	911 	19177 	19170 	2753 	33369 	140164 	52754 	13043.87 	Fiscal 	242323
4 	2013 	2 	91239 	2897 	2894 	21 	36130 	6423 	445 	28684 	58813 	0 	7655.28 	Calendar 	82106
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	23839 	23847 	535 	12752 	14869 	3062 	9610 	78980 	30115 	13068.80 	Fiscal 	147079
287832 	2015 	5 	26055 	6598 	6597 	790 	81349 	5380 	1341 	790 	30704 	0 	5465.57 	Calendar 	40174
287833 	2014 	2 	91239 	2897 	2894 	6 	6059 	17052 	1112 	38352 	104451 	0 	13054.94 	Calendar 	164669
287834 	2013 	1 	54769 	2363 	2356 	250 	16317 	9370 	2600 	29266 	14425 	0 	4051.90 	Calendar 	19594
287835 	2015 	4 	62828 	62834 	62859 	791 	21861 	30047 	10445 	13906 	105561 	8945 	7993.89 	Fiscal 	154197

287798 rows × 15 columns

one_hot  =  pd.get_dummies(train_data.YT)

df = pd.concat([train_data, one_hot], axis=1)

df

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT 	Total_Compensation 	Calendar 	Fiscal
0 	2015 	4 	62828 	62834 	62859 	250 	16317 	5777 	37 	6725 	12196 	0 	0.00 	Calendar 	16158 	1 	0
1 	2013 	4 	62828 	62834 	62859 	39 	4602 	17052 	1620 	25058 	74639 	2820 	12703.31 	Fiscal 	115784 	0 	1
2 	2015 	6 	25912 	1293 	1301 	21 	36130 	1357 	88 	46108 	100554 	0 	12424.50 	Calendar 	144708 	1 	0
3 	2016 	1 	54769 	22896 	22911 	911 	19177 	19170 	2753 	33369 	140164 	52754 	13043.87 	Fiscal 	242323 	0 	1
4 	2013 	2 	91239 	2897 	2894 	21 	36130 	6423 	445 	28684 	58813 	0 	7655.28 	Calendar 	82106 	1 	0
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	23839 	23847 	535 	12752 	14869 	3062 	9610 	78980 	30115 	13068.80 	Fiscal 	147079 	0 	1
287832 	2015 	5 	26055 	6598 	6597 	790 	81349 	5380 	1341 	790 	30704 	0 	5465.57 	Calendar 	40174 	1 	0
287833 	2014 	2 	91239 	2897 	2894 	6 	6059 	17052 	1112 	38352 	104451 	0 	13054.94 	Calendar 	164669 	1 	0
287834 	2013 	1 	54769 	2363 	2356 	250 	16317 	9370 	2600 	29266 	14425 	0 	4051.90 	Calendar 	19594 	1 	0
287835 	2015 	4 	62828 	62834 	62859 	791 	21861 	30047 	10445 	13906 	105561 	8945 	7993.89 	Fiscal 	154197 	0 	1

287798 rows × 17 columns

f_train_data = df.drop('YT',axis=1)

f_train_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	Total_Compensation 	Calendar 	Fiscal
0 	2015 	4 	62828 	62834 	62859 	250 	16317 	5777 	37 	6725 	12196 	0 	0.00 	16158 	1 	0
1 	2013 	4 	62828 	62834 	62859 	39 	4602 	17052 	1620 	25058 	74639 	2820 	12703.31 	115784 	0 	1
2 	2015 	6 	25912 	1293 	1301 	21 	36130 	1357 	88 	46108 	100554 	0 	12424.50 	144708 	1 	0
3 	2016 	1 	54769 	22896 	22911 	911 	19177 	19170 	2753 	33369 	140164 	52754 	13043.87 	242323 	0 	1
4 	2013 	2 	91239 	2897 	2894 	21 	36130 	6423 	445 	28684 	58813 	0 	7655.28 	82106 	1 	0
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
287831 	2016 	3 	26702 	23839 	23847 	535 	12752 	14869 	3062 	9610 	78980 	30115 	13068.80 	147079 	0 	1
287832 	2015 	5 	26055 	6598 	6597 	790 	81349 	5380 	1341 	790 	30704 	0 	5465.57 	40174 	1 	0
287833 	2014 	2 	91239 	2897 	2894 	6 	6059 	17052 	1112 	38352 	104451 	0 	13054.94 	164669 	1 	0
287834 	2013 	1 	54769 	2363 	2356 	250 	16317 	9370 	2600 	29266 	14425 	0 	4051.90 	19594 	1 	0
287835 	2015 	4 	62828 	62834 	62859 	791 	21861 	30047 	10445 	13906 	105561 	8945 	7993.89 	154197 	0 	1

287798 rows × 16 columns

f_train_data.corr()

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	Total_Compensation 	Calendar 	Fiscal
Year 	1.00 	-0.01 	0.00 	0.00 	0.00 	-0.00 	0.01 	-0.01 	0.00 	0.00 	0.00 	0.02 	-0.01 	0.01 	-0.30 	0.30
OGC 	-0.01 	1.00 	-0.58 	0.13 	0.13 	-0.01 	0.28 	-0.04 	-0.10 	0.00 	-0.22 	-0.30 	-0.23 	-0.27 	-0.00 	0.00
OG 	0.00 	-0.58 	1.00 	0.26 	0.26 	-0.26 	-0.16 	0.15 	0.20 	0.00 	0.11 	0.11 	0.16 	0.14 	0.00 	-0.00
DC 	0.00 	0.13 	0.26 	1.00 	1.00 	0.03 	-0.10 	0.49 	0.32 	0.01 	-0.04 	-0.03 	-0.05 	-0.03 	0.01 	-0.01
Dept 	0.00 	0.13 	0.26 	1.00 	1.00 	0.03 	-0.10 	0.49 	0.32 	0.01 	-0.04 	-0.03 	-0.05 	-0.03 	0.01 	-0.01
UC 	-0.00 	-0.01 	-0.26 	0.03 	0.03 	1.00 	0.50 	0.16 	0.04 	-0.00 	-0.05 	0.06 	-0.07 	-0.03 	-0.00 	0.00
Union 	0.01 	0.28 	-0.16 	-0.10 	-0.10 	0.50 	1.00 	-0.26 	-0.18 	0.00 	-0.30 	-0.20 	-0.14 	-0.32 	-0.00 	0.00
JF 	-0.01 	-0.04 	0.15 	0.49 	0.49 	0.16 	-0.26 	1.00 	0.61 	0.00 	-0.00 	0.11 	-0.09 	0.03 	0.01 	-0.01
Job 	0.00 	-0.10 	0.20 	0.32 	0.32 	0.04 	-0.18 	0.61 	1.00 	-0.00 	-0.12 	0.13 	-0.06 	-0.07 	0.01 	-0.01
EI 	0.00 	0.00 	0.00 	0.01 	0.01 	-0.00 	0.00 	0.00 	-0.00 	1.00 	-0.00 	-0.00 	-0.00 	-0.00 	-0.00 	0.00
Salaries 	0.00 	-0.22 	0.11 	-0.04 	-0.04 	-0.05 	-0.30 	-0.00 	-0.12 	-0.00 	1.00 	0.27 	0.77 	0.97 	0.01 	-0.01
Overtime 	0.02 	-0.30 	0.11 	-0.03 	-0.03 	0.06 	-0.20 	0.11 	0.13 	-0.00 	0.27 	1.00 	0.31 	0.45 	-0.00 	0.00
H/D 	-0.01 	-0.23 	0.16 	-0.05 	-0.05 	-0.07 	-0.14 	-0.09 	-0.06 	-0.00 	0.77 	0.31 	1.00 	0.81 	0.01 	-0.01
Total_Compensation 	0.01 	-0.27 	0.14 	-0.03 	-0.03 	-0.03 	-0.32 	0.03 	-0.07 	-0.00 	0.97 	0.45 	0.81 	1.00 	0.01 	-0.01
Calendar 	-0.30 	-0.00 	0.00 	0.01 	0.01 	-0.00 	-0.00 	0.01 	0.01 	-0.00 	0.01 	-0.00 	0.01 	0.01 	1.00 	-1.00
Fiscal 	0.30 	0.00 	-0.00 	-0.01 	-0.01 	0.00 	0.00 	-0.01 	-0.01 	0.00 	-0.01 	0.00 	-0.01 	-0.01 	-1.00 	1.00

import seaborn as sns

sns.heatmap(f_train_data.corr(),annot=True)

<matplotlib.axes._subplots.AxesSubplot at 0x7f09ccfe5b10>

n_train_data = f_train_data.drop_duplicates()

X = n_train_data.drop("Total_Compensation",axis=1)   #Feature Matrix
y = n_train_data["Total_Compensation"]

# separate dataset into train and test
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.3,
    random_state=0)

X_train.shape, X_test.shape

((200979, 15), (86134, 15))

def correlation(dataset, threshold):
    col_corr = set()  # Set of all the names of correlated columns
    corr_matrix = dataset.corr()
    for i in range(len(corr_matrix.columns)):
        for j in range(i):
            if abs(corr_matrix.iloc[i, j]) > threshold: # we are interested in absolute coeff value
                colname = corr_matrix.columns[i]  # getting the name of column
                col_corr.add(colname)
    return col_corr

corr_features = correlation(X_train, 0.75)
len(set(corr_features))

3

corr_features

{'Dept', 'Fiscal', 'H/D'}

x_train  = X_train.drop(corr_features,axis=1)
x_test = X_test.drop(corr_features,axis=1)

from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

cols_to_scale = ['Year','OGC','OG','DC','UC','Union','JF','Job','EI','Salaries','Overtime','Calendar']

scaler = MinMaxScaler()
x_train[cols_to_scale] = scaler.fit_transform(x_train[cols_to_scale])

x_test[cols_to_scale] = scaler.fit_transform(x_test[cols_to_scale])

x_train.head()

	Year 	OGC 	OG 	DC 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	Calendar
149438 	0.33 	0.00 	0.60 	0.12 	0.50 	0.06 	0.26 	0.02 	0.20 	0.13 	0.02 	0.00
101266 	0.00 	0.67 	0.28 	0.10 	0.80 	1.00 	0.18 	0.08 	0.02 	0.17 	0.00 	1.00
88825 	0.33 	0.17 	1.00 	0.67 	0.25 	0.22 	0.79 	1.00 	0.68 	0.12 	0.04 	0.00
73073 	0.67 	0.33 	0.29 	0.38 	0.80 	1.00 	0.52 	0.28 	0.17 	0.03 	0.00 	0.00
171489 	0.33 	0.50 	0.69 	1.00 	0.80 	1.00 	0.19 	0.06 	0.77 	0.16 	0.00 	1.00

x_test.head()

	Year 	OGC 	OG 	DC 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	Calendar
80410 	0.67 	0.17 	1.00 	0.67 	0.01 	0.07 	0.57 	0.09 	0.20 	0.27 	0.15 	0.00
105343 	0.00 	0.00 	0.60 	0.18 	0.81 	0.13 	0.37 	0.32 	0.17 	0.26 	0.34 	1.00
68421 	1.00 	0.17 	1.00 	0.11 	0.35 	0.10 	0.31 	0.06 	0.36 	0.35 	0.06 	0.00
237738 	0.00 	0.50 	0.69 	1.00 	0.02 	0.44 	0.01 	0.00 	0.21 	0.43 	0.06 	1.00
194949 	1.00 	0.00 	0.60 	0.36 	0.92 	0.24 	0.64 	0.33 	0.42 	0.33 	0.08 	0.00

import lazypredict

from lazypredict.Supervised import LazyRegressor

from sklearn.utils import shuffle
import numpy as np

test_data = pd.read_csv('/content/test_set.csv')

test_data.head()

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT
0 	2016 	2 	Public Works, Transportation & Commerce 	AIR 	Airport Commission 	790 	SEIU - Miscellaneous, Local 1021 	Budget, Admn & Stats Analysis 	Management Assistant 	6161 	74526 	0 	13068.80 	Fiscal
1 	2013 	3 	Human Welfare & Neighborhood Development 	DSS 	Human Services 	1 	Miscellaneous Unrepresented Employees 	Public Service Aide 	Public Svc Aide-Public Works 	17890 	7219 	0 	3328.05 	Calendar
2 	2016 	2 	Public Works, Transportation & Commerce 	PUC 	PUC Public Utilities Commission 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Sub-Professional Engineering 	Stdntdsgntrain1, Arch/Eng/Plng 	15092 	4616 	0 	1147.26 	Fiscal
3 	2015 	3 	Human Welfare & Neighborhood Development 	DSS 	Human Services 	535 	SEIU - Human Services, Local 1021 	Human Services 	Eligibility Worker 	5144 	6345 	0 	1433.60 	Calendar
4 	2015 	2 	Public Works, Transportation & Commerce 	HHP 	PUC Hetch Hetchy 	6 	Electrical Workers, Local 6 	Journeyman Trade 	Trans And Dist Line Worker 	40128 	105851 	153 	12242.44 	Calendar

test_data.isnull().sum()

Year        0
OGC         0
OG          0
DC          0
Dept        0
UC          0
Union       7
JF          7
Job         0
EI          0
Salaries    0
Overtime    0
H/D         0
YT          0
dtype: int64

test_data['Union'].fillna(test_data['Union'].mode()[0], inplace=True)

test_data.isnull().sum()

Year        0
OGC         0
OG          0
DC          0
Dept        0
UC          0
Union       0
JF          7
Job         0
EI          0
Salaries    0
Overtime    0
H/D         0
YT          0
dtype: int64

test_data['JF'].fillna(test_data['JF'].mode()[0], inplace=True)

test_data.OG.value_counts().to_dict()
df_frequency_map = test_data.OG.value_counts().to_dict()
test_data.OG = test_data.OG.map(df_frequency_map)

test_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT
0 	2016 	2 	15314 	AIR 	Airport Commission 	790 	SEIU - Miscellaneous, Local 1021 	Budget, Admn & Stats Analysis 	Management Assistant 	6161 	74526 	0 	13068.80 	Fiscal
1 	2013 	3 	4420 	DSS 	Human Services 	1 	Miscellaneous Unrepresented Employees 	Public Service Aide 	Public Svc Aide-Public Works 	17890 	7219 	0 	3328.05 	Calendar
2 	2016 	2 	15314 	PUC 	PUC Public Utilities Commission 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Sub-Professional Engineering 	Stdntdsgntrain1, Arch/Eng/Plng 	15092 	4616 	0 	1147.26 	Fiscal
3 	2015 	3 	4420 	DSS 	Human Services 	535 	SEIU - Human Services, Local 1021 	Human Services 	Eligibility Worker 	5144 	6345 	0 	1433.60 	Calendar
4 	2015 	2 	15314 	HHP 	PUC Hetch Hetchy 	6 	Electrical Workers, Local 6 	Journeyman Trade 	Trans And Dist Line Worker 	40128 	105851 	153 	12242.44 	Calendar
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
47855 	2015 	4 	10414 	DPH 	Public Health 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Budget, Admn & Stats Analysis 	Senior Administrative Analyst 	23825 	91767 	0 	11176.32 	Calendar
47856 	2013 	2 	15314 	AIR 	Airport Commission 	790 	SEIU - Miscellaneous, Local 1021 	Housekeeping & Laundry 	Custodian 	16397 	44603 	0 	10471.44 	Calendar
47857 	2015 	5 	4286 	REC 	Recreation and Park Commission 	790 	SEIU - Miscellaneous, Local 1021 	Housekeeping & Laundry 	Custodian 	37834 	49274 	0 	11019.75 	Fiscal
47858 	2013 	2 	15314 	MTA 	Municipal Transportation Agency 	21 	Prof & Tech Engineers - Miscellaneous, Local 21 	Legal & Court 	Parking Hearing Examiner 	49141 	69972 	0 	9699.15 	Calendar
47859 	2015 	4 	10414 	DPH 	Public Health 	791 	SEIU - Staff and Per Diem Nurses, Local 1021 	Nursing 	Registered Nurse 	38462 	129524 	0 	12424.50 	Calendar

47860 rows × 14 columns

test_data.DC.value_counts().to_dict()
df_frequency_map = test_data.DC.value_counts().to_dict()
test_data.DC = test_data.DC.map(df_frequency_map)

test_data.Dept.value_counts().to_dict()
df_frequency_map = test_data.Dept.value_counts().to_dict()
test_data.Dept = test_data.Dept.map(df_frequency_map)


test_data.Union.value_counts().to_dict()
df_frequency_map = test_data.Union.value_counts().to_dict()
test_data.Union = test_data.Union.map(df_frequency_map)


test_data.JF.value_counts().to_dict()
df_frequency_map = test_data.JF.value_counts().to_dict()
test_data.JF = test_data.JF.map(df_frequency_map)

test_data.Job.value_counts().to_dict()
df_frequency_map = test_data.Job.value_counts().to_dict()
test_data.Job = test_data.Job.map(df_frequency_map)

test_data

	Year 	OGC 	OG 	DC 	Dept 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	H/D 	YT
0 	2016 	2 	15314 	2364 	2369 	790 	13473 	1283 	144 	6161 	74526 	0 	13068.80 	Fiscal
1 	2013 	3 	4420 	3982 	3985 	1 	1159 	2456 	1078 	17890 	7219 	0 	3328.05 	Calendar
2 	2016 	2 	15314 	1095 	1093 	21 	6042 	675 	243 	15092 	4616 	0 	1147.26 	Fiscal
3 	2015 	3 	4420 	3982 	3985 	535 	2136 	2456 	352 	5144 	6345 	0 	1433.60 	Calendar
4 	2015 	2 	15314 	448 	449 	6 	999 	2872 	11 	40128 	105851 	153 	12242.44 	Calendar
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
47855 	2015 	4 	10414 	10415 	10417 	21 	6042 	1283 	301 	23825 	91767 	0 	11176.32 	Calendar
47856 	2013 	2 	15314 	2364 	2369 	790 	13473 	1628 	1013 	16397 	44603 	0 	10471.44 	Calendar
47857 	2015 	5 	4286 	2634 	2637 	790 	13473 	1628 	1013 	37834 	49274 	0 	11019.75 	Fiscal
47858 	2013 	2 	15314 	7001 	6996 	21 	6042 	1061 	14 	49141 	69972 	0 	9699.15 	Calendar
47859 	2015 	4 	10414 	10415 	10417 	791 	3612 	5055 	1490 	38462 	129524 	0 	12424.50 	Calendar

47860 rows × 14 columns

one_hot  =  pd.get_dummies(test_data.YT)
df = pd.concat([test_data, one_hot], axis=1)
f_test_data = df.drop('YT',axis=1)
# {'Dept', 'Fiscal', 'H/D'}(drop)

d_test_data = f_test_data.drop(['Dept','Fiscal','H/D'],axis=1)

d_test_data

	Year 	OGC 	OG 	DC 	UC 	Union 	JF 	Job 	EI 	Salaries 	Overtime 	Calendar
0 	2016 	2 	15314 	2364 	790 	13473 	1283 	144 	6161 	74526 	0 	0
1 	2013 	3 	4420 	3982 	1 	1159 	2456 	1078 	17890 	7219 	0 	1
2 	2016 	2 	15314 	1095 	21 	6042 	675 	243 	15092 	4616 	0 	0
3 	2015 	3 	4420 	3982 	535 	2136 	2456 	352 	5144 	6345 	0 	1
4 	2015 	2 	15314 	448 	6 	999 	2872 	11 	40128 	105851 	153 	1
... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	... 	...
47855 	2015 	4 	10414 	10415 	21 	6042 	1283 	301 	23825 	91767 	0 	1
47856 	2013 	2 	15314 	2364 	790 	13473 	1628 	1013 	16397 	44603 	0 	1
47857 	2015 	5 	4286 	2634 	790 	13473 	1628 	1013 	37834 	49274 	0 	0
47858 	2013 	2 	15314 	7001 	21 	6042 	1061 	14 	49141 	69972 	0 	1
47859 	2015 	4 	10414 	10415 	791 	3612 	5055 	1490 	38462 	129524 	0 	1

47860 rows × 12 columns

cols_to_scale = ['Year','OGC','OG','DC','UC','Union','JF','Job','EI','Salaries','Overtime','Calendar']

scaler = MinMaxScaler()
d_test_data[cols_to_scale] = scaler.fit_transform(d_test_data[cols_to_scale])

d_test_data.isnull().sum()

Year        0
OGC         0
OG          0
DC          0
UC          0
Union       0
JF          0
Job         0
EI          0
Salaries    0
Overtime    0
Calendar    0
dtype: int64

target = regressor.predict(d_test_data)

# To create Dataframe of predicted value with particular respective index
res = pd.DataFrame(target) # target are nothing but the final predictions of your model on input features of your new unseen test data
res.index = test_data.index # its important for comparison. Here "test_new" is your new test dataset
res.columns = ['Compensation']

# calculate-an-estimated-Total-Compensation-for-each-employee.
The HR department asks your help if you can use your data science and machine learning skills and calculate an estimated ‘Total Compensation’ for each employee.
