---
layout: post
title: "Shrinking a Volume Taking Too Long?"
category: tut
tag: windows
---
 
Ever been in a situation where while shrinking your hard disk via Windows Partition Manager takes far to long? With that irritating blue circle and it's never ending rotation and a grey titlebar? You think, "Ditch this shit! I don't wanna partition my drive. Gimme the cancel button!" But where is the cancel button? Nope, not on the current screen. Then you either wait long enough for the process to end or you simply force shutdown.

---

###The Reason

The reason is trivial but not apparent. So, what happens is that the Windows partition manager, by default starts off the **Disk Defragmenter** while partitioning (w00t?). Yup! If you open the **Disk Defragmenter** window in the background, you can even see the steps.

<a href="{{ site.baseurl }}public/img/tut/too-long/1.png"><img src="{{ site.baseurl }}public/img/tut/too-long/1.png"></a>

The above image shows the moment when you right-click on the disk you want to partition and the Defragmenter window analyses your disk. The **Shrink Volume** window won't come up until it's 100% complete.

<a href="{{ site.baseurl }}public/img/tut/too-long/2.png"><img src="{{ site.baseurl }}public/img/tut/too-long/2.png"></a>

This image is of that moment when you finally choose the shrink size and the process starts. This is the process that takes ages. Here, what happens is that the Defragmenter first analyses the disk (again!), defragments it and then the actual shrinking happens. You can see all this happening in the Defragmenter window.

---

###How to Stop it?

Well, now at least you can rest in peace and watch the whole thing happening when your window has frozen. But what if you don't have enough time and you want to cancel?
Simple! Just stop the Defragment process. And that stops your shrinking process too, without causing any harm to your PC. Here's what it looks like:

<a href="{{ site.baseurl }}public/img/tut/too-long/3.png"><img src="{{ site.baseurl }}public/img/tut/too-long/3.png"></a>

So, it's not because Windows goes bonkers while shrinking that this happens, it's because of a sub-process.