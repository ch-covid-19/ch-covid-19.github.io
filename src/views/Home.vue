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

      <section class="section-hero section-shaped my-0">
        <div class="shape shape-style-1 shape-default shape-skew">
          <span></span>
          <span></span>
        </div>
        <div class="container shape-container d-flex">
          <div class="col text-white">
            <h3 class="text-white">{{ $t(`home.countryListTitle`) }}</h3>
            <div id="country-buttons">
              <base-button type="secondary" v-for="country of countries" :key="country.code" class="country-button">
              <img :src="`https://www.countryflags.io/${country.code}/flat/32.png`"
                   :alt="`${country.code} flag`"
                   target="_blank"
                   class="flag ml-1"/>
                   <a :href="country.url" class="country">
                   {{ $t(`app.countries.${country.code}`) }}
                   </a>
              </base-button>
            </div>
            <h3 class="text-white">{{ $t(`partnerships.title`) }}</h3>
            <div id="partnerships">
              <div class="card text-white bg-primary mb-3">
                <div class="card-body">
                  <h5 class="card-title">iGH: intelligent Global Health</h5>
                  <p class="card-text">
                    <a href="https://www.epfl.ch/labs/mlo/igh-intelligent-global-health/">iGH: intelligent Global Health</a>
                    research groupe of the laboratory of
                    <a href="https://www.epfl.ch/labs/mlo/">Machine Learning and Optimization Laboratory</a> at
                    <a href="https://www.epfl.ch">EPFL</a>
                  </p>
                </div>
              </div>
            </div>
            <h3 class="text-white">{{ $t(`openData.header`) }}</h3>
            <h4 class="text-white">{{ $t(`openData.subheader`) }}</h4>
            <div id="country-buttons">
              <base-button type="secondary" v-for="country of countries" :key="country.code" class="country-button">
              <img :src="`https://www.countryflags.io/${country.code}/flat/32.png`"
                   :alt="`${country.code} flag`"
                   target="_blank"
                   class="flag ml-1"/>
                   <a :href="country.datasets" class="country">
                   {{ $t(`app.countries.${country.code}`) }}
                   </a>
              </base-button>
            </div>
          </div>

        </div>
      </section>

    </div>

  </div>
</template>

<script>
  const countries = require('@/assets/sites.json');
  import VueWorldMap from "vue-world-map";

  export default {
    name: "home",
    components: {
      VueWorldMap,
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
            toPlot[c.code.toUpperCase()] = 1
          });
          return toPlot;
        }
    },
  };

</script>

<style scoped>
#partnerships a:link {
  color: white;
  background-color: transparent;
  text-decoration: underline;
}

#partnerships a:visited {
  color: white;
  background-color: transparent;
  text-decoration: underline;
}

#partnerships a:hover {
  color: white;
  background-color: transparent;
  text-decoration: underline;
}

#partnerships a:active {
  color: white;
  background-color: transparent;
  text-decoration: underline;
}

#worldMap{
  margin: 3em;
}

#alert{
  margin: 3em;
}

#country-buttons{
  margin: 2em;
}
.country-button{
  margin: 0.2em;
}
#partnerships{
  margin: 2em;
}

</style>
