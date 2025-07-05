---
layout: default
---
<p align="center">
<img src="{{site.baseurl}}/media/iapr-logo.jpeg" width="40%" alt="IAPR-TC15 Logo">
</p>

This is the official website of **Technical Committee #15 (TC15)** of the [**International Association for Pattern Recognition (IAPR)**](http://www.iapr.org/). 
TC15 is dedicated to promoting research on **graph-based representations and learning** in pattern recognition, image analysis, and related fields.

Graphs offer a rich and flexible way to represent structured and relational data. From image segmentation to shape analysis, from social network modeling to bioinformatics, graph-based methods play a central role in understanding complex data domains. In recent years, the emergence of graph neural networks (GNNs) and related deep learning techniques has further expanded the scope and impact of graph-based research.

As a technical committee, TC15 facilitates collaboration within the research community by coordinating workshops, challenges, and joint activities. It contributes to the dissemination of scientific advances, encourages reproducible research, and fosters connections among researchers.

### What You’ll Find Here

- Information about **TC15 activities**, past and present  
- Updates on **workshops, challenges, and conferences**  
- Access to **benchmark datasets, publications, and software**  
- Details about **our members, working groups, and mailing list**

*To become part of the TC15 community or subscribe to our mailing list, please visit the **[Members section](/members/)**.*

For communication with the current leaders, please use the following e-mail: chair at iapr-tc15.org

### Board Memebers

Chair: Prof. Vincenzo Carletti

Vice-Chair: Prof. Benoit Gaüzère

### Lates News

<ul>
  {% assign sortedposts = site.posts | sort: "date" | reverse %}
  {% for post in sortedposts limit:5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a><br/>
      <small>{{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>

