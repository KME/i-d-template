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

Panel groups: {#panels}
----------------------------

1. Coordination between CSIRTS and attack response mitigation efforts
2. Distributed Denial of Service and Botnet researchers, vendors, and operators
3. Infrastructure: DNS and RIR providers and researchers
4. Trust and Privacy with the exchange of potentially sensitive information
5. IAB wrap up for architecture next steps

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



{: #figxmpclos title="Closing the Bytestream: Success response"}

