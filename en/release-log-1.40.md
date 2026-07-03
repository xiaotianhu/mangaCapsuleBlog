---
id: release-log-1.40
title: Manga Capsule 1.40 Update Released~
excerpt: 1.40 brings many new features~
category: Public
readTime: 1 min read
date: 2026年05月20日
tags:
  - 资源
  - 漫画
  - 工具
image: 'https://mangacapsule.com/images/blog-release-log.jpg'
author:
  name: Rainy
  avatar: 'https://mangacapsule.com/images/rainyavatar.jpg'
  role: Developer
---
Recently I made something fun. We added an AI coloring feature to our manga reader 「漫画胶囊」.

Here's the story. I'm actually a longtime anime fan myself. Growing up, I read black-and-white manga over and over and never thought there was anything wrong with it. Dragon Ball, Slam Dunk, Yu Yu Hakusho — flipping through page by page, the black-and-white lines were the entire world. Back then, I thought manga was supposed to be black and white; adding colors would actually take away some of the flavor.

But recently, while scrolling through Xiaohongshu, I saw people using AI to color manga pages, and it looked pretty cool.

Lately, other readers have been doing AI coloring too; we researched and tried many online coloring models, but the results were all underwhelming. We've always believed that if a feature can't be done well, it's better not to do it at all. Chasing after a massive list of features will only result in doing nothing well.

That was until we discovered the GPT2Image model — the results are absolutely explosive. It's basically on par with official artwork. That feeling is just amazing.

Then I started thinking: can we just stuff this directly into the reader? Not having to open another app, export, upload, wait forever, then import back. Just in the reader, long-press and the colors appear. The manga reading experience shouldn't be interrupted — it should be as natural as turning to the next page.

So we got to work, spent some time on it, and finally made it happen.

Now in the reader, long-press or two-finger tap, and you can AI color the current page directly from the menu. Not just manga pages — you can also upload photos from your gallery to color. For example, if you drew a line art and want to see what it looks like colored, or you found a black-and-white illustration and want to add some color to it for fun, you can throw it in and try.

But honestly, this feature is extremely costly.

I'm not talking about development cost — I'm talking about the computational cost of running the model for each coloring. As you know, AI coloring services on the market are either subscription-based or charge per image, and they're not cheap. This time we're paying out of pocket for everyone to try it out, temporarily limited to 5 images per person. Let's see how it goes.

Some people might ask, only 5? What can you even do with that?

Honestly, I'm not sure if 5 is enough. But I know one thing: if I don't let people try it at all, what's the point of making this feature? Let's get it out there first and see what feedback we get. If there's genuine demand, there's a feedback option in Settings-AI Coloring — feel free to reach out. Whether to increase the limit or come up with a more flexible plan, we'll try our best to accommodate.

So our plan is to release it first, let everyone play with it, and see how the feedback goes.



Now, while we're at it, we also threw together a "Nine-Grid Generator."

This was actually inspired by something I saw on Jike last week. Some guy posted a nine-grid of his manga collection covers, and the comments were full of people asking how they did it. I thought about it — it's just a排列组合 thing — so we might as well build it into the app.

You select a few books, generate a nine-grid with one tap, and share it to WeChat Moments or Xiaohongshu. That neatly arranged manga shelf cover image just looks so satisfying.

I think there's inherently an urge to "show off" when it comes to manga collections. When you finish a series you love, or finally gather all the physical books of a series you've been collecting for a while, that desire to share — it's the same as collecting figures, finishing a LEGO set, or completing a card deck. It's not bragging; it's a simple joy of wanting to connect with fellow fans.

One of the biggest regrets of the digital age is that this "sense of collection" has been weakened. Your bookshelf exists on your hard drive, on your NAS — no one else can see it. Thousands of manga sitting on your hard drive might as well not exist.

The nine-grid, in a way, helps bring back that sense of collection a little bit. And I'll tell you secretly, the generated images actually look pretty good. The covers are neatly arranged, the color matching is pleasing to the eye. I've already posted two on my WeChat Moments, and the likes are several times higher than usual.

Feel free to share and help us spread the word~



Now let me talk about an update I think is pretty important: search.

We haven't had search before, and honestly, it's not because we're lazy — it's just really hard to do. Manga files are all local or on NAS, doing full-text indexing would be too performance-heavy, but not having it gets us criticized. Every time I see someone in the comments say "how come there's no search," I just quietly note it down...

