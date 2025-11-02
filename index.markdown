---
layout: default
title: Home - Vini e Ristoranti
---

{% comment %} Prende l'ultimo articolo pubblicato nella collezione 'vini_e_cantine' {% endcomment %}
{% assign ultimo_vino = site.vini_e_cantine | reverse | first %}

{% comment %} *** Correzione Liquid: prepariamo i valori con i filtri prima di includerli *** {% endcomment %}
{% assign testo_vino = ultimo_vino.content | strip_html | truncatewords: 60 | default: "Inserisci qui un testo introduttivo se non ci sono articoli." %}
{% assign immagine_vino = ultimo_vino.image | default: "/assets/images/placeholder-vino.jpg" %}

{% include section_block.html
  title="Le Nostre Selezione: Vini e Cantine"
  text=testo_vino
  image=immagine_vino
  link="/vini-e-cantine/"
  section_class="bg-light-grey"
%}

{% assign ultimo_ristorante = site.ristoranti_e_osterie | reverse | first %}

{% comment %} *** Correzione Liquid per RISTORANTI *** {% endcomment %}
{% assign testo_ristorante = ultimo_ristorante.content | strip_html | truncatewords: 60 | default: "Inserisci qui un testo introduttivo se non ci sono articoli." %}
{% assign immagine_ristorante = ultimo_ristorante.image | default: "/assets/images/placeholder-ristorante.jpg" %}

{% include section_block.html
  title="I Sapori del Territorio: Ristoranti e Osterie"
  text=testo_ristorante
  image=immagine_ristorante
  link="/ristoranti-e-osterie/"
  section_class="bg-white inverse-layout"
%}

{% comment %} La sezione 3 non aveva filtri, quindi la lasciamo pulita. {% endcomment %}
{% include section_block.html
  title="Prenota una Visita"
  text="Vuoi saperne di più sulla nostra filosofia? Contattaci o seguici sui social media."
  image="/assets/images/contatti.jpg"
  link="/contatti/"
  section_class="bg-dark-contrast"
%}