---
title: "Curriculum Vitae"
layout: single
permalink: /cv/
excerpt: "CV"
last_modified_at: 2026-03-24
toc: false
toc_sticky: false
toc_label: curriculum vitae
current_cv: /assets/documents/cv_EunkyungAraJo_20260317.pdf
---

<div id="pdf-viewer" style="height: 50em; width: 120%;"></div>

<script type="module">
  import EmbedPDF from 'https://cdn.jsdelivr.net/npm/@embedpdf/snippet@2/dist/embedpdf.js';

  EmbedPDF.init({
    type: 'container',
    target: document.getElementById('pdf-viewer'),
    src: '{{ page.current_cv }}',
    theme: { preference: 'system' }
  });
</script>