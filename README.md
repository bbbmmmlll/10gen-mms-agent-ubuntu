    Copyright 2012 PayPerks Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
 
        http://www.apache.org/licenses/LICENSE-2.0
 
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
 


10gen-mms-agent-ubuntu
======================

Tools for running mms-agent on Ubuntu


Presently we have:

## Upstart Script
* This is known to work at least on Ubuntu 12's upstart, version 1.5.
* Drop into /etc/init to have mms-agent started on boot and restarted whenever required.  Logging goes to /var/log/upstart/ or to /var/log/syslog.
* Assumes a dedicated user has been setup to run the agent

## Ubuntu Packaging Files
Drop the contents of the latest & greatest mms-agent into opt/mongo-mms-agent/ and then you can build them into a package with:

    dpkg-deb --build mongo-mms-agent_1.0-6

It's best to leave your api & secret keys out and add them upon installation.

Creates a user/group 'mongomms' to run the agent as.  UID/GID 510.

Potential improvements:
* Install settings.py to /etc and have the daemon look for it there
* Prompt on attented dpkg installations for api & secret keys 
* Version with debian-friendly init script


