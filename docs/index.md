---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
---

I am a quantum scientist at Xanadu studying quantum machine learning. I was previously a postdoc and PhD student at University of Waterloo studying machine learning for error correction and topics at the intersection of quantum information and  learning theory. I also do quantum computing Q&A as <a href="https://quantumcomputing.stackexchange.com/users/1939/forky40">@forky40</a>.


<h2> Select publications </h2>
 - _Sample importance for data-driven decoding._ <a href="https://arxiv.org/abs/2505.22741
">2505.22741</a> (2025). 
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

<!-- <h2> Conference talks / Group seminars</h2> -->


 <!-- 16. <span style="font-size:small;"> INRIA (Paris).  Talk: Sample importance for Data‑Driven Decoding. July 23, 2025. </span>
 15. <span style="font-size:small;"> Eisert group seminar. Talk: Sample importance for Data‑Driven Decoding.  July 16, 2025. </span>
 14. <span style="font-size:small;"> ML4QT workshop (Heilbronn). Talk: Sample importance for Data‑Driven Decoding.  July 8, 2025. </span>
 13. <span style="font-size:small;"> Eisert group QML seminar. Talk: Bounds and Guarantees for learning and entanglement.  May 16, 2024. </span>
 12. <span style="font-size:small;"> Quantum Techniques in Machine Learning 2023. Talk: Learning guarantees from entanglement manipulation.  Nov 20, 2023. </span>
 11. <span style="font-size:small;"> University of Ottawa quantum information seminar. Talk: Some learning bounds and guarantees for quantum-quantum hypothesis testing.  Oct 13, 2023. </span>
 9. <span style="font-size:small;"> Vector institute QML seminar. Talk: Generalization despite overfitting in quantum machine learning models. Feb. 15, 2023 </span>
 8. <span style="font-size:small;"> Centre for Quantum Technologies QML seminar. Talk: Generalization despite overfitting in quantum machine learning models <a href="https://www.youtube.com/watch?v=0qa2YNeOrkQ">link</a>. Jan 6, 2023. </span>
 7. <span style="font-size:small;"> Quantum Techniques in Machine learning 2022. Extended conference talk:  Generalization despite overfitting in quantum machine learning models. Nov 9, 2022 </span>
 6. <span style="font-size:small;"> Eisert group QML seminar. Talk: Generalization despite overfitting in quantum machine learning models. Nov 4, 2022 </span>
 5. <span style="font-size:small;"> Xanadu QML seminar. Talk: Generalization despite overfitting in quantum machine learning. Oct 13, 2022 </span>
 4. <span style="font-size:small;"> APS March meeting. Talk: Qubit assignment on NISQ hardware using Simulated Annealing and a Loschmidt Echo heuristic. Mar 16, 2022. </span>
 3. <span style="font-size:small;"> Second annual International Workshop on Quantum Computing Software. Talk: Large scale multi-node simulations of Z2 gauge theory quantum circuits using Google Cloud Platform. Nov 15, 2021. </span>
 2. <span style="font-size:small;"> Chicago quantum exchange workshop on feature maps. Talk: Machine learning of high dimensional data on a noisy quantum processor. Apr 16, 2021. </span>
 1. <span style="font-size:small;"> Stanford Linear Accelerator AI seminar. Talk: Machine learning of high dimensional data on a noisy quantum processor. Dec, 2020. </span> -->

