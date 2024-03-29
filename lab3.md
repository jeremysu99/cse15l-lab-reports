# Lab Report 3

## Part 1:


Input that caused the bug: 

`int[] input1 = {1,2,3};`

Associated code with the bug: 

```
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{3,2,1}, input1);
```



Input that caused the pass:

`int[] input1 = {1};`

Associated code with the pass:

`assertArrayEquals(new int[]{1}, ArrayExamples.reversed(input1));`

Bug symptom: 

<img width="630" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/472a98b2-0558-4873-9797-177ddd474265">

Passed test symptom: 

<img width="414" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/303c7a95-a2a5-480d-8890-9da1e85b4b9c">

Before bug fixed:

```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```

After bug fixed:

```
static void reverseInPlace(int[] arr) {
  int[] tempArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    tempArray[i] = arr[arr.length - i - 1];
  }
  for (int i = 0; i < arr.length; i++)
    arr[i] = tempArray[i];
}
```

The reason that this new code addresses the issue is because the original code does not properly reverse the array in place due to a flaw in logic. The loop incorrectly iterates through the array, setting each value to its corresponding mirrored value on the other end of the array. However, this overwrites the existing data at the beginning of the array,
leaving the array a symmetric array with only the first half reversed. 

The adjusted code correctly creates a temporary array to avoid this data overwriting by first setting each value in the temp array to the reversed value in the real array, then changing each value in the original array to the temp array's values. This properly reverses the original array in place.

## Part 2:

Option 1 - `find -depth d`: 

