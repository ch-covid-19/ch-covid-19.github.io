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
            <h1 class="display-3 text-white">{{ $t('home.title') }}</h1>
            <h3 class="text-white">{{ $t(`home.subtitle`) }}</h3>
            <vue-world-map id="worldMap"
                    v-bind:countryData="countryData"
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
            <h4 class="text-white">{{ $t(`home.countryListTitle`) }}</h4>
            <div id="country-buttons">
              <base-button type="secondary" v-for="country of countries" :key="country.code">
              <img :src="`https://www.countryflags.io/${country.code}/flat/32.png`"
                   :alt="`${country.code} flag`"
                   target="_blank"
                   class="flag ml-1"/>
                   <a :href="country.url" class="country">
                   {{ $t(`app.countries.${country.code}`) }}
                   </a>
              </base-button>
            </div>
            <h4 class="text-white">{{ $t(`partnerships.title`) }}</h4>
            <div id="country-buttons">
              <base-button type="secondary" v-for="country of countries" :key="country.code">
              <img :src="`https://www.countryflags.io/${country.code}/flat/32.png`"
                   :alt="`${country.code} flag`"
                   target="_blank"
                   class="flag ml-1"/>
                   <a :href="country.url" class="country">
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
        mapBaseLayerUrl: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
        countries: countries,
        countryData: {
            US: 0, /* need a country at zeor */
            CH: 1,
            IN: 1,
            MX: 1
          },
        map: {
          defaultCountryFillColor: '#555abf',
          highColor: '#ff000099',
          lowColor: '#555abf',
          countryStrokeColor: 'white'
        },
      }
    }
  };

</script>

<style scoped>

#worldMap{
  margin: 3em;
}

#country-buttons{
  margin: 2em;
}

</style>
