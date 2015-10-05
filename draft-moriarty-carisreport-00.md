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

Coordination between CSIRTS and attack response mitigation efforts
Distributed Denial of Service and Botnet researchers, vendors, and operators
Infrastructure: DNS and RIR providers and researchers
Trust and Privacy with the exchange of potentially sensitive information
IAB wrap up for architecture next steps
There were a few items that stood out to me from the workshop (more to be included in the formal report):

The participants are interested in expanded information on the resources and assistance offered by the RIRs and DNS providers.  Participants are going to define what is needed with follow through on next steps.

Another reoccurring theme was the lack of knowledge by the community of basic security principles such as ingress and egress filtering explained in {{RFC2728}} BCP38.  The CSIRTS, operators, and vendors of attack mitigation tools found this particularly frustrating.  As a result, follow up activities may include determining if security guidance BCPs require updates or to determine whether there are opportunities to educate on these basic principles already documented by the IETF.

After the workshop, the Internet Society hosted a three and a half hour boat tour through the canals of Berlin, offering additional time for collaboration among participants.  One of the lively discussions was the need for better transports for information exchange.  As the author of Real-time Inter-network Defense (RID), I agree.  RID was written more than 10 years ago and while the patterns established still show promise, there are updated solutions being worked on.  One such solution is in the IETF DOTS working group, that has an approach similar to RID with updated formats and protocols to meet the demands of todays DDoS attacks.  While TAXII (another transport option) is just in transition to OASIS, its base is similar to RID in its use of SOAP-like messaging, which will likely prevent it from scaling to the demands of the Internet.  Vendors also cited several interoperability challenges in TAXII.  Alternatively, XMPP-Grid has been proposed in the IETF SACM working group and it offers promise as the data exchange protocol.  XMPP inherently meets the requirements for today’s information exchanges with features such as publish/subscribe, federation, and use of a control channel.  XMPP-grid is taking off too with at least 10 current vendors using open source code in their products with several more planning to add support.  Review and discussion of this draft would be helpful.  REST was also brought up as a needed interface.  IETF’s MILE has a draft detailing a common RESTful interface (ROLIE) that could be used with any data format and may be of interest.  It would be good to hear from the community if this draft is of value to assist with that gap and it would be resurrected if helpful.



