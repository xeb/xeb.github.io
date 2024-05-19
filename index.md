---
layout: landing
type: landing
---

<div class="home">
<p>
The following are topics about my life, spirtuality, software engineering, artificial intelligence, accelerationism, journal entries, and other thoughts. I am writing this <a href="https://youtube.com/shorts/zlT_aPrf8KU?si=VSVS2QeiHz13eRWn">for me</a>.
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