Example 1:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/911report -depth 1
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```

This command is finding all the contents within `./technica/911report` that has a depth of 1 from that directory. This is particularly useful if you want to find certain files or directories directly under 911report but don't want to include the contents of its subfolders.

Example 2:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/ -depth 3
technical//government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
technical//government/About_LSC/Progress_report.txt
technical//government/About_LSC/Strategic_report.txt
technical//government/About_LSC/Comments_on_semiannual.txt
technical//government/About_LSC/Special_report_to_congress.txt
technical//government/About_LSC/CONFIG_STANDARDS.txt
technical//government/About_LSC/commission_report.txt
technical//government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
technical//government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
technical//government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
technical//government/About_LSC/diversity_priorities.txt
technical//government/About_LSC/reporting_system.txt
technical//government/About_LSC/State_Planning_Report.txt
technical//government/About_LSC/Protocol_Regarding_Access.txt
technical//government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
technical//government/About_LSC/conference_highlights.txt
technical//government/About_LSC/State_Planning_Special_Report.txt
technical//government/Env_Prot_Agen/multi102902.txt
technical//government/Env_Prot_Agen/section-by-section_summary.txt
technical//government/Env_Prot_Agen/jeffordslieberm.txt
technical//government/Env_Prot_Agen/final.txt
technical//government/Env_Prot_Agen/ctf7-10.txt
technical//government/Env_Prot_Agen/ctf1-6.txt
technical//government/Env_Prot_Agen/ro_clear_skies_book.txt
technical//government/Env_Prot_Agen/ctm4-10.txt
technical//government/Env_Prot_Agen/1-3_meth_901.txt
technical//government/Env_Prot_Agen/atx1-6.txt
technical//government/Env_Prot_Agen/tech_sectiong.txt
technical//government/Env_Prot_Agen/bill.txt
technical//government/Env_Prot_Agen/nov1.txt
technical//government/Env_Prot_Agen/tech_adden.txt
technical//government/Alcohol_Problems/Session2-PDF.txt
technical//government/Alcohol_Problems/Session3-PDF.txt
technical//government/Alcohol_Problems/DraftRecom-PDF.txt
technical//government/Alcohol_Problems/Session4-PDF.txt
technical//government/Gen_Account_Office/d0269g.txt
technical//government/Gen_Account_Office/Testimony_cg00010t.txt
technical//government/Gen_Account_Office/og97032.txt
technical//government/Gen_Account_Office/og99036.txt
technical//government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
technical//government/Gen_Account_Office/Sept27-2002_d02966.txt
technical//government/Gen_Account_Office/d01376g.txt
technical//government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
technical//government/Gen_Account_Office/og97019.txt
technical//government/Gen_Account_Office/pe1019.txt
technical//government/Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt
technical//government/Gen_Account_Office/gg96118.txt
technical//government/Gen_Account_Office/og97020.txt
technical//government/Gen_Account_Office/ffm.txt
technical//government/Gen_Account_Office/og97023.txt
technical//government/Gen_Account_Office/July11-2001_gg00172r.txt
technical//government/Gen_Account_Office/d01121g.txt
technical//government/Gen_Account_Office/og96011.txt
technical//government/Gen_Account_Office/d03419sp.txt
technical//government/Gen_Account_Office/Letter_Walkeraug17let.txt
technical//government/Gen_Account_Office/og97051.txt
technical//government/Gen_Account_Office/og97045.txt
technical//government/Gen_Account_Office/Testimony_d01609t.txt
technical//government/Gen_Account_Office/og97050.txt
technical//government/Gen_Account_Office/og96038.txt
technical//government/Gen_Account_Office/og98029.txt
technical//government/Gen_Account_Office/Sept14-2002_d011070.txt
technical//government/Gen_Account_Office/d03273g.txt
technical//government/Gen_Account_Office/Oct15-1999_gg00026t.txt
technical//government/Gen_Account_Office/og96012.txt
technical//government/Gen_Account_Office/og97046.txt
technical//government/Gen_Account_Office/og97052.txt
technical//government/Gen_Account_Office/d03232sp.txt
technical//government/Gen_Account_Office/og97043.txt
technical//government/Gen_Account_Office/June30-2000_gg00135r.txt
technical//government/Gen_Account_Office/d01591sp.txt
technical//government/Gen_Account_Office/Oct15-2001_d0224.txt
technical//government/Gen_Account_Office/og96028.txt
technical//government/Gen_Account_Office/og96014.txt
technical//government/Gen_Account_Office/og97041.txt
technical//government/Gen_Account_Office/og96015.txt
technical//government/Gen_Account_Office/d01145g.txt
technical//government/Gen_Account_Office/InternalControl_ai00021p.txt
technical//government/Gen_Account_Office/og96031.txt
technical//government/Gen_Account_Office/d01186g.txt
technical//government/Gen_Account_Office/og96033.txt
technical//government/Gen_Account_Office/og96027.txt
technical//government/Gen_Account_Office/og98022.txt
technical//government/Gen_Account_Office/og96026.txt
technical//government/Gen_Account_Office/og96032.txt
technical//government/Gen_Account_Office/im814.txt
technical//government/Gen_Account_Office/og96036.txt
technical//government/Gen_Account_Office/og96022.txt
technical//government/Gen_Account_Office/og96023.txt
technical//government/Gen_Account_Office/og96037.txt
technical//government/Gen_Account_Office/og98032.txt
technical//government/Gen_Account_Office/og98026.txt
technical//government/Gen_Account_Office/og98030.txt
technical//government/Gen_Account_Office/og98024.txt
technical//government/Gen_Account_Office/og96009.txt
technical//government/Gen_Account_Office/og96021.txt
technical//government/Gen_Account_Office/og98018.txt
technical//government/Gen_Account_Office/ai00134.txt
technical//government/Gen_Account_Office/og96034.txt
technical//government/Gen_Account_Office/og98019.txt
technical//government/Gen_Account_Office/og96020.txt
technical//government/Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt
technical//government/Gen_Account_Office/og96047.txt
technical//government/Gen_Account_Office/ai9868.txt
technical//government/Gen_Account_Office/og98041.txt
technical//government/Gen_Account_Office/og97038.txt
technical//government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt
technical//government/Gen_Account_Office/og97011.txt
technical//government/Gen_Account_Office/og97039.txt
technical//government/Gen_Account_Office/May1998_ai98068.txt
technical//government/Gen_Account_Office/og98040.txt
technical//government/Gen_Account_Office/og96045.txt
technical//government/Gen_Account_Office/og98044.txt
technical//government/Gen_Account_Office/og96041.txt
technical//government/Gen_Account_Office/d02701.txt
technical//government/Gen_Account_Office/og97001.txt
technical//government/Gen_Account_Office/og97028.txt
technical//government/Gen_Account_Office/ai2132.txt
technical//government/Gen_Account_Office/Letter_WalkerJan30-2001.txt
technical//government/Gen_Account_Office/og96040.txt
technical//government/Gen_Account_Office/og98045.txt
technical//government/Gen_Account_Office/og96042.txt
technical//government/Gen_Account_Office/og97002.txt
technical//government/Gen_Account_Office/og97003.txt
technical//government/Gen_Account_Office/og96043.txt
technical//government/Gen_Account_Office/og98046.txt
technical//government/Post_Rate_Comm/Gleiman_EMASpeech.txt
technical//government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
technical//government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
technical//government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
technical//government/Post_Rate_Comm/Mitchell_RMVancouver.txt
technical//government/Post_Rate_Comm/Gleiman_gca2000.txt
technical//government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
technical//government/Post_Rate_Comm/Redacted_Study.txt
technical//government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
technical//government/Post_Rate_Comm/Cohenetal_comparison.txt
technical//government/Post_Rate_Comm/Cohenetal_Scale.txt
technical//government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
technical//government/Post_Rate_Comm/ReportToCongress2002WEB.txt
technical//government/Post_Rate_Comm/WolakSpeech_usps.txt
technical//government/Media/Federal_agency.txt
technical//government/Media/water_fees.txt
technical//government/Media/Helping_Out.txt
technical//government/Media/balance_scales_of_justice.txt
technical//government/Media/BusinessWire2.txt
technical//government/Media/Legal-aid_chief.txt
technical//government/Media/Unusual_Woodburn.txt
technical//government/Media/Funding_cuts_force.txt
technical//government/Media/Good_guys_reward.txt
technical//government/Media/Anthem_Payout.txt
technical//government/Media/Donald_Hilliker.txt
technical//government/Media/Free_legal_service.txt
technical//government/Media/Owning_a_Piece.txt
technical//government/Media/Targeting_Domestic_Violence.txt
technical//government/Media/highlight_Senior_Day.txt
technical//government/Media/State_funding.txt
technical//government/Media/Few_who_need.txt
technical//government/Media/City_Council_Budget.txt
technical//government/Media/Legal_system_fails_poor.txt
technical//government/Media/Supporting_Legal_Center.txt
technical//government/Media/Lindsays_legacy.txt
technical//government/Media/New_funding_sources.txt
technical//government/Media/Barnes_new_job.txt
technical//government/Media/Providing_Legal_Aid.txt
technical//government/Media/Nonprofit_Buys.txt
technical//government/Media/Legal_Aid_in_Clay_County.txt
technical//government/Media/Domestic_Violence_Ruling.txt
technical//government/Media/Abuse_penalties.txt
technical//government/Media/Law_Award_from_College.txt
technical//government/Media/Law_Schools.txt
technical//government/Media/Raising_the_Bar.txt
technical//government/Media/Justice_for_all.txt
technical//government/Media/agency_expands.txt
technical//government/Media/Helping_Hands.txt
technical//government/Media/Legal_hotline.txt
technical//government/Media/not_accessible_to_disabled.txt
technical//government/Media/Campaign_Pays.txt
technical//government/Media/New_Online_Resources.txt
technical//government/Media/Annual_Fee.txt
technical//government/Media/Oregon_Poor.txt
technical//government/Media/Barnes_pro_bono.txt
technical//government/Media/Poor_Lacking_Legal_Aid.txt
technical//government/Media/Paralegal_Honored.txt
technical//government/Media/Workers_aid_center.txt
technical//government/Media/Philly_Lawyers.txt
technical//government/Media/Too_Crucial_to_Take_Cut.txt
technical//government/Media/Pro_Bono_Services.txt
technical//government/Media/Rumble_in_the_Bronx.txt
technical//government/Media/FortWorthStarTelegram.txt
technical//government/Media/predatory_loans.txt
technical//government/Media/Survey.txt
technical//government/Media/AP_LawSchoolDebts.txt
technical//government/Media/Working_for_Free.txt
technical//government/Media/Eviction_law.txt
technical//government/Media/Law-school_grads.txt
technical//government/Media/FY_04_Budget_Outlook.txt
technical//government/Media/help_rent-to-own_tenants.txt
technical//government/Media/Texas_Lawyer.txt
technical//government/Media/Disaster_center.txt
technical//government/Media/Kiosks_for_court_forms.txt
technical//government/Media/Higher_Registration_Fees.txt
technical//government/Media/Fire_Victims_Sue.txt
technical//government/Media/Funds_Shortage.txt
technical//government/Media/Terrorist_Attack.txt
technical//government/Media/Butler_Co_attorneys.txt
technical//government/Media/BergenCountyRecord.txt
technical//government/Media/families_saved.txt
technical//government/Media/Court_Keeps_Judge_From.txt
technical//government/Media/Volunteers_Step_Up.txt
technical//government/Media/Coup_Reshapes_Legal_Aid.txt
technical//government/Media/IOLTA_INTEREST_RATE.txt
technical//government/Media/Ginny_Kilgore.txt
technical//government/Media/Legal_Aid_looks_to_legislators.txt
technical//government/Media/Poverty_Lawyers.txt
technical//government/Media/Wingates_winds.txt
technical//government/Media/Avoids_Budget_Cut.txt
technical//government/Media/grants_fail_to_come.txt
technical//government/Media/Lockyer_Warns.txt
technical//government/Media/It_Pays_to_Know.txt
technical//government/Media/Self-Help_Website.txt
technical//government/Media/Rental_rules.txt
technical//government/Media/Using_Tech_Tools.txt
technical//government/Media/Assuring_Underprivileged.txt
technical//government/Media/Boone_legal_service.txt
technical//government/Media/Firm_to_the_Poor_Needs_Help.txt
technical//government/Media/Making_a_case.txt
technical//government/Media/Barnes_Volunteers.txt
technical//government/Media/Commercial_Appeal.txt
technical//government/Media/Justice_requests.txt
technical//government/Media/Free_Legal_Assistance.txt
technical//government/Media/Local_Attorneys.txt
technical//government/Media/Texas_Supreme_Court.txt
technical//government/Media/Civil_Matters.txt
technical//government/Media/Low-income_children.txt
technical//government/Media/man_on_national_team.txt
technical//government/Media/BusinessWire.txt
technical//government/Media/Funding_May_Limit.txt
technical//government/Media/The_Columbian.txt
technical//government/Media/Higher_court.txt
technical//government/Media/Service_Agency.txt
technical//government/Media/Marylands_Legal_Aid.txt
technical//government/Media/Bias_on_the_Job.txt
technical//government/Media/Attorney_gives_his_time.txt
technical//government/Media/Library_Lawyers.txt
technical//government/Media/Crains_New_York_Business.txt
technical//government/Media/Hard_to_Get.txt
technical//government/Media/The_State_of_Pro_Bono.txt
technical//government/Media/residents_sue_city.txt
technical//government/Media/Legal_Aid_Society.txt
technical//government/Media/GreensburgDailyNews.txt
technical//government/Media/Major_Changes.txt
technical//government/Media/Program_Lodges.txt
technical//government/Media/Wilmington_lawyer.txt
technical//government/Media/All_May_Have_Justice.txt
technical//government/Media/Domestic_violence_aid.txt
technical//government/Media/Advocate_for_Poor.txt
technical//government/Media/fight_domestic_abuse.txt
technical//government/Media/CommercialAppealMemphis2.txt
technical//government/Media/Weak_economy.txt
technical//government/Media/Lawyer_Web_Survey.txt
technical//government/Media/Valley_Needing_Legal_Services.txt
technical//government/Media/Barr_sharpening_ax.txt
technical//government/Media/Legal_Aid_attorney.txt
technical//government/Media/The_Bend_Bulletin.txt
technical//government/Media/Legal_services_for_poor.txt
technical//government/Media/Farm_workers.txt
technical//government/Media/Entities_Merge.txt
technical//government/Media/less_legal_aid.txt
technical//government/Media/Understanding.txt
technical//government/Media/Do-it-yourself_divorce.txt
technical//government/Media/Politician_Practices.txt
technical//government/Media/defend_yourself.txt
technical//government/Media/Towson_Attorney.txt
technical//government/Media/Pro-bono_road_show.txt
technical//government/Media/A_Perk_of_Age.txt
technical//government/Media/A_helping_hand.txt
technical//government/Media/pro_bono_efforts.txt
technical//government/Media/5_Legal_Groups.txt
technical//government/Media/Greedy_Generous.txt
technical//government/Media/Retirement_Has_Its_Appeal.txt
technical//government/Media/RoanokeTimes.txt
technical//government/Media/NJ_Legal_Services.txt
technical//government/Media/Bridging_legal_aid_gap.txt
technical//government/Media/Legal_Aid_campaign.txt
technical//government/Media/Aid_Gets_7_Million.txt
```

