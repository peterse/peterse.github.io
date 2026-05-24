---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
---

I am a quantum scientist at Xanadu studying quantum machine learning. I was previously a postdoc and PhD student at University of Waterloo studying machine learning for error correction and other topics at the intersection of quantum information and learning theory.


<h2> Select publications </h2>
 - _Trapped by simplicity: When Transformers fail to learn from noisy features._ (<a href="https://openreview.net/forum?id=n5bPL58uMC">ICLR 2026</a>)
 - _Sample importance for data-driven decoding._ <a href="https://arxiv.org/abs/2505.22741">2505.22741</a> (2025). 
 - _Generalization despite overfitting in quantum machine learning models._ <a href="https://quantum-journal.org/papers/q-2023-12-20-1210/">Quantum</a> 7 (2023).
 - _Qubit assignment using time reversal._ <a href="https://journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.3.040333">PRX Quantum</a> (2022).

Complete list: <a href="https://scholar.google.com/citations?user=JLvD4RkAAAAJ&hl=en&oi=ao">Google Scholar</a>.
<hr style="width:95%;color:gray;margin:auto;margin-bottom:.5cm;margin-top:0.5cm;" >
<h2>{{ page.list_title | default: "Other writing/research" }}</h2>
<ul class="post-list">
    {%- for post in site.posts -%}
    <li margin=10px>
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <span class="post-meta">{{ post.date | date: date_format }}</span>
    <h4><a href="{{ post.url | relative_url }}">
        {{ post.title | escape }}
        </a></h4>
    {%- if site.show_excerpts -%}
        {{ post.excerpt }}
    {%- endif -%}
    </li>
    {%- endfor -%}
</ul>
<hr style="width:95%;color:gray;margin:auto;margin-bottom:.5cm;margin-top:0.5cm;" >

