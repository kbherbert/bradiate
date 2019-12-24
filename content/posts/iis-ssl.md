---
title: 'How to Setup a SSL Secure Server (HTTPS) in Local IIS'
date: 2019-12-24
draft: false
tags:
- .net
---

Sometimes it is necessary to test your local code using a secured protocol (https). All browsers have the capability to interact with secured web servers using the SSL protocol.

Fortunately, if you are developing on a .NET stack, IIS makes this relatively easy by using self-signed certificates. This brief tutorial assumes that you have a good understanding of IIS and .NET development.

  1. Open IIS and select your root machine/server instance within the ‘Connections’ pane on the left
  2. Within the ‘Features View’ pane, find and duble-click on the ‘Server Certificates’ icon
  3. Within the ‘Actions’ pane on the far right, select ‘Create Self-Signed Certificate’
  4. Give your certificate any friendly name (it doesn’t matter what), then complete the Wizard

Now that you have created a certificate for your local server, you will just need to assign it to the site(s) you are working with.

  1. Select your Site within the ‘Connections’ pane on the left
  2. Open the ‘Edit Bindings’ window by either right-clicking the Site, or selecting ‘Bindings’ within the ‘Actions’ pane
  3. You likely already have at least one binding to port ’80’ with a type of ‘http’. Add another binding and select ‘https’ as the type, which should automatically set your port to ‘443’. Within the ‘SSL certificate’ dropdown, select the certificate you in the steps above.

Just restart your site, open a browser and you should be able to navigate to https//localhost.