This time we went with a compromise: search the cache. Meaning only directories you've already visited can be searched.

I know this isn't the most perfect solution. But my own usage pattern is like this — I have hundreds of series stored on my NAS, but the ones I actually flip through repeatedly are only those ten or so: One Piece, Jujutsu Kaisen, Chainsaw Man, over and over. Those directories have definitely been visited, so searching the cache basically covers them. If you're the type who randomly opens a new series every time, this really won't cover you — I'll figure something out later.

If you try it and feel it's not enough, feel free to give us feedback. We'll see if we can make search more perfect down the road.

We also switched to a new approach for handling local PDF long images.

Some users reported that certain PDF landscape cross-page long images had a poor experience — the reader was missing features, the experience was inconsistent. I researched this for a while and found that the original rendering solution took shortcuts with super-long images, compromising on functionality. This time we switched to a new rendering pipeline, and after testing it feels much better — all the features are added, the experience is more consistent.

Friends who read manga with PDF can update and try it — the experience should improve noticeably. If there are still issues, feel free to come yell at me, I'll keep fixing it.



Besides these bigger updates, there are also some minor fixes.
A few small bugs in the reader have been fixed — the occasional page-turn crash, zoom ratio abnormality, those should all be resolved now. The issue where the shelf wouldn't refresh after importing has also been fixed, and progress sync has been slightly optimized — cross-device reading should be more stable now. Also fixed some EPUB file sorting issues and infinite loop problems.

Honestly, every time we update and fix bugs, I have mixed feelings.

On one hand, I feel bad for users who encountered these issues. On the other hand, after fixing them, I think — yeah, this app got a little better again. Maybe this is the daily life of an indie developer: always on the road of patching and fixing, always thinking it's not good enough, but always moving forward.



Back to 「漫画胶囊」 itself — if you haven't tried it yet, let me give you a quick intro.
It's a local manga reader on iOS, supporting EPUB, ZIP, RAR, PDF, MOBI, CBR, CBZ, AZW3 and other mainstream formats — basically any manga file you have can be opened. Its biggest feature is streaming reading: store your manga on NAS or cloud drive, no need to wait for everything to download, tap to open and you can read immediately, like a video — instant start.

It supports quite a few cloud drives too: Aliyun Drive, Baidu Netdisk, iCloud, Google Drive, Dropbox all have it. There's also WebDAV and SMB protocols — NAS users should be pretty familiar. I have a NAS at home with a few hundred gigabytes of manga stored. Before, every time I wanted to read I'd have to download first, and I'd wait until my scalp went numb... Now I just tap and read — this feeling is so goddamn exciting.

For reading experience, Japanese manga, American comics, and webtoons each have their own dedicated adaptation mode. Page-turn animations have three options: slide, scroll, and simulation. There are also some small features I really love: intelligent page splitting, which automatically splits dual-page scans into single pages for phone reading; merge next page, which temporarily combines wide-spreads for viewing; long-press zoom, super useful when you can't read the text on small screens. Auto-cropping white margins is also my own must-have — some scanned manga have ridiculously huge white margins, and after cropping, the whole page instantly looks cleaner.

Oh, and AI upscaling — it uses an on-device Waifu2X model, runs directly on the device, no network needed. Put in old, blurry manga resources and the quality can jump up a level. I have an old scan of City Hunter with resolution so low that zooming in makes text unreadable. After running AI upscaling, the lines are clearer, text becomes readable — it's like restoring an old photo. I'm pretty proud that it works quite well even on old devices like iPad Mini 5.

Actually, sometimes I wonder what makes a reader "good." Does ComicShare have many features? Yes. Does KaDa support many formats? Yes. But I always feel like something's missing — maybe it's that feeling of "opening it and just feeling comfortable." An app's interaction, animation, color scheme, font, spacing — these things seem insignificant individually, but put together they form a complete user experience. We might actually spend more time on this than on writing feature code.

One step at a time, no rush.

Okay, that's about it for this update.
AI coloring, nine-grid generator, search, PDF long image optimization, plus some bug fixes. If you're using 「漫画胶囊」, remember to update to the latest version and try it out. If you think it's good, please give us a five-star review — that really means a lot to us indie developers.

Everyone, remember to update and give us a five-star review. I read every single review carefully. Grateful.


Since you made it this far, if you think it's good, feel free to like, share, and tap the three-button combo. If you want to get updates first, you can also star me⭐～

