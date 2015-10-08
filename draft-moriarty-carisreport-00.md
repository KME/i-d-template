---
title: Coordinating Attack Response at Internet Scale (CARIS) Workshop Report
abbrev: CARIS
docname: draft-moriarty-carisreport-00
date: 2015-10-05
category: info

ipr: trust200902
area: General
workgroup: Network
keyword: Internet-Draft

stand_alone: yes
pi: [toc, sortrefs, symrefs]

author:
 -
    ins: K. Moriarty
    name: Kathleen M. Moriarty
    organization: EMC Corporation
    street: 176 South Street
    city: Hopkinton, MA
    country: United States
    email: Kathleen.Moriarty@emc.com
 -

normative:
  RFC2119:

informative:
  RFC2827:

--- abstract

The Internet Architecture Board (IAB) and the Internet Society (ISOC) hosted day-long Coordinating Attack Response at Internet Scale (CARIS) workshop took place 18 June 2015 in coordination with the Forum for Incident Response and Security Teams (FIRST) Conference in Berlin. The workshop included members of the FIRST community, attack response working group representatives (APWG, ACDC, etc.), network & security operators, RIR representatives, researchers, vendors, and representatives from standards communities. Key goals of the workshop were to improve mutual awareness, understanding, and coordination among the diverse participating organizations. The workshop also aimed at providing greater awareness of existing efforts to mitigate specific types of attacks, and greater understanding of the options others have to collaborate and engage with these efforts.

--- middle

