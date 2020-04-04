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

            <div class="card text-white bg-primary mb-3">
              <div class="card-body">
                <h5 class="card-title text-white">Mexico website is online </h5>
                <p class="card-text">
                  Our mexico team lauch their app today.
                </p>
              </div>
              <div class="card-footer text-white bg-primary">
                 31 March 2020
              </div>
            </div>

            <div class="card text-white bg-primary mb-3">
              <div class="card-body">
                <h5 class="card-title text-white">India website is online </h5>
                <p class="card-text">
                  Our inda team lauch their app today.
                </p>
              </div>
              <div class="card-footer text-white bg-primary">
                 30 March 2020
              </div>
            </div>

            <div class="card text-white bg-primary mb-3">
              <div class="card-body">
                <h5 class="card-title text-white">Switzerland website is online </h5>
                <p class="card-text">
                  Our switzerland team lauch their app today.
                </p>
              </div>
              <div class="card-footer text-white bg-primary">
                 24 March 2020
              </div>
            </div>

          </div>
        </div>
      </section>
    </div>

  </div>
</template>

<script>

export default {
  name: "news",
  components: {},
  data() {
    return { }
  },
};

</script>

<style scoped>

</style>
