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
            <h1 class="display-3 text-white">{{ $t('news.title') }}</h1>
            <div class="card text-white bg-primary mb-3" v-for="news of newsList">
              <div class="card-body">
                <h5 class="card-title text-white">{{ news.title }}</h5>
                <p class="card-text">
                  {{ news.content }}
                </p>
              </div>
              <div class="card-footer text-white bg-primary">
                 {{ news.date }}
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

  </div>
</template>

<script>
const newsList = require('@/assets/news.json');

export default {
  name: "news",
  components: {},
  data() {
    return {
      newsList: newsList.reverse(),
    }
  },
};

</script>

<style scoped>

</style>