Introduction        {#problems}
============

The Internet Architecture Board (IAB) and the Internet Society (ISOC) hosted day-long Coordinating Attack Response at Internet Scale (CARIS) workshop took place 18 June 2015 in coordination with the Forum for Incident Response and Security Teams (FIRST) Conference in Berlin. The workshop included members of the FIRST community, attack response working group representatives (APWG, ACDC, etc.), network & security operators, RIR representatives, researchers, vendors, and representatives from standards communities. Key goals of the workshop were to improve mutual awareness, understanding, and coordination among the diverse participating organizations. The workshop also aimed at providing greater awareness of existing efforts to mitigate specific types of attacks, and greater understanding of the options others have to collaborate and engage with these efforts.

The day-long workshop included a mix of invited and selected speakers with opportunities to collaborate throughout, taking full advantage of the tremendous value of having these diverse communities with common goals in one room. There were approximately 50 participants engaged in the CARIS workshop from the 25 papers received and additional 20 template submissions.  The template submissions will be maintained at the Internet Society web site and as a result of the workshop will be amended to provide additional value to the computer security incident response teams (CSIRTs) and attack response communities/operators on their information exchange activities.  The CARIS participants found the template submissions to be very useful in coordinating their future attack mitigation efforts.  Nothing like this had previously been done — this is open for the global community and hosted in a neutral location.  All submissions are linked from the agenda.

The workshop talks and panels involved full participation from attendees who were required to read all other submissions.  The panels were organized to spur conversation between specific groups to see if we could further progress towards more efficient and effective attack mitigation efforts.  See paper and blog series for additional information on possible approaches to accomplish more effective attack response and information exchanges with methods that require fewer analysts.

The workshop was run under Chatham House Rule as a result of the often sensitive information involved with incident response.  As such, there was no recording, but minutes were taken and used to aid int he generation of this report.  Comments will not be attributed to any particular attendee, nor will organizations be named in association with any discussion topics that were not made public through submission templates or papers by the submitter and organization.

Sessions and Panel Groups: {#panels}
------------------------------------

1. Stage Setting and Goals of the Workshop
2. Coordination between CSIRTs and attack response mitigation efforts
2. Scaling response to DDoS and Botnets effectively and safely
3. Infrastructure: DNS and RIR providers and researchers
4. Trust and Privacy with the exchange of potentially sensitive information
5. IAB wrap up for architecture next steps

Coordination between CSIRTs and Attack Response Mitigation Efforts
------------------------------------------------------------------
The first panel session on Coordination between CSIRTs and attack mitigation efforts included representatives from several organizations that submitted templates exchange/attack type mitigation efforts.  This panel was purposefully a cross section of organizations attending to see if there were opportunities to collaborate and improve efficiency and better scale attack mitigation.  The panelists described their efforts with the following questions in mind:
  1. Describe your use case?
  2. Where they are focusing?
  3. How can others engage with them?
  4. Who participates?

For each of the following organizations, additional information can be found in their template submissions:
https://internetsociety2.wufoo.com/reports/caris-workshop-template-submissions/
The following summaries are to be read in context of the workshop and not as stand alone descriptions for each organization as these summaries are a result of the workshop discussions.

While ENISA provides support for the community in the form of education, training and collaboration on security and attack mitigation, it does not offer a service for attack response or mitigation.

The APWG offered examples of operator driven exchanges focused on specific use cases that involve hundreds of participating organizations daily.  The APWG operates a data clearinghouse and provides infrastructure to support meaningful data exchanges and maintains a current set of data through these interactions.  More can be learned on the APWG web site in addition to their template submission.

Ren-ISAC represents an interesting operational model that scales well through automation, exchanging actionalable information between 500 universities automatically implementing controls.  They leverge a small number of analysts to accomplish the task of protecting many universities, understanding the scarcity of resources, since many universities cannot respond in real-time without this automation.  The key to the sucess of their project is actualization with tools that allow organizations to make use of data operationally. They are currently working to develop open-source tools to track metrics formally.

CERT.br is the Brazilian CERT and they have made impressive progress in a short amount of time.  CERT.br is the national focal point for incident reporting, collect and dissemination of threat and attack trend information in Brazil. CERT.br works to increase awareness and incident-handling capabilities in country as well as assiting to establish new CSIRTs.  In addition to providing training and awareness campaigns, they distribute honeypots and have a primary focus on network monitoring.  CERT.br requires active participation to collaborate and exchange data with them.

MyCERT's mission is to address security concerns of Malaysian Internet users and reduce the probability of successful attacks.  They have been operational since 1997. MyCERT is responsible for incident handling on intrusions, identifity theft, and handling DDoS attacks, etc. MyCERT assists with CSIRT incident help in Malaysia, provides malware research, and technical coordination. In addition to incident response and coordination activities, MyCERT members provide talks, training, as well as local and regional security exercises.  MyCERT also provides incident alerts, advisories on vulnerabilities, breaches, etc. 

CERT/CC has been operational work since 1998 on an international and national scale. They have long been known for their software vulnerability work and the national vulnerability database in the US (CVEs) and informing organizations of vulnerabilities.  CERT/CC helps to coordinate between vendors and researchers for improved collaborations.  CERT/CC assists with guidance on plans to deal with the aftermath, risk assessment pratice, bug bounties, and other incident related areas. 

Highlighted points from the panel discussion:
1. Passive survellience has impacted incident response activities
2. Government involvement in exchange eforts hasn't been productive, lots of talk without useful exchanges
3. More interest in cunsuming feeds of information rather than sharing information
4. Ego has been a big issue as is reputation concerns for data shared (impact your own reputation) or with data received.  
5. There is a perception of weakness around organizations who do share attack information in some regions.
6. Sharing alone doesn't help, must lead to operational ROI
7. Language barriers has been an issue for some national CSIRTs
8. Sharing too much information leads to capacity and resource issues for receiving organizations.  Organizations directly receiving feeds often results in mis-interpretation of the data and thinking they are under attack when it is not the case. Operational models preferred where there is an impact from exchanges and efficiencies ganied using a small number of analysts to impact many.
9. Privacy regulations restricting some from sahring IP address information has had an impact on effectiveness of exchanges.  ENISA is currently running a study on this impact (raised by several attendees).
10. Too many efforts are using data just for blocking attacks and not operational mitigation and elimination as part of incident response.  Note: Operational efforts stand out in that they do eliminate threats and update data warehouses.
11. Involvement of vendors is needed to better scale attack response.  This is not seen as a need by all groups, just some sharing groups with an operational focus looking for improved efficiency to leverge the small number of analysts.  Analysts are a limited resource in this technical area of expertise.
12. Enterprises don't want another security box as they don't have the resources to manage them, so invoving vendors doesn't mean deploying more equipment, but improving automated controls and elimination of threats where possible.
False positives are still an issue, which can be problematic for some automation activities.

Scaling Response to DDoS and Botnets Effectively and Safely
-----------------------------------------------------------

The intorduction talk provided interesting history on Distributed Denial of Service (DDoS) attacks and the evolution of Botnets as well as methods to combat these threats.  The paper by Dave Dittrich is available to learn more on the history, this section of the report will focus on the workshop discussion in an effort to benefit from the discussions on how to better scale response to these threats.

Key points from the discussion:
1. Of the attack types discussed, DDoS and Botnets appear to be the furthest along in terms of efficient and efective response.  Other effort can learn from these afforts.  There has not been any interaction between these two attack types that may benefit from information exchange tied to remediation activities since Botnets can be the source of DDoS attacks.
2. There is a disparity between short-term mitigation goals and actual eradication of DDoS and Botnet threats. The questions was raised: how do we normalize the same data in different ways to serve different goals? In other words, DDoS traffic is often the result of Botnets, but the data is not shared between the service providers and vendors responding to DDoS threats and those actively mitigating and erradicating Botnets.
2. There are adhoc trust groups within the OpSec community today, CRAG is one example.
3. Filtering and triage is an issue, but this is a solveable problem.
4. The IETF DOTS working group effort was discussed and compared to a previous effort, Real-time Inter-network defense (RID) {{RFC6545}}.  It was stated that the two are similar, excpet DOTS makes use of current data formats and protocols and has the support of multiple DDoS vendors.  One of the goals of DOTS is to have this solution be the "glue" between vendors to communicate shared data using standard formats and protcols developed in open source tools.
5. The IETF I2NSF effort was discussed to see if there is a way to leverage infrastructure to combat DDoS attacks.
6. Vendors discussed existing capabilities for DDoS mitigation, while sharing exchange groups discussed their mitigation activities around Botnets (see paper submissions).
7. Trust and reputation of data sources is still a concern.
8. One of the exchange groups has a goal of "automated takedowns" for Botnets.  However, they think they will always have a need for manual intervention.
9. The need for multiple levels of trust seemed to be prevalent among those participating in the panel discussion.  Intelligence agencies erode trust (this was also mentioned in the first panel in terms of surveilance activities from governments).
10. Although trust was discussed in this panel and there are needs, it was noted that trust is not as big a barrier in these attack spaces likely due to the operational experience of participants.


DNS & RIRs: Attack Response and Mitigation
------------------------------------------
This session was a shift from other sessions in the day as the panelists were infrastructure providers for those combating attack response.  This session was of interest to see how attack and incident responders could better collaborate with DNS and RIRs.  These groups have not interacted in the past and it was interesting to see the collaboration opportunities since the workshop patricipants rely on these services to do their jobs.  From the panelists perspective, DNS and RIRs are separate worlds, where they spend a lot of time trying to educate policymakers and how they work together to make the Internet work.

Key discussion points:
1. The use of passive DNS in attack mitigation was described and how it can be usful to organizations.
2. RIRs discussed the data they maintain and provide for those interested including worldwide BGP update data and root DNS server data.  These data sets are avaiable to share with researchers and could be of interest to those working on attack response.  The current way the data is made available does not scale and ideas were discussed in the workshop to improve the scalability if this does become a tapped on resource.
3. Some of the global RIRs already actively coordinate with incident responders in their region.  In some cases they do facilitate information sharing as well as provide education and training.  Data shared out by RIRs is anonymized.
4. A concern was raised on overlapping eforts and a request was made for the IETF and ISOC to pay attention to this and help.  This workshop was one step toward that in bringing together this diverse community.  The participants wish to see this type of even repeated for future cross area collaboration between the diverse set of groups that often only meet within their silo.  
5. Standards for APIs to access data consistently from RIRs and scoring methods were discussed as possible ways to scale trust.  Still questions were raised as to how this might be possible.  One might receive unverifiable data about a network. They may be able to verify the source's identity, verify route origins, but won't be able to verify provenance of data.


Trust Privacy and Data Markings Panel
-------------------------------------



Workshop Themes {#themes}
-------------------------
Better scaling attack response through improvements to the efficiency and effectiveness of information exchanges. 
1. Data exchanges should not be just for the purpose of creating blacklists that could be redundant efforts.
2. Involving service providers and vendors to better coordinate and scale response is key.

Information security practitioners are a scare resource.
1. Training and education was discussed to improve this gap, both to train information security professionals and others in IT on basic network {{RFC2728}}and system hygiene. 
2. Leveraging resources to better scale response, using fewer resources is critical.


Next Steps {#nextsteps}
-----------------------

RIR and DNS Provider Resources
------------------------------

The participants are interested in expanded information on the resources and assistance offered by the RIRs and DNS providers.  Participants are going to define what is needed with follow through on next steps.

Education and Guidance
----------------------

Another reoccurring theme was the lack of knowledge by the community of basic security principles such as ingress and egress filtering explained in {{RFC2728}} BCP38.  The CSIRTS, operators, and vendors of attack mitigation tools found this particularly frustrating.  As a result, follow up activities may include determining if security guidance BCPs require updates or to determine whether there are opportunities to educate on these basic principles already documented by the IETF.

Transport Options
-----------------

One of the lively discussions was the need for better transports for information exchange.  Real-time Inter-network Defense (RID) was written more than 10 years ago.  While the patterns established in RID still show promise, there are updated solutions being worked on.  One such solution is in the IETF DOTS working group, that has an approach similar to RID with updated formats and protocols to meet the demands of todays DDoS attacks.  While TAXII (another transport option) is just in transition to OASIS, its base is similar to RID in its use of SOAP-like messaging, which will likely prevent it from scaling to the demands of the Internet.  Vendors also cited several interoperability challenges in TAXII in discussions.  Alternatively, XMPP-Grid has been proposed in the IETF SACM working group and it offers promise as the data exchange protocol.  XMPP inherently meets the requirements for today’s information exchanges with features such as publish/subscribe, federation, and use of a control channel.  XMPP-grid is gaining traction with at least 10 vendors using it in their products with several more planning to add support.  Review and discussion of this draft would be helpful as it transitions to the MILE working group as an outcome of the workshop.  REST was also brought up as a needed interface because of the low barrier to use a RESTful interface, one only needs a browser.  IETF’s MILE has a draft detailing a common RESTful interface (ROLIE) that could be used with any data format and may be of interest. 

Updated Template for Information Exchange Groups
-----------------------------------------------
One of the submission options was for organizations actively exchanging data to submit a template form describing their work to reduce attacks.  The CSIRTs, in particular, liked having access to this information in a neutral location like the Internet Society.  However, they would like to see changes to the form to ensure it's usefulness.  There was a desire to have this used by additional exchange groups, creating a living library to better understand how to become a member, benefit frm, or contribute to the success of the attack response and CSIRT exchange platforms.



Security Considerations
=======================

The CARIS workshop was focused on security and methods to improve the effectiveness and efficiency of attack response to enable better scaling.  The report is focused on the summary and outcomes to improve security.  As such, no additional considerations are needed in this section.

--- back

Acknowledgements
================
Thank you to the members of the program committee (in alphabetical order) for your efforts to make this workshop possible and a productive session with cross area expertise.
Matthew Ford, Internet Society, UK
Ted Hardie, Google
Joe Hildebrand, Cisco, USA
Eliot Lear, Cisco, Switzerland
Kathleen M. Moriarty, EMC Corporation, USA
Andrew Sullivan, Dyn
Brian Trammell, ETH Zurich, Switzerland

Thank you to the CARIS workshop sponsors!
  o FIRST provided a room and excellent facilities in partnership with their annual conference in Berlin.
  o The Internet Society hosted the social event, a boat ride through the canals of Berlin.
  o EMC Corporation provided lunch, snacks and coffee throughout the day to keep us going.


