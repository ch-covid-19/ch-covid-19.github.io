<template>
  <div>
    <div class="position-relative">
      <!-- shape Hero -->
      <section class="section-hero section-shaped my-0">
        <div class="shape shape-style-1 shape-default shape-skew">
          <span></span>
          <span></span>
        </div>
        <div class="container shape-container d-flex">
          <div class="col text-white">
            <h1 class="display-3 text-white">{{ $t('home.header') }}</h1>
            <h3 class="text-white">{{ $t(`home.subheader`) }}</h3>
            <base-alert type="warning" id="alert">
             <strong>{{ $t(`home.alert.strong`) }}</strong>
             {{ $t(`home.alert.text`) }}<a :href="welcomeLink">link</a>.
            </base-alert>
            <vue-world-map id="worldMap"
                    v-bind:countryData="countriesMap"
                    v-bind:defaultCountryFillColor="map.defaultCountryFillColor"
                    v-bind:highColor='map.highColor'
                    v-bind:countryStrokeColor='map.countryStrokeColor'
                    v-bind:lowColor="map.lowColor"></vue-world-map>
          </div>
        </div>
      </section>
      <countries></countries>
      <parnteships></parnteships>
      <news></news>
      <press></press>
      <about></about>
    </div>
  </div>
</template>

<script>
  const countries = require('@/assets/sites.json');
  import VueWorldMap from "vue-world-map";
  import News from "@/views/News";
  import Countries from "@/views/Countries";
  import Parnteships from "@/views/Partnerships";
  import Press from "@/views/Press";
  import About from "@/views/About";

  export default {
    name: "home",
    components: {
      VueWorldMap,
      News,
      Countries,
      Parnteships,
      Press,
      About
    },
    data() {
      return {
        welcomeLink: process.env.VUE_APP_JOIN_GITHUB,
        countries: countries,
        map: {
          defaultCountryFillColor: '#555abf',
          highColor: '#ff000099',
          lowColor: '#555abf',
          countryStrokeColor: 'white'
        },
      }
    },
    computed: {
        countriesMap() {
          let toPlot = { 'US': 0 } /* need a country at zero */
          countries.forEach(c => {
            if(c.status == 'prod'){
              toPlot[c.code.toUpperCase()] = 1
            } else {
              toPlot[c.code.toUpperCase()] = 0.2
            }

          });
          return toPlot;
        }
    },
  };

</script>

<style scoped>
#worldMap{
  margin: 3em;
}

#alert{
  margin: 3em;
}

</style>
