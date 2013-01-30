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

    dpkg-deb --build mongo-mms-agent_1.5.3-0

It's best to leave your api & secret keys out and add them upon installation.

Creates a user/group 'mongomms' to run the agent as.  UID/GID 510.

Potential improvements:
* Install settings.py to /etc and have the daemon look for it there
* Prompt on attented dpkg installations for api & secret keys 
* Version with debian-friendly init script

##History
* Originally created by Alex Hewson (alex@payperks.com, https://github.com/alexmbird)

##License

Copyright (c) 2012, PayPerks, Inc.
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:
* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of PayPerks, Inc. nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