This command is finding all the contents within `./technical` that has a depth of 3 from that directory. This is particularly useful if you want to find all the files/directories beneath `./technical` that has exactly a depth of 3 from it without manually counting each one. 

Sources used: the `man` command

Option 2 - `find -user uname`:

Example 1:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/ -user unknownuser
find: -user: unknownuser: no such user
```

This command is finding all the contents within `./technical` that is owned by the user `unknownuser`. Since there is nothing owned by this user, it returns nothing. This is particularly useful if you want to quickly locate all the files/directories within `./techincal` that are owned by the user `unkownuser` without manually checking each one.

Example 2:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/government/Post_Rate_Comm -user jeremysu
technical/government/Post_Rate_Comm
technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt
technical/government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
technical/government/Post_Rate_Comm/Redacted_Study.txt
technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt
technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt
technical/government/Post_Rate_Comm/WolakSpeech_usps.txt
```

This command is finding all the contents within `./technical/government/Post_Rate_Comm` that is owned by the user `jeremysu`. Since I own every file/directory within this directory, it returns all the contents underneath this directory. This is particularly useful for quickly locating all the files/directories within `./technical/government/Post_Rate_Comm` that is owned by the user `jeremysu` without manually counting each one.

Sources used: the `man` command

Option 3 - `find -type t`:

