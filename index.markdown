---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: main
---
I was previously a health psychology researcher at UCSF and UC Berkeley. I remained interested in health care and decided to complete pre-requisites for Physical Therapy school. I was accepted into the UCSF/SFSU DPT program. However, after receiving the financial aid package and making several dynamic spreadsheets, I decided to pivot to software engineering instead. I look forward to creating tools to support others in their daily lives and well-being in languages such as Python, Javascript, HTML, and others.

When I am not programming, I enjoy yoga, (a large variety of) martial arts, tea/tea culture, long conversations, and snuggling my two dogs. 

[✨ Resume ✨](/assets/ResumeAileenTran.pdf)

{% for post in paginator.posts %}
<article class="post">
  {% if post.img %}
    <a class="post-thumbnail" style="background-image: url({{"/assets/img/" | prepend: site.baseurl | append : post.img}})" href="{{post.url | prepend: site.baseurl}}"></a>
  {% else %}
  {% endif %}
  <div class="post-content">
    <h2 class="post-title"><a href="{{post.url | prepend: site.baseurl}}">{{post.title}}</a></h2>
    <p>{{ post.content | strip_html | truncatewords: 15 }}</p>
    <span class="post-date">{{post.date | date: '%Y, %b %d'}}&nbsp;&nbsp;&nbsp;—&nbsp;</span>
    <span class="post-words">{% capture words %}{{ post.content | number_of_words }}{% endcapture %}{% unless words contains "-" %}{{ words | plus: 250 | divided_by: 250 | append: " minute read" }}{% endunless %}</span>
  </div>
</article>
{% endfor %}

{% include pagination.html %}