The Need for Standardization   {#need}
----------------------------

If STuPiD is so easy to deploy, why standardize on it?
First of all, STuPiD server implementations will be done by
other people than the clients making use of the service.
Clearly communicating between these communities is a good
idea, in particular if there are security considerations.

Having one standard form of STuPiD service instead of one
specific to each kind of client also creates an incentive
for optimized implementations.

Finally, where STuPiD becomes part of a client standard
(such as a potential extension to XMPP's in-band byte-stream
protocol as hinted in {{xmpp}}), it is a good
thing if STuPiD is already defined.

Hence, this document focuses on the definition of the STuPiD
service itself, tries to make this as general as possible
without increasing complexity or cost and leaves the details
of any client standards to future documents.


Basic Protocol Operation   {#ops}
========================

The STuPiD protocol will typically be used with application
instances that first attempt to obtain connectivity using
mechanisms similar to those described in the STUN
specification {{RFC5389}}.  However, with STuPiD,
STUN is not really needed for TCP, as was demonstrated in
previous STUN-like implementations {{STUNT}}.
Instead, STuPiD (like {{STUNT}}) provides a
simple Web service that
echoes the remote address and port of an incoming HTTP
request; in most cases, this is enough to get the job done.

In case no connection can be established with this simple
STUN(T)-like mechanism, a TURN-like relay is needed as a final
fall-back.
The STuPiD protocol supports this, but solely provides a way
for the data to be
relayed.  STuPiD relies on an out-of-band channel to notify
the peer whenever new data is available (synchronization signal).
See {{xmpp}} for one likely example of such an
out-of-band channel.
(Note that the out-of-band channel may have a much lower
throughput than the STuPiD relay channel — this is exactly
the case in the example provided in {{xmpp}},
where the out-of-band channel is typically throughput-limited
to on the order of a few kilobits per second.)

By designing the STuPiD web service in such a way that it can
be implemented by a simple PHP script such as that presented
in {{impl}}, it is easy to deploy by those who
need the STuPiD services.
The combination of the low-throughput out-of-band channel for
synchronization and the STuPiD web service for bulk data
relaying is somewhat silly but gets the job done.

The STuPiD data relay is implemented as follows (see {{figops}}):

1. Peer A, the source of the data to be relayed, stores a chunk of
   data at the STuPiD server using an opaque identifier, the "chunk
   identifier". How that chunk identifier is chosen is local to Peer
   A; it could be composed of a random session id and a sequence number.

2. Peer A notifies the receiver of the data, Peer
   B, that a new data chunk is available, specifying the URI needed
   for retrieval.
   This notification is provided through an out-out-band channel.
   (As an optimization for multiple consecutive transfers, A might
   inform B once of a constant prefix of that URI and only send a
   varying part such as a sequence number in each notification —
   this is something to be decided in the client-client notification
   protocol.)

3. Peer B retrieves the data from the STuPiD server using the URI
   provided by Peer A.

Note that the data transfer mechanism is one-way, i.e. to send
data in the other direction as well, Peer B needs to perform
the same steps using a STuPiD server at the same or a
different location.

~~~~~~~~~~


        STuPiD   ```````````````````````````````,
        Script   <----------------------------. ,
                                              | ,
          ^ ,                                 | ,
          | ,                                 | ,
    (1)   | ,                                 | ,  (3)
    POST  | ,                                 | ,  GET
          | ,                                 | ,
          | v                                 | v

        Peer A   ----------------------->   Peer B
                           (2)
                       out-of-band
                       Notification
~~~~~~~~~~
{: #figops title="STuPiD Protocol Operation"}


Protocol Definition
===================

Terminology          {#Terminology}
-----------
In this document, the key words "MUST", "MUST NOT", "REQUIRED",
"SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY",
and "OPTIONAL" are to be interpreted as described in BCP 14, RFC 2119
{{RFC2119}} and indicate requirement levels for compliant STuPiD
implementations.


Discovering External IP Address and Port
----------------------------------------

A client may discover its external IP address and the port
required for port prediction by performing a HTTP GET
request to a STuPiD server. The STuPiD server MUST reply
with the remote address and remote port in the following
format:

host ":" port

where 'host' and 'port' are defined as in {{RFC3986}}.


Storing Data
------------

Data chunks are stored using the POST request of HTTP. The
STuPiD server MUST support one URI parameter which is passed
as query-string:

'chid':  A unique ID identifying the data chunk to be stored.
The ID SHOULD be chosen from the characters of the base64url
set {{RFC4648}}.

The payload of the POST request MUST be the data to be
stored. The 'Content-Type' SHOULD be
'application/octet-stream', although a STuPiD server
implementation SHOULD simply ignore the 'Content-Type' as a
client implementation may be restricted and may not able to
specify a specific 'Content-Type'.  (E.g., in certain cases,
the peer may be limited to sending the data as
multipart-form-encoded — still, the data is stored as a
byte stream.)

STuPiD servers may reject data chunks that are larger than
some predefined limit.
This maximum size in bytes of each data chunk is RECOMMENDED
to be 65536 or more.

As HTTP already provides data transparency,
the data chunk SHOULD NOT be encoded using Base64 or any
other data transparency mechanism; in any case, the STuPiD
server will not attempt to decode the chunk.

The sender MUST wait for the HTTP response before
going on to notify the receiver.


Notification
------------

The sender notifies the receiver of the data chunk by passing
via an out-of-band channel (which is not part of the STuPiD
protocol):

The full URL from which the data chunk can be retrieved,
i.e. the same URL that was used to store the data chunk,
including the chunk ID parameter.

The exact notification mechanism over the out-of-band channel
and the definition of a session is dependent on the
out-of-band channel.  See {{xmpp}} for one
example of such an out-of-band channel.


Retrieving Data
---------------

The notified peer retrieves the data chunk using a GET request
with the URL supplied by the sender. The STuPiD server MUST
set the 'Content-Type' of the returned body to
'application/octet-stream'.


Implementation Notes
====================

A STuPiD server implementation SHOULD delete stored data some
time after it was stored. It is RECOMMENDED not to delete the
data before five minutes have elapsed after it was stored.
Different client protocols will have different reactions to
data that have been deleted prematurely and cannot be
retrieved by the notified peer; this may be as trivial as
packet loss or it may cause a reliable byte-stream to fail
({{impl}}).
(TODO: It may be useful to provide some hints in the storing
POST request.)

STuPiD clients should aggregate data in order to minimize the
number of requests to the STuPiD server per second.
The specific aggregation method chosen depends on the data
rate required (and the maximum chunk size), the latency
requirements, and the application semantics.

Clearly, it is up to the implementation to decide how the data
chunks are actually stored.  A sufficiently silly STuPiD server
implementation might for instance use a MySQL database.


Security Considerations
=======================

The security objectives of STuPiD are to be as secure as if
NAT traversal had succeeded, i.e., an on-path attacker can
overhear and fake messages, but an off-path attacker cannot.
If a higher level of security is desired, it should be
provided on top of the data relayed by STuPiD, e.g. by using
XTLS {{I-D.meyer-xmpp-e2e-encryption}}.

Much of the security of STuPiD is based on the assumption that
an off-path attacker cannot guess the chunk identifiers.  A
suitable source of randomness {{RFC4086}} should
be used to generate at least a sufficiently large part of the
chunk identifiers (e.g., the chunk identifier could be a hard
to guess prefix followed by a serial number).

To protect the STuPiD server against denial of service and
possibly some forms of theft of service, it is RECOMMENDED
that the POST side of the STuPiD server be protected by some
form of authentication such as HTTP authentication.  There is
little need to protect the GET side.

--- back


Examples  {#xmp}
========

This appendix provides some examples of the STuPiD protocol operation.

~~~~~~~~~~
   Request:

      GET /stupid.php HTTP/1.0
      User-Agent: Example/1.11.4
      Accept: */*
      Host: example.org
      Connection: Keep-Alive

   Response:

      HTTP/1.1 200 OK
      Date: Sun, 05 Jul 2009 00:30:37 GMT
      Server: Apache/2.2
      Cache-Control: no-cache, must-revalidate
      Expires: Sat, 26 Jul 1997 05:00:00 GMT
      Vary: Accept-Encoding
      Content-Length: 17
      Keep-Alive: timeout=1, max=400
      Connection: Keep-Alive
      Content-Type: application/octet-stream

      192.0.2.239:36654
~~~~~~~~~~
{: #figxmpdisco title="Discovering External IP Address and Port"}

~~~~~~~~~~
   Request:

      POST /stupid.php?chid=i781hf64-0 HTTP/1.0
      User-Agent: Example/1.11.4
      Accept: */*
      Host: example.org
      Connection: Keep-Alive
      Content-Type: application/octet-stream
      Content-Length: 11

      Hello World

   Response:

      HTTP/1.1 200 OK
      Date: Sun, 05 Jul 2009 00:20:34 GMT
      Server: Apache/2.2
      Cache-Control: no-cache, must-revalidate
      Expires: Sat, 26 Jul 1997 05:00:00 GMT
      Vary: Accept-Encoding
      Content-Length: 0
      Keep-Alive: timeout=1, max=400
      Connection: Keep-Alive
      Content-Type: application/octet-stream
~~~~~~~~~~
{: #figxmpstore title="Storing Data"}

~~~~~~~~~~
   Request:

      GET /stupid.php?chid=i781hf64-0 HTTP/1.0
      User-Agent: Example/1.11.4
      Accept: */*
      Host: example.org
      Connection: Keep-Alive

   Response:

      HTTP/1.1 200 OK
      Date: Sun, 05 Jul 2009 00:21:29 GMT
      Server: Apache/2.2
      Cache-Control: no-cache, must-revalidate
      Expires: Sat, 26 Jul 1997 05:00:00 GMT
      Vary: Accept-Encoding
      Content-Length: 11
      Keep-Alive: timeout=1, max=400
      Connection: Keep-Alive
      Content-Type: application/octet-stream

      Hello World
~~~~~~~~~~
{: #figxmpretr title="Retrieving Data"}


Sample Implementation     {#impl}
=====================

~~~~~~~~~~
<?php
header("Cache-Control: no-cache, must-revalidate");
header("Expires: Sat, 26 Jul 1997 05:00:00 GMT");
header("Content-Type: application/octet-stream");

mysql_connect(localhost, "username", "password");
mysql_select_db("stupid");

$chid = mysql_real_escape_string($_GET["chid"]);

if ($_SERVER["REQUEST_METHOD"] == "GET") {
   if (empty($chid)) {
      echo $_SERVER["REMOTE_ADDR"] . ":" . $_SERVER["REMOTE_PORT"];
   } elseif ($result = mysql_query("SELECT `data` FROM `Data` " .
                         "WHERE `chid` = '$chid'")) {
      if ($row = mysql_fetch_array($result, MYSQL_ASSOC)) {
         echo base64_decode($row["data"]);
      } else {
         header("HTTP/1.0 404 Not Found");
      }
      mysql_free_result($result);
   } else {
      header("HTTP/1.0 404 Not Found");
   }
} elseif ($_SERVER["REQUEST_METHOD"] == "POST") {
   if (empty($chid)) {
      header("HTTP/1.0 404 Not Found");
   } else {
      mysql_query("DELETE FROM `Data` " .
                  "WHERE `timestamp` < DATE_SUB(NOW(), INTERVAL 5 MINUTE)");
      $data = base64_encode(file_get_contents("php://input"));
      if (!mysql_query("INSERT INTO `Data` (`chid`, `data`) " .
                       "VALUES ('$chid', '$data')")) {
         header("HTTP/1.0 403 Bad Request");
      }
   }
} else {
   header("HTTP/1.0 405 Method Not Allowed");
   header("Allow: GET, HEAD, POST");
}
mysql_close();
?>
~~~~~~~~~~
{: #figimpl title="STuPiD Sample Implementation"}


Using XMPP as Out-Of-Band Channel  {#xmpp}
=================================

XMPP {{I-D.ietf-xmpp-3920bis}} is a good choice for
an out-of-band channel.

The notification protocol is closely modeled after XMPP's
In-Band Bytestreams (IBB, see
http://xmpp.org/extensions/xep-0047.html). Just replace the
namespace and insert the STuPiD Retrieval URI instead of the
actual Base64 encoded data, see {{figxmpnots}}.
(Note that the current proposal redundantly sends a sid and a
seq as well as the chid composed of these two; it may be
possible to optimize this, possibly sending the constant prefix
of the URI once at bytestream creation time.)

Notifications MUST be processed in the order they are
received. If an out-of-sequence notification is received for a
particular session (determined by checking the 'seq' attribute),
then this indicates that a notification has been lost. The
recipient MUST NOT process such an out-of-sequence notification,
nor any that follow it within the same session; instead, the
recipient MUST consider the session invalid.  (Adapted from
http://xmpp.org/extensions/xep-0047.html#send)

Of course, other methods can be used for setup and teardown, such as Jingle
(see http://xmpp.org/extensions/xep-0261.html).

~~~~~~~~~~
      <iq from='romeo@montague.net/orchard'
          id='jn3h8g65'
          to='juliet@capulet.com/balcony'
          type='set'>
        <open xmlns='urn:xmpp:tmp:stupid'
              block-size='65536'
              sid='i781hf64'
              stanza='iq'/>
      </iq>
~~~~~~~~~~
{: #figxmpcri title="Creating a Bytestream: Initiator requests session"}


~~~~~~~~~~
      <iq from='juliet@capulet.com/balcony'
          id='jn3h8g65'
          to='romeo@montague.net/orchard'
          type='result'/>
~~~~~~~~~~
{: #figxmpcrr title="Creating a Bytestream: Responder accepts session"}



~~~~~~~~~~
      <iq from='romeo@montague.net/orchard'
          id='kr91n475'
          to='juliet@capulet.com/balcony'
          type='set'>
        <data xmlns='urn:xmpp:tmp:stupid'
              seq='0'
              sid='i781hf64'
              url='http://example.org/stupid.php?chid=i781hf64-0'/>
      </iq>
~~~~~~~~~~
{: #figxmpnots title="Sending Notifications: Notification in an IQ stanza"}

~~~~~~~~~~
      <iq from='juliet@capulet.com/balcony'
          id='kr91n475'
          to='romeo@montague.net/orchard'
          type='result'/>
~~~~~~~~~~
{: #figxmpnota title="Sending Notifications: Acknowledging notification using IQ"}

~~~~~~~~~~
      <iq from='romeo@montague.net/orchard'
          id='us71g45j'
          to='juliet@capulet.com/balcony'
          type='set'>
        <close xmlns='urn:xmpp:tmp:stupid'
               sid='i781hf64'/>
      </iq>
~~~~~~~~~~
{: #figxmpclor title="Closing the Bytestream: Request"}

~~~~~~~~~~
      <iq from='juliet@capulet.com/balcony'
          id='us71g45j'
          to='romeo@montague.net/orchard'
          type='result'/>
~~~~~~~~~~
{: #figxmpclos title="Closing the Bytestream: Success response"}

