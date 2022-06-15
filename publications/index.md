---
title: Publications
layout: academic
author_profile: true
---

<!--
<html>
<body>

<script src="https://bibbase.org/show?bib=https%3A%2F%2Fapi.zotero.org%2Fusers%2F8977552%2Fcollections%2FU9LKE4WR%2Fitems%3Fkey%3DRz23P0o82UTav1awtfi3IlzI%26format%3Dbibtex%26limit%3D100&jsonp=1"></script> 

</body>
</html> 
-->

[Click here for full BibTex details and to group by year or author (BibBase)](JackAllenPublicationsBibBase.html)

## PhD Thesis
**J. Allen.** “An Optimisation Framework for Magnetic Resonance Fingerprinting”. PhD Thesis, University of Oxford, 2019. Supervisors: Dr. James Kennedy & Prof. Peter Jezzard.

## Journal Articles
A. Suinesiaputra, …, **J. Allen**, …, P. Medrano-Gracia. “Statistical Shape Modeling of the Left Ventricle: Myocardial Infarct Classification Challenge”. IEEE Journal of Biomedical and Health Informatics, 2018.

**J. Allen**, …, V. Grau. “Myocardial Infarction Detection from Left Venctricular Shapes Using a Random Forest”. Camara O., Mansi T., Pop M., Rhode K., Sermesant M., Young A. (eds) Statistical Atlases and Computational Models of the Heart. Imaging and Modelling Challenges. Lecture Notes in Computer Science, 2016.

## Conferences
S. Kukran, …, **J. Allen**, …, M. Grech-Sollars. "Mitigation of Magnetisation Transfer Effects Using Off-Resonance Pulses In MR Fingerprinting". ISMRM (programme number: 2598), 2022.

G. Yang, …, **J. Allen**, …, J. Keegan. “Atrial Scar Segmentation from 3D Late Gadolinium Enhanced Datasets: Effect of Time After Contrast Injection”. SCMR, 2021.

**J. Allen**, …, P. Gatehouse. “Blood-Focused Dynamic Inversion Times for 3D LGE Imaging: Initial Patient Demonstration”. Digital poster. ISMRM, 2021.

**J. Allen**, …, P. Gatehouse. “Dynamic Inversion Times for 3D LGE Imaging, using a Blood-Focused Algorithm: Initial Patient Demonstration”. Digital poster. Postgraduate meeting of the British, Irish & Iberian chapters of the ISMRM, 2021.

**J. Allen**, …, J. Keegan. “Improved Image Quality for 3D LGE Scar Imaging in Patients with Fast and Variable Heart Rate: a Simulation Study”. Digital poster. ISMRM, 2020.

**J. Allen**, …, P. Jezzard. “Estimating MRF Time Point Importance by Random Forest Classification”. Poster. ISMRM MR Fingerprinting workshop, 2017.

**J. Allen**, …, P. Jezzard. “A Comparison of Optimised Single-Shot MR Fingerprinting Pulse Sequence Designs”. Poster. ISMRM, 2017.

**J. Allen**, …, V. Grau. “Myocardial Infarction Detection from Left Ventricular Shapes Using a Random Forest”. Poster. STACOM workshop, in conjunction with MICCAI 2015.



## Other
**J. Allen**, …, S. V. Babu-Narayan. “Fully-Modelled Blood-Focused Variable Inversion Times for 3D Late Gadolinium-Enhanced Imaging”. Magnetic Resonance Imaging (Journal technical note **submitted February 2022, currently under review**).

**J. Allen**, …, P. Jezzard. “Time-efficient Single-Shot Spin-Echo Magnetic Resonance Fingerprinting (MRF)”. ISMRM, 2018 (**abstract not accepted**).

**J. Allen** "The Characterisation of a New Environmentally Sensitive Membrane Dye (di-2-ANBDQ(F)PTEA". Supervisor: Dr. Dylan Owen. Physics MSci final-year project, King's College London, 2014. (**unpublished, submitted as part of MSci course**)

