---
layout: post
title:  "A video call that is just a link"
date:   2026-11-05 18:30:00 +0000
categories: computing
---
{% include analytics.html %}

I have added video calls to [bep46-webrtc](https://github.com/mrmartin/bep46-webrtc), my project for web pages that live in the browsers of the people reading them. The call works the same way: there is no server in the middle, only a link.

[Start a call]({{ "/video-call.html" | relative_url }}){: target="_blank" rel="noopener"}

You open the page, you see your own camera and microphone level, and there is one button. Pressing it gives you a link. Whoever opens the link is in the call. Nothing about the link is stored anywhere, so the same link works next Tuesday, and the Tuesday after that, even if nobody used it in between. There are no accounts and nothing to install; a current Chrome or Edge is enough.

[![The call page: the active speaker on the stage, the others as thumbnails, the link to share at the top]({{ "/images/bep46-call.png" | relative_url }})]({{ "/images/bep46-call.png" | relative_url }})
*Three browsers in one call. The cameras are synthetic: this is the test harness, which runs real headless browsers with generated video.*

## What is different from Zoom or Meet

A normal video service receives everybody's video on its servers and sends each participant a mix. Here the video goes from browser to browser. Every participant sends two versions of their camera, a full one and a small thumbnail, and audio. You only receive what you look at: the person on the stage in full quality, the thumbnails of the others in low quality, and the voices of at most three people, the ones who have spoken most recently. Nobody wants to hear more than three people at once anyway. You can pin anyone to the stage and force whom you watch or listen to.

The part I like most is that everyone who watches also helps carry the stream. When someone's upload is used up, the next viewer is served by an existing viewer, which passes the encoded frames on without decoding them. Small trees of relays form on their own and repair themselves when people leave. On the test machine a frame takes between 15 and 150 milliseconds from camera to screen, which is what a conversation needs.

What is still needed is a way for browsers to find each other. That is a WebSocket tracker, the same one the pages use, and it only ever sees an opaque hash of the link and the WebRTC introductions, never the call. Participants authenticate each other with a periodic handshake that proves they know the link; the video itself is not signed, so no latency is added on the way.

## Limits

This is a hobby, so the honest list: Chromium browsers are the target, because they have the WebCodecs API that makes relaying without re-encoding possible. Two people who are both behind strict NATs may not be able to connect directly, in which case the call routes around them through someone else. The relays can see the video they forward, since they are participants in the same call. And a tab has to stay open; there is no one to hold the call for you when everyone leaves, which is also the point.

The page above is a self-contained copy hosted on this site. The code, the design and the tests are in the [repository](https://github.com/mrmartin/bep46-webrtc){: target="_blank" rel="noopener"}, where the same page is served from the project's own site once it is on its main branch.
