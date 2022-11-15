---
layout: landing
type: landing
---

<div class="home">
<p>
The following are various topics about software engineering, artificial intelligence, journal entries, and other technical findings. My hope is that the below content is useful or interesting to others. However, my expectation is to keep this blog for my own sake. Writing is thinking.
</p>
<p>&nbsp;</p>
<ul class="post-list">
    {% for post in site.posts limit:20 %}
        <li>
            <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
            <h2>
                <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
            </h2>
        </li>
    {% endfor %}
</ul>

<p>My old school blog is at <a href="https://kockerbeck.blogspot.com">kockerbeck.blogspot.com</a>.
</p>

</div>