Example 1:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/ -type dir
technical/
technical//government
technical//government/About_LSC
technical//government/Env_Prot_Agen
technical//government/Alcohol_Problems
technical//government/Gen_Account_Office
technical//government/Post_Rate_Comm
technical//government/Media
technical//plos
technical//biomed
technical//911report
```

This command is finding all the contents within `./technical` that is of the directory type. This is particularly useful for finding just the existing directories within `./technical` but not the files without manually going through and counting each folder.

Example 2:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/government/About_LSC -type f
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
technical/government/About_LSC/Progress_report.txt
technical/government/About_LSC/Strategic_report.txt
technical/government/About_LSC/Comments_on_semiannual.txt
technical/government/About_LSC/Special_report_to_congress.txt
technical/government/About_LSC/CONFIG_STANDARDS.txt
technical/government/About_LSC/commission_report.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
technical/government/About_LSC/diversity_priorities.txt
technical/government/About_LSC/reporting_system.txt
technical/government/About_LSC/State_Planning_Report.txt
technical/government/About_LSC/Protocol_Regarding_Access.txt
technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
technical/government/About_LSC/conference_highlights.txt
technical/government/About_LSC/State_Planning_Special_Report.txt
```

This command is finding all the contents within the `./technical/government/About_LSC` directory that is of the file type. This is particularly useful for finding just the files within `./technical/government/About_LSC` and excluding the folders if you wanted to quickly list just its subfiles.

