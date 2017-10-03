---
layout: default
title: Configure Network Authentication to Accept Other Agency PIV/CAC cards
collection: userconfig
permalink: userconfig/2_networkauth.md/
---

If you want to allow other agency users to authenticate to your agency network, this article will help you configure your agency's Active Directory to support other agency issued PIV/CAC card authentication.

## Import Agency Specific PIV Issuer Certificates

The agency specific PIV Issuer certificates can be found on the [FPKI Crawler](https://fpki-graph.fpki-lab.gov/crawler/){target="_blank"}_ website. You will find the certificate listed by agencies in the table 'Certificate Files Grouped by Type'. Once you locate the agency, you can download the certificates and the path to COMMON in p7b format.
{target="_blank"}_.

Import the certificates in the Windows [NTAuth Trust Store](https://piv.idmanagement.gov/networkconfig/trustedroots/){target="_blank"}_.

## Add Agency UPN Suffix

In order to trust the PIV/CAC cards from another agency, you have to [add the UPN suffix](https://technet.microsoft.com/en-us/library/cc772007(v=ws.11).aspx){target="_blank"}_ of that agency in your agencies Active Directory Domains and Trusts.

To add UPN suffixes

1. Open Active Directory Domains and Trusts. To open Active Directory Domains and Trusts, click Start , click Administrative Tools, and then click Active Directory Domains and Trusts .
2. In the console tree, right-click Active Directory Domains and Trusts, and then click Properties.
3. On the UPN Suffixes tab, type an alternative UPN suffix for the forest, and then click Add.


## Account Linking of Other Agency Users

When a user authenticates with another agency PIV/CAC card, the credential of that user may not match the account created in the Active Directory user setup in your agency. There are multiple ways to match that PIV/CAC card owner to the Active Directory account.