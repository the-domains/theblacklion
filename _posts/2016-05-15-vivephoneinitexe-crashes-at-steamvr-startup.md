---
inFeed: true
hasPage: true
inNav: false
inLanguage: null
keywords: []
description: 'Since I first tried to pair my iPhone with my HTC Vive I got the vivephoneinit.exe crash - also pairing did not work. But thanks to hurzhurz on reddit, I was finally able to get rid of this error and managed to pair iPhone and Vive.'
datePublished: '2016-05-15T07:26:56.031Z'
dateModified: '2016-05-15T07:26:44.734Z'
title: vivephoneinit.exe crashes at steamvr startup
author: []
sourcePath: _posts/2016-05-15-vivephoneinitexe-crashes-at-steamvr-startup.md
authors: []
publisher:
  name: null
  domain: null
  url: null
  favicon: null
starred: false
url: vivephoneinitexe-crashes-at-steamvr-startup/index.html
_type: Article

---
# vivephoneinit.exe crashes at steamvr startup

Since I first tried to pair my iPhone with my HTC Vive I got the vivephoneinit.exe crash - also pairing did not work. But thanks to [hurzhurz on reddit][0], I was finally able to get rid of this error and managed to pair iPhone and Vive.

Basically the issue is simply that vivephoneinit wants to write a debug log into a file it is not allowed to. I can tell you this implementation was done wrong on multiple levels and will hopefully be addresses in a future patch. But until then, this workaround will resolve the issue. You will need admin rights to do that.

1) Use widows explorer to go to the directory C:\\Program Files (x86)\\ViveSetup\\PCClient\\web\\apps\\phone\\

2) Right click on the folder vivephoneinit and select properties.
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/a55f8d73-4940-484e-b39e-5dc3637a4a2e.png)

(I promise I will switch my Windows to English for future screenshots, but for now, I have not set it up yet.)

3) In the properties pop-up go t the tab security, select the group users (Benutzer in German) and click on Edit... (Bearbeiten... in German).
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/92e52976-9f37-4121-b4b1-abc0c7c67ad9.png)

4) Then check the checkbox at Modify and Write (should autoselected once you checked Modify) and click OK.
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/16c245a3-5de1-41bf-be08-82b74f6221d1.png)

That should do it. Now, vivephoneinit.exe should not crash anymore and paring with your phone should work as well. Thanks again to [hurzhurz][1] for figuring that out.

[0]: https://www.reddit.com/r/Vive/comments/4h1jym/vivephoneinitexe_crashes_at_steamvr_startup/
[1]: https://www.reddit.com/user/hurzhurz