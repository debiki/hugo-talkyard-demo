---
title: "Demo and installation instructions"
date: 2018-02-05T00:00:02+01:00
draft: false
discussionId: demo-and-instructions
---


Talkyard is a new embedded commenting system for Hugo and other static site generators.
It's [open source](https://github.com/debiki/ed-server/) so you can install it for free on your own server.
There's [hosting](https://www.talkyard.io) for €3, if you don't want to maintain your own server.
No ads, no tracking.

Demo video:

<iframe src="https://player.vimeo.com/video/249611399" width="684" height="385" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<br>
This website is a static Hugo blog, with Talkyard comments below each blog post — look at the bottom of the pages.
Talkyard is forum software too, with chat and question-answers features —
so you can create a community for your website, integrated with the blog comments.

<a href="/posts/like-about-hugo">Here's a demo Hugo discussion.</a>

<a href="https://www.kajmagnus.blog/new-embedded-comments">Longer demo discussion (the one in the video).</a>
<br>
<br>

### Quick test if this is for you

Here're two quick steps for you to try out Talkyard on your own site, without signing up or installing anything:

1. Add this where you want the commetns to appear, for example, in
   `./themes/YOUR_THEME_NAME/layouts/_default/single.html`,
   in a new `<section>` after the blog post `.Content`:

        <script>talkyardServerUrl='{{ .Site.Params.talkyardServerUrl }}';</script>
        <script async defer src="{{ .Site.Params.talkyardScriptUrl | default "https://cdn.talkyard.net/-/talkyard-comments.min.js" }}"></script>
        <!-- You can specify a per page discussion id on the next line, if your URLs might change. -->
        <div class="talkyard-comments" data-discussion-id="{{ .Params.discussionId }}" style="margin-top: 45px;">
        <noscript>Please enable Javascript to view comments.</noscript>
        <p style="margin-top: 25px; opacity: 0.9">Comments powered by
        <a href="https://www.talkyard.io">Talkyard</a>.</p>
        </div>

1. Add this config value, and use a dummy test comments account:

        // In config.toml:
        [params]
        talkyardServerUrl = "https://comments-demo.talkyard.io"
        ...


Now, look at the comment section that should appear below the blog posts. You can post test comments **but** they'll disappear later on, some day (because you use a demo test account).

Are you satisfied with how it looks? If not, please tell us/me: <https://www.talkyard.io/forum/latest/support>; maybe we can make it look better.


### Real installation instructions

Do steps 1 and 2 above, then go to <https://www.talkyard.io>, click Create Community and choose Blog Comments.
Follow the instructions — and, in `config.toml`, change the `talkyardServerUrl` value
to the address of your new Talkyard blog comments site,
e.g. `https://comments-for-your-blog.talkyard.net`.

You should also add a frontmatter `discussionId: per-discussion-id` to each blog post / article,
so you can change the URL to the blog post, without the discussion disappearing.

Again, note that Talkyard also is forum software, with chat and Q&A features — you can create a community for your website, integrated with the blog comments.

You can ask for help in [the support forum][support-cat], and [suggest ideas][ideas-cat].
Or post a comment below on this page (test comments are fine too).

[support-cat]: https://www.talkyard.io/forum/latest/support
[ideas-cat]: https://www.talkyard.io/forum/latest/ideas

