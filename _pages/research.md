---
title: "Research"
layout: page
permalink: /research/
---

# Research Projects and Resources

<div class="research-project-list" markdown="0">

<article class="section-card research-project research-project--with-image" id="sawgraph">
<figure class="research-project-figure">
<p class="research-type">open knowledge network</p>
<div class="research-project-image-panel">
<img src="{{ '/images/research/sawgraph-logo.png' | relative_url }}" alt="SAWGraph logo" loading="lazy">
</div>
</figure>

<div class="research-project-content">
<h2 class="research-project-title">Safe Agricultural Products and Water Graph (SAWGraph)</h2>
<p>SAWGraph is an open knowledge network that integrates PFAS observations with information about facilities and industries, hydrology, geography, agriculture, and chemical substances. It supports investigation of monitoring results and coverage, potential impacts, and possible contamination sources and pathways.</p>
<p>Its ontology framework includes <strong>ContaminOSO</strong> for contamination observations and samples, the <strong>Facilities and Industries Ontology</strong>, the <strong>SAWGraph Spatial Ontology</strong>, the <strong>SAWGraph Water Ontology</strong>, and the <strong>DSSTox Ontology</strong> for chemical substances and their properties. These ontologies reuse and extend established models, with dataset-specific extensions that connect source data to the broader framework for integrated querying and analysis.</p>
<p>SAWGraph is supported by the <strong>U.S. National Science Foundation</strong> under <a href="https://www.nsf.gov/awardsearch/show-award?AWD_ID=2333782">Award No. 2333782</a> (Oct 2023–Sep 2027, estimated) as a Theme 1 project in the <strong>Prototype Open Knowledge Network (Proto-OKN)</strong> program. Led by SKAI Lab director Torsten Hahmann, the collaboration includes the University of Maine, Kansas State University, Pennsylvania State University, and Northeastern University, with researchers from the U.S. Environmental Protection Agency participating as federal partners.</p>
<p class="research-resource-links">
<a href="https://sawgraph.com/">Website and Demos</a>
<a href="https://github.com/SAWGraph">GitHub Repositories</a>
<a href="https://sawgraph.com/ontologies.html">Ontologies and Documentation</a>
</p>
</div>
</article>

<article class="section-card research-project research-project--with-image" id="digital-forest">
<figure class="research-project-figure">
<p class="research-type">geospatial knowledge graph</p>
<div class="research-project-image-panel">
<img src="{{ '/images/research/inspires-logo.png' | relative_url }}" alt="INSPIRES collaboration logo" width="836" height="1024" loading="lazy">
</div>
<figcaption>INSPIRES collaboration</figcaption>
</figure>

<div class="research-project-content">
<h2 class="research-project-title">Digital Forest Knowledge Graph</h2>
<p>The Digital Forest Knowledge Graph investigates how ontologies and geospatial knowledge graphs can bring together forest inventories, tree species information, and environmental data. The aim is to make these sources easier to query, explore, visualize, and analyze together, supporting research into forest–environment interactions and forest resource management.</p>
<p>This work includes ontologies for forest ecology and aggregated environmental data. The <strong>Spatial and Temporal Aggregate Data (STAD) Ontology Design Pattern</strong> represents statistically aggregated quantities and their spatial and temporal context, helping distinguish data summarized over different areas and time periods. The project also explores combining ontologies with machine learning to identify relationships in forest data.</p>
<p>The Digital Forest work was developed as part of the <strong>INSPIRES</strong> collaboration, supported by the <strong>U.S. National Science Foundation</strong> under <a href="https://www.nsf.gov/awardsearch/show-award?AWD_ID=1920908">Award No. 1920908</a> (Aug 2019–Jul 2024) through the <strong>EPSCoR RII Track-2</strong> program. Led by Aaron Weiskittel at the University of Maine, INSPIRES brought together researchers from the University of Maine, University of New Hampshire, University of Vermont, and Alabama A&amp;M University.</p>
<p class="research-resource-links">
<a href="https://github.com/theSKAILab/DigitalForestKG">GitHub Repository</a>
<a href="https://crsf.umaine.edu/inspires/">INSPIRES Project</a>
<a href="https://github.com/theSKAILab/STAD">STAD Ontology</a>
</p>
</div>
</article>

<article class="section-card research-project research-project--with-image" id="cellograph">
<figure class="research-project-figure">
<p class="research-type">cellulose informatics system</p>
<div class="research-initials" aria-hidden="true">CG</div>
</figure>

<div class="research-project-content">
<h2 class="research-project-title">CelloGraph</h2>
<p>CelloGraph is developing a cellulose informatics system to support materials discovery and research. The work combines information extraction from scientific publications, ontology development, expert review, data analysis, and web-based access to help researchers organize, query, and explore knowledge about materials, their properties, and their relationships.</p>
<p>The <strong>CelloGraph Ontology</strong> represents concepts in the cellulose materials domain, extending the Basic Formal Ontology (BFO) and reusing concepts from ChEBI. The <strong>Ontology for Named Entity Representation (OnNER)</strong> structures information about publications, extracted entities, their labels, and their provenance. The <strong>AnNER</strong> web application supports annotation and expert review, recording annotator identities, timestamps, and revision histories. Together, AnNER and OnNER support <strong>provenance-aware knowledge graph construction and querying</strong>, allowing researchers to trace entities back to their source text and examine how annotations were reviewed and revised.</p>
<p>Research contributing to CelloGraph is supported in part by the <strong>U.S. Department of Agriculture</strong> through the <strong>Forest Service</strong> (Project 20-JV-11111124-055), the <strong>Agricultural Research Service (ARS)</strong> (Project 0204-41510-001-98S), and the <strong>National Institute of Food and Agriculture (NIFA)</strong> under Grant No. 2021-67022-34366 (Mar 2021–Feb 2027).</p>
<p class="research-resource-links">
<a href="https://github.com/theSKAILab/CelloGraph">GitHub Repository</a>
<a href="https://github.com/theSKAILab/OnNER">OnNER Ontology</a>
<a href="https://theskailab.github.io/AnNER/">Try AnNER</a>
</p>
</div>
</article>

<article class="section-card research-project research-project--with-image" id="macleod">
<figure class="research-project-figure">
<p class="research-type">ontology development environment</p>
<div class="research-initials" aria-hidden="true">M</div>
</figure>

<div class="research-project-content">
<h2 class="research-project-title">Macleod</h2>
<p>Macleod provides scripts for developing and verifying ontologies written in CLIF, a dialect of Common Logic. It supports a subset of Common Logic focused on first-order logic axioms and imports between ontology modules.</p>
<p>Its main functions include <strong>format translation</strong> into languages used by automated reasoners, <strong>OWL approximation</strong> of CLIF ontologies, and <strong>ontology verification</strong>. Macleod coordinates external theorem provers and model finders to test logical consistency, prove intended consequences, and search for counterexamples. Its <strong>modular and parallel verification</strong> approach helps localize inconsistencies and identify consistent subtheories.</p>
<p class="research-resource-links">
<a href="https://github.com/thahmann/macleod">GitHub Repository and Documentation</a>
</p>
</div>
</article>

</div>