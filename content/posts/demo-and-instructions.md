---
title: "Demo and installation instructions"
date: 2018-02-05T00:00:02+01:00
draft: false
discussionId: demo-and-instructions
---


Talkyard is an embedded commenting system for Hugo and other static site generators.
It's [open source](https://github.com/debiki/talkyard/); you can install it for free on your server.
There's serverless [hosting](https://www.talkyard.io/blog-comments) — no ads, no tracking.

Demo video:

<iframe src="https://player.vimeo.com/video/249611399" width="684" height="385" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<br>
This website is a static Hugo blog, with Talkyard comments — look at the bottom of the pages.
Talkyard is forum software too, with chat and question-answers features:
you can create a community for your website, integrated with the blog comments.

<a href="/posts/like-about-hugo">Here's a demo Hugo discussion.</a>

<a href="https://www.kajmagnus.blog/new-embedded-comments">Longer demo discussion</a> (the one in the video).
<br>
<br>

### Quick test if this is for you

Two steps for trying out Talkyard, without signing up or getting a server:

1. Add this where you want the commetns to appear, for example, in
   `./themes/YOUR_THEME_NAME/layouts/_default/single.html`,
   in a new `<section>` after the blog post `.Content`:

        <script>talkyardServerUrl='{{ .Site.Params.talkyardServerUrl }}';</script>
        <script async defer src="{{ .Site.Params.talkyardScriptUrl | default "https://c1.ty-cdn.net/-/talkyard-comments.min.js" }}"></script>
        <!-- You can specify a per page discussion id on the next line, if your URLs might change. -->
        <div class="talkyard-comments" data-discussion-id="{{ .Params.discussionId }}" style="margin-top: 45px;">
        <noscript>Please enable Javascript to view comments.</noscript>
        <p style="margin-top: 25px; opacity: 0.9">Comments powered by
        <a href="https://www.talkyard.io">Talkyard</a>.</p>
        </div>

1. Add this config value in the `[params]` section, and use a demo comments account:

        // In config.toml:
        [params]       <——— note, must be this section
        talkyardServerUrl = "https://comments-demo.talkyard.io"



Now, look at the comment section that should appear below the blog posts. You can post test comments **but** they'll disappear later on, some day (because you use a demo test account).


### Real installation

Do steps 1 and 2 above, then go to <https://www.talkyard.io/plans> and choose Blog Comments.
Follow the instructions — and, in `config.toml`, change the `talkyardServerUrl` value
to the address of your new Talkyard blog comments site,
e.g. `https://comments-for-your-blog.talkyard.net`.

You should also add a frontmatter `discussionId: per-discussion-id` to each blog post / article,
so you can change the URL to the blog post, without the discussion disappearing.

You can ask for help in the [support forum][support-cat] over at www.Talkyard.io.

[support-cat]: https://www.talkyard.io/forum/latest/support
[ideas-cat]: https://www.talkyard.io/forum/latest/ideas

