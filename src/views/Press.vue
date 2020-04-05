<template>
  <div>
    <div class="position-relative">
      <section class="section-hero section-shaped my-0">
        <div class="shape shape-style-1 shape-default shape-skew">
          <span></span>
          <span></span>
        </div>
        <div class="container shape-container d-flex">
          <div class="row">
            <div class="col">
              <h3 class="text-white">{{ $t(`press.articles.header`) }}</h3>
              <ul class="list-group">
                <li class="list-group-item list-group-item-primary list-group-flush" v-for="item in articlesList">
                  <badge type="secondary">{{item.country}}</badge>
                  <span class="date">{{item.date}}</span>
                  <span class="document">{{item.title}}</span>
                  <a :href="item.link">
                    <base-button type="secondary" size="sm" icon="ni ni-cloud-download-95"></base-button>
                  </a>
                </li>
              </ul>
              <h3 id="releaseHeader" class="text-white">{{ $t(`press.releases.header`) }}</h3>
              <ul class="list-group">
                <li class="list-group-item list-group-item-primary" v-for="item in releasesList">
                  <badge type="secondary">{{item.country}}</badge>
                  <span class="date">{{item.date}}</span>
                  <span class="document">{{item.title}}</span>
                  <a :href="item.link">
                    <base-button type="secondary" size="sm" icon="ni ni-cloud-download-95"></base-button>
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>
    </div>

  </div>
</template>

<script>
const articlesList = require('@/assets/articles.json');
const releasesList = require('@/assets/releases.json');

export default {
  name: "press",
  components: {},
  data() {
    return {
      articlesList: articlesList.reverse(),
      releasesList: releasesList.reverse(),
    }
  },
};

</script>

<style scoped>
.date{
  margin-left: 1em;
  margin-right: 1em;
}
.document{
  margin-right: 1em;
}
#releaseHeader{
  margin-top:1em;
}

</style>