<p style="color: purple">This is a purple paragraph.</p>

<!-- {% raw %} -->
<!-- #JA: remove this to uncomment
<div id="app"> 
    <div>
      <p><br></p>
      <p style="width:60%;">
          <Slider
            v-model="yearslider.value"
            v-bind="yearslider"
          ></Slider>
      </p>
          </div>
    <div v-for="yr in [...new Set(publ.map(a => a.year))].sort().reverse()">
      <h2>{{ yr }}</h2>
      <ul class="publist">
        <div v-for="pub in publ.filter(a => (a.year === yr))">
          <li class="publist">{{ pub.text }}<span v-if="pub.preprint != ''"> &mdash; <a v-bind:href="pub.preprint">Preprint</a></span><span v-if="pub.datarepo != ''"> &mdash; <a v-bind:href="pub.datarepo">Data repository</a></span><span v-if="pub.rpackagename != ''"> &mdash; <a v-bind:href="pub.rpackagelink">{{ pub.rpackagename }}</a></span><span v-if="pub.webappname != ''"> &mdash; <a v-bind:href="pub.webapplink">{{ pub.webappname }}</a></span><span v-if="pub.doi != ''">&nbsp;<div data-badge-popover="bottom" style="display: inline-block;" data-badge-type="4" v-bind:data-doi="pub.doi" data-hide-no-mentions="true" class="altmetric-embed"></div></span></li>
        </div>
      </ul>
    </div>
</div>
<!-- {% endraw %} -->

<!--
<script> 
// publication list
var p = [
        {% for ms in site.data.publications %}{
          "id": "{{ ms.id }}",
          "text": "{{ ms.text }}",
          "year": {{ ms.year }},
          "type": "{{ ms.type }}",
          "authorship": "{{ ms.authorship }}",
          "status": "{{ ms.status }}",
          "preprint": "{{ ms.preprint }}",
          "datarepo": "{{ ms.datarepo }}",
          "rpackagename": "{{ ms.rpackagename }}",
          "rpackagelink": "{{ ms.rpackagelink }}",
          "webappname": "{{ ms.webappname }}",
          "webapplink": "{{ ms.webapplink }}",
          "doi": "{{ ms.doi }}"
        }{% unless forloop.last %},{% endunless %}
      {% endfor %}];
// unique years
var yrs = [...new Set(p.map(a => a.year))].sort().reverse();
//vue app
const app = Vue.createApp({
  data: () => ({
    yearslider: {
        value: [Math.min(...yrs), Math.max(...yrs)],
        min: Math.min(...yrs),
        max: Math.max(...yrs),
    },
    pubs: p,
    allyears: yrs,
    show: {
        empirical: true,
        methods: true,
        first: true,
        last: true,
        published: true,
        inprep: true,
    },
  }),
  computed: {
    publ: function () {
        var x = [];
        for (i = 0; i < this.pubs.length; i++) {
            let add = false;
            // type
            if (this.show.empirical && this.pubs[i].type == "empirical")
                add = true;
            if (this.show.methods && this.pubs[i].type == "methods")
                add = true;
            // authorship
            if (this.show.first && this.pubs[i].authorship == "first")
                add = true;
            if (this.show.last && this.pubs[i].authorship == "last")
                add = true;
            // status
            if (this.show.published && this.pubs[i].status == "published")
                add = true;
            if (this.show.inprep && this.pubs[i].status != "published")
                add = true;
            if (add) {
                if (this.pubs[i].year < this.yearslider.value[0]) {
                    add = false;
                }
                if (this.pubs[i].year > this.yearslider.value[1]) {
                    add = false;
                }
            }
            if (add)
                x.push(this.pubs[i]);
        }
        return x
    }
  }
})
// slider component
app.component('Slider', VueformSlider)
app.mount('#app')
</script>
-->
