### [2024‐02‐27 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9002%E2%80%9027-TAPI-Meeting-Minutes)

Reviewed contribution

  + https://github.com/OpenNetworkingFoundation/TAPI/blob/tapi-team-activities/TAPI-TEAM-ACTIVITIES/ContributionsForDiscussions/TAPI_2.5.0_Review_26_02_2024.pptx

Andrea presents the slides
  - the ongoing review of version 2.5.0 is highlighting bugs and need for rapid improvements
  - so far two regressions have been found, more urgent to be solved
    + through a TAPI 2.5.0 Release Note, recommending how to patch (e.g. name/value pairs etc.)
    + Roshan asks to check if regressions affect also 2.4.0/1 versions (answer is yes).
  - Other enhancements are presented
    + some only affecting the RIA, with OTSiMCA Connectivity Service as top priority
  - Nigel: the enhancements for not yet defined UCs could be left as proprietary ones
  - Agreed to prepare for the next week a proposal for the plan of corrections/enhancements
    + Anders will bring back the plan to MUST, for evaluation.

### [2024‐03‐12 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9003%E2%80%9012-TAPI-Meeting-Minutes)

2.5.0 Review: plan for corrections and enhancements
   + Andrea shows the used process for bugs/regressions, applicable to any TAPI delivery:
     1) an issue is opened with the description of the issue
	 2) a patch is drafted
	    - the patches are defined in separate Yang modules, as augments constructs
        - this allows to maintain unaltered the originally delivered Yang modules
   + Issues and patches:
     - https://github.com/OpenNetworkingFoundation/TAPI/issues/568
	   https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/blob/tapi-2_5_0-fixes/TAPI-FIXES/YANG-Patches-Normative/tapi-patch1-photonic-media.yang
	 - https://github.com/OpenNetworkingFoundation/TAPI/issues/569
       https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/blob/tapi-2_5_0-fixes/TAPI-FIXES/YANG-Patches-Normative/tapi-patch1-notification.yang
   + Nigel and Andrea resp. R&Ds approve the patches
   + Esther has presented the TAPI 2.5.0 patches to TIP MUST
     - Esther will inform TAPI team in case a dedicated meeting will be called

 Proposal to close all issues older than 2023
- Andrea shows the almost 100 open issues, almost all being pretty old
  + proposal is to close all issues older than 2023
  + agreed, but for the issues opened by Service Providers - for further review
  + the other issues will be closed adding a comment like:
    - "This issue has been closed due to the lack of activity for more than one year.
       Please reopen it if follow up is necessary."

### [2024‐03‐19 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9003%E2%80%9019-TAPI-Meeting-Minutes)

2.5.0 Review: plan for corrections and enhancements
 - Esther reports the perplexities regarding the currently proposed management of patches for TAPI version 2.5.0
   + Why these two branches have been defined?
     - https://github.com/OpenNetworkingFoundation/TAPI/tree/tapi-team-activities and
     - https://github.com/OpenNetworkingFoundation/TAPI/tree/tapi-2_5_0-fixes
   + Normally it is delivered a new version including the corrections, no need of additional branches.
   + Nigel explains that we need to keep separate threads from main "https://github.com/OpenNetworkingFoundation/TAPI" for
     - activities related to TAPI 2.5.0 (patches), i.e. that will never be part of any release different from TAPI 2.5.0
     - activities independent to releases (contributions, meeting minutes, etc.), i.e. that will never be part of any TAPI release
 - A possible compromise would be to create a TAPI 2.5.1 delivery composed by:
   + TAPI 2.5.0 contents, and
   + TAPI 2.5.0 patches
 - Agreed that there are pros and cons:
   + clearer identification of a TAPI package
   + proliferation of deliveries with very similar content	   
- For further discussion - also necessary the opinion of TIP

Proposal to close all issues older than 2023
- Agreed, but for the issues opened by Service Providers - for further review
- The other issues will be closed adding this comment:
  + "This issue has been closed due to the lack of activity for more than one year.
     Please reopen it if follow up is necessary."

### [2024‐03‐26 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9003%E2%80%9026-TAPI-Meeting-Minutes)

2.5.0 Review: plan for corrections and enhancements

- Esther confirms the perplexities regarding the currently proposed management of patches for TAPI version 2.5.0
   + Anders indicates that also Telia is preferring a 2.5.1 version
   + Arturo thinks it is more clear a 2.5.1 version
     - Andrea will create the new delivery, based on
	   + https://github.com/OpenNetworkingFoundation/TAPI/tree/tapi-2_5_0-fixes
	   + where the defined patches are considered as agreed
   + Nigel, TIP then shall refer to "latest 2.5.x version", rather than to 2.5.0

Proposal to close all issues older than 2023

- Andrea shows the few remaining open issues
  + https://github.com/OpenNetworkingFoundation/TAPI/issues (old link)
  + https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/issues
- All the other issues have been closed, as agreed last week
  + Note that the closed issues are still available

### [2024‐04‐02 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9004%E2%80%9002-TAPI-Meeting-Minutes)

- Andrea shows the draft 2.5.1 release based on
  + https://github.com/OpenNetworkingFoundation/TAPI/tree/tapi-2_5_0-fixes (old link)
  + https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/tree/tapi-2_5_0-fixes
- Proposal is agreed - Andrea will deliver 2.5.1
  + Esther confirms the general agreement in TIP MUST regarding TAPI 2.5.1 for patches

### [2024‐04‐09 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9004%E2%80%9009-TAPI-Meeting-Minutes)

- Andrea shows the draft 2.5.1 release
- Proposal is agreed with some amendments in the text
  + Andrea delivers
    -  https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/releases/tag/2.5.1