Sources used: the `man` command

Option 4 - `find -ls`:

Example 1:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/911report -ls
11277333        0 drwxr-xr-x   19 jeremysu         staff                 608 Feb  8 14:18 technical/911report
11277341      520 -rwxr-xr-x    1 jeremysu         staff              265912 Feb  8 14:18 technical/911report/chapter-13.4.txt
11277342      576 -rwxr-xr-x    1 jeremysu         staff              290993 Feb  8 14:18 technical/911report/chapter-13.5.txt
11277338      176 -rwxr-xr-x    1 jeremysu         staff               89854 Feb  8 14:18 technical/911report/chapter-13.1.txt
11277339      216 -rwxr-xr-x    1 jeremysu         staff              110568 Feb  8 14:18 technical/911report/chapter-13.2.txt
11277340      296 -rwxr-xr-x    1 jeremysu         staff              150467 Feb  8 14:18 technical/911report/chapter-13.3.txt
11277344      520 -rwxr-xr-x    1 jeremysu         staff              264360 Feb  8 14:18 technical/911report/chapter-3.txt
11277343      160 -rwxr-xr-x    1 jeremysu         staff               79803 Feb  8 14:18 technical/911report/chapter-2.txt
11277334      232 -rwxr-xr-x    1 jeremysu         staff              118656 Feb  8 14:18 technical/911report/chapter-1.txt
11277345      200 -rwxr-xr-x    1 jeremysu         staff               99008 Feb  8 14:18 technical/911report/chapter-5.txt
11277346      296 -rwxr-xr-x    1 jeremysu         staff              149063 Feb  8 14:18 technical/911report/chapter-6.txt
11277347      256 -rwxr-xr-x    1 jeremysu         staff              128370 Feb  8 14:18 technical/911report/chapter-7.txt
11277349      296 -rwxr-xr-x    1 jeremysu         staff              149644 Feb  8 14:18 technical/911report/chapter-9.txt
11277348      168 -rwxr-xr-x    1 jeremysu         staff               84835 Feb  8 14:18 technical/911report/chapter-8.txt
11277350       24 -rwxr-xr-x    1 jeremysu         staff                9332 Feb  8 14:18 technical/911report/preface.txt
11277337      256 -rwxr-xr-x    1 jeremysu         staff              127587 Feb  8 14:18 technical/911report/chapter-12.txt
11277335       96 -rwxr-xr-x    1 jeremysu         staff               47307 Feb  8 14:18 technical/911report/chapter-10.txt
11277336      144 -rwxr-xr-x    1 jeremysu         staff               71151 Feb  8 14:18 technical/911report/chapter-11.txt
```

This command is taking all the contents within `./technical/911report` and displaying a list of data for each one. It lists data like size in bytes, last modification time, pathname, inode number, etc. This is particularly useful if you want to quickly display the properties of all the contents within `./technical/911report`.

Example 2:

```
jeremysu@Jeremys-MacBook-Pro docsearch % find technical/government/Env_Prot_Agen -ls  
11278213        0 drwxr-xr-x   16 jeremysu         staff                 512 Feb  8 14:18 technical/government/Env_Prot_Agen
11278222      384 -rwxr-xr-x    1 jeremysu         staff              195851 Feb  8 14:18 technical/government/Env_Prot_Agen/multi102902.txt
11278225      104 -rwxr-xr-x    1 jeremysu         staff               52552 Feb  8 14:18 technical/government/Env_Prot_Agen/section-by-section_summary.txt
11278221      128 -rwxr-xr-x    1 jeremysu         staff               62387 Feb  8 14:18 technical/government/Env_Prot_Agen/jeffordslieberm.txt
11278220       72 -rwxr-xr-x    1 jeremysu         staff               32919 Feb  8 14:18 technical/government/Env_Prot_Agen/final.txt
11278218      160 -rwxr-xr-x    1 jeremysu         staff               77895 Feb  8 14:18 technical/government/Env_Prot_Agen/ctf7-10.txt
11278217      152 -rwxr-xr-x    1 jeremysu         staff               73979 Feb  8 14:18 technical/government/Env_Prot_Agen/ctf1-6.txt
11278224       40 -rwxr-xr-x    1 jeremysu         staff               19798 Feb  8 14:18 technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
11278219      264 -rwxr-xr-x    1 jeremysu         staff              131959 Feb  8 14:18 technical/government/Env_Prot_Agen/ctm4-10.txt
11278214       40 -rwxr-xr-x    1 jeremysu         staff               19836 Feb  8 14:18 technical/government/Env_Prot_Agen/1-3_meth_901.txt
11278215      144 -rwxr-xr-x    1 jeremysu         staff               72635 Feb  8 14:18 technical/government/Env_Prot_Agen/atx1-6.txt
11278227       32 -rwxr-xr-x    1 jeremysu         staff               13279 Feb  8 14:18 technical/government/Env_Prot_Agen/tech_sectiong.txt
11278216      480 -rwxr-xr-x    1 jeremysu         staff              243860 Feb  8 14:18 technical/government/Env_Prot_Agen/bill.txt
11278223       64 -rwxr-xr-x    1 jeremysu         staff               31404 Feb  8 14:18 technical/government/Env_Prot_Agen/nov1.txt
11278226      352 -rwxr-xr-x    1 jeremysu         staff              178501 Feb  8 14:18 technical/government/Env_Prot_Agen/tech_adden.txt
```

This command is taking all the contents within `./technical/government/Env_Prot_Agen` and displaying a list of data for each one. It lists data like each file's size, last modification time, pathname, inode number, etc. This would be particularly useful if you want to quickly display the properties of all the contents within `./technical/government/Env_Prot_Agen`.

Sources used: the `man` command
