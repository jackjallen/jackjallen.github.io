---
title: Code
layout: academic
author_profile: true
---

Feel free to make use of the code below. Citation or acknowledgment would be gratefully received, where appropriate.
Unfortunately I can't guarantee the absence of errors or 'bugs'. Please contact me regarding any issues or suggestions.

---

**Title:** *make_gif_3DLGE.m*

**Link:** <a href="make_gif_3DLGE/make_gif_3DLGE.zip">make_gif_3DLGE.m<a>

**Upload Date:** *June 2022*
    
**Description:** 
MATLAB code to make an animated GIF from a stack of images. Adapted from matlab file exchange: https://uk.mathworks.com/matlabcentral/answers/94495-how-can-i-create-animated-gif-images-in-matlab. Animations can also be made using 'ImageJ' software.

---

<!-- {% raw %} -->
<div id="app">
    <div>
     
    </div>
    <div v-for="sof in softw">
        <h2>{{ sof.name }}</h2>
        <ul class="softlist">
          <li>
          {{ sof.description }}
          </li>
          <li>
          <a v-bind:href="sof.link">{{ sof.type }}</a> / {{ sof.domain }}
          </li>
        </ul>
    </div>
</div>
<!-- {% endraw %} -->

<script>
// software list
var sw = [
        {% for ss in site.data.software %}{
          "name": "{{ ss.name }}",
          "description": "{{ ss.description }}",
          "link": "{{ ss.link }}",
          "type": "{{ ss.type }}",
          "domain": "{{ ss.domain }}"
        }{% unless forloop.last %},{% endunless %}
      {% endfor %}];
//vue app
const app = Vue.createApp({
  data: () => ({
    swa: sw,
    show: {
        rpkg: true,
        stata: true,
        gui: true,
        statistics: true,
        psychology: true,
    },
  }),
  computed: {
    softw: function () {
        var x = [];
        for (i = 0; i < this.swa.length; i++) {
            let add = false;
            if (this.show.rpkg && this.swa[i].type == "R package")
                add = true;
            if (this.show.stata && this.swa[i].type == "Stata module")
                add = true;
            if (this.show.gui && this.swa[i].type == "GUI")
                add = true;
            if (this.show.statistics && this.swa[i].domain == "Statistics")
                add = true;
            if (this.show.psychology && this.swa[i].domain == "Psychology")
                add = true;
            if (add)
                x.push(this.swa[i]);
        }
        return x
    }
  }
})
app.mount('#app')
</script>
