---
layout: default
title: "HCL Domino RSS Feed Generator Template"
nav_order: 1
description: "HCL Domino RSS Feed Generator Templatey"
has_children: false
---
<h1>HCL Domino RSS Feed Generator Template</h1>
This database contains a collection of agents and script-libraries designed to produce RSS feeds

<details close markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

![Screenshot RSS Feed Generator](assets/images/png/screenshot.png)

## Info

Property | Value
---|---
Filename | rss_generator.ntf
Templatename | RSS Generator Template
Template version | 9.0
Signed by | Open Source Template/Domino Development
Optimized for | Notes Client 

## Domino RSS Syndication

This database contains a collection of agents and script-libraries designed to produce RSS feeds of any Domino view, including but not limited to:
* E-mail, Calendar, and Contact entries from a user's database
* Corporate contacts
* Discussions

The agents and script-libraries in this database can be copied to a user's mail database (for individual use) or left in this database as a shared application for all users.  As a shared application, special lookup functions find the current webuser's mail database and only create RSS XML for that user.  

## Features

1. Homepage redirects user to "AvailableFeeds" service which advertises all feeds listed in the RSS Feed Definitions view.
2. Only allows user-based RSS feeds when server security is set to "Basic" authentication mode and Anonymous is set to "no access" in this database's ACL.
3. Has an internal function to create iCalendar or vCard objects when the <enclosure> tag is associated with an RSS item
   * iCalendar and vCard objects can be retrieved by examining the "url" property of the <enclosure> tag
   * Since most RSS readers do not process enclosure tags, sending a link to the iCalendar or vCard object reduces the amount of unnecessary data delivered to the client.
   * Visit http://www.rsscalendar.com/rss/  to see similar feeds
<enclosure> tags are used by Podcasts to advertise an audio or video file

1. Contacts and Calendar feeds should be advertised as "ordered lists". This means that RSS readers are supposed to remove items that are no longer in the list.  A common example of an "ordered list" is a top-10 feed of best selling books.  The order and content may change on a weekly or monthly basis, and you wouldn't want overlapping #1 books!
2. Has a view to collect and advertise "External Web Documents" as RSS items.  You might use this to aggregate important company documents like Human Resources PDF forms, Corporate policies, and other documents that may not be part of a Domino view.
