<template>
  <section class="section section-lg">
    <div class="container shape-container d-flex">
      <div class="col text-black">
        <h3 class="text-black">{{ $t(`teams.header`) }}</h3>
        <h4 class="text-black">{{ $t(`teams.subheader`) }}</h4>
        <div class="country-buttons">
          <base-button type="primary" v-for="country of countries" :key="country.code" class="country-button">
          <img :src="`https://www.countryflags.io/${country.code}/flat/32.png`"
               :alt="`${country.code} flag`"
               target="_blank"
               class="flag ml-1"/>
               <a v-if="country.status === 'prod'" :href="country.url" class="country">
               {{ $t(`app.countries.${country.code}`) }}
               </a>
               <a v-else>
                 {{ $t(`app.countries.${country.code}`) }}
                 <badge v-if="country.status === 'dev'" type="secondary">DEV</badge>
               </a>
          </base-button>
        </div>
        <h3 class="text-black">{{ $t(`openData.header`) }}</h3>
        <h4 class="text-black">{{ $t(`openData.subheader`) }}</h4>
        <div class="country-buttons">
          <base-button type="primary" v-for="country of prodCountries" :key="country.code" class="country-button">
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
</template>

<script>
const countries = require('@/assets/sites.json');

export default {
  name: "countries",
  components: {},
  data() {
    return {
      countries: countries,
    }
  },
  computed: {
      prodCountries() {
        let toPlot = []/* need a country at zero */
        countries.forEach(c => {
          if(c.status == 'prod'){
            toPlot.push(c)
          }
        });
        return toPlot;
      }
  },
};
</script>

<style scoped>
.country-buttons{
  margin: 2em;
}
.country-button{
  margin: 0.2em;
}

.country-buttons a:link {
  color: white;
  background-color: transparent;
  text-decoration: none;
}

.country-buttons a:visited {
  color: white;
  background-color: transparent;
  text-decoration: none;
}

.country-buttons a:hover {
  color: white;
  background-color: transparent;
  text-decoration: none;
}

.country-buttons a:active {
  color: white;
  background-color: transparent;
  text-decoration: none;
}
</style>
