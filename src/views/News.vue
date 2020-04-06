<template>
    <section id="news"class="section section-lg">
      <div class="container shape-container d-flex">
        <div class="col text-white">
          <h2 class="display-3 text-black">
            {{ $t('news.title') }}
          </h2>
          <div class="card text-white bg-primary mb-3" v-for="news of newsList">
            <div class="card-body">
              <h5 class="card-title text-white">
                <badge type="secondary">{{ news.date }}</badge>
                {{ news.title }}
              </h5>
              <p class="card-text">
                {{ news.content }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
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
