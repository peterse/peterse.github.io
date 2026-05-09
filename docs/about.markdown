---
layout: page
title: About
permalink: /about/
---

I currently work at Xanadu (opinions here are my own). I previously did research on machine learning and quantum information at University of Waterloo /  Perimeter Institute for Theoretical Physics. 

**Research timeline**

**2026-** machine learning with quantum computers at Xanadu, once again. Exploring the potential of quantum algorithms as _spectral methods_ (<a href="https://arxiv.org/abs/2603.24654">2603.24654</a>).

**2024-2025** theory and simulation of machine learning for (quantum) error correction (<a href="https://arxiv.org/abs/2505.22741
">2505.22741</a>) and learning theory for binary data  (<a href="https://openreview.net/forum?id=n5bPL58uMC
">ICLR 2026</a>).

**2021-2024** machine learning with quantum computers, e.g. connections between learning and entanglement (<a href="https://arxiv.org/abs/2404.07277
">2404.07277</a>), strange generalization behavior in quantum machine learning models (<a href="https://quantum-journal.org/papers/q-2023-12-20-1210/">Quantum</a>) with Maria Schuld at Xanadu, and how bandwidth affects quantum kernel models (<a href="https://openreview.net/forum?id=A1N2qp4yAq&referrer=[TMLR](%2Fgroup%3Fid%3DTMLR)">TMLR</a>).

**2019-2021** near-term implementations of quantum algorithms at Fermilab, e.g. how to select better qubits on Google's hardware (<a href="https://journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.3.040333">PRX Quantum</a>), simulating noisy quantum field theory simulations on a _lot_ of GPUs (<a href="https://ieeexplore.ieee.org/abstract/document/9651438">IEEE</a>, <a href="https://arxiv.org/abs/2111.02396
">2111.02396</a>), cheap-but-efficient readout error mitigation (<a href="https://journals.aps.org/pra/abstract/10.1103/PhysRevA.107.062426">Phys. Rev. A</a>), and quantum machine learning on Google's Sycamore quantum computer (<a href="https://www.nature.com/articles/s41534-021-00498-9">npj quantum</a>).

**2018-2019** part of the original team of UWaterloo students prototyping/developing <a href="https://www.tensorflow.org/quantum">TensorFlow Quantum</a> (<a href="https://arxiv.org/abs/2003.02989
">2003.02989</a>, <a href="https://uwaterloo.ca/news/news/new-software-combines-quantum-and-classical-machine-learning
">press</a>).

**2017-2018** design and fabrication of superconducting qubits.

<hr style="width:95%;color:gray;margin:auto;margin-bottom:.5cm;margin-top:0.5cm;" >
<h2>Posts</h2>
<ul class="post-list">
    {%- assign sorted_notes = site.notes | sort: "date" | reverse -%}
    {%- for post in sorted_notes -%}
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

