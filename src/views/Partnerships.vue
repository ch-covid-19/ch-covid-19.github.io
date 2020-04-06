<template>
  <section id="partnerships" class="section section-lg bg-primary">
    <div class="container shape-container d-flex">
      <div class="col text-black">
        <h3 class="text-white">{{ $t(`partnerships.title`) }}</h3>
        <div id="partnerships">
          <div class="card text-black bg-secondary mb-3">
            <div class="card-body">
              <h5 class="card-title">iGH: intelligent Global Health</h5>
              <p class="card-text text-dark">
                <a href="https://www.epfl.ch/labs/mlo/igh-intelligent-global-health/">iGH: intelligent Global Health</a>
                research groupe of the laboratory of
                <a href="https://www.epfl.ch/labs/mlo/">Machine Learning and Optimization Laboratory</a> at
                <a href="https://www.epfl.ch">EPFL</a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

export default {
  name: "partnerships",
  components: {},
  data() {
    return {
    }
  },
};
</script>

<style scoped>
#partnerships a:link {
  color: black;
  background-color: transparent;
  text-decoration: underline;
}

#partnerships a:visited {
  color: black;
  background-color: transparent;
  text-decoration: underline;
}

#partnerships a:hover {
  color: black;
  background-color: transparent;
  text-decoration: underline;
}

#partnerships a:active {
  color: black;
  background-color: transparent;
  text-decoration: underline;
}
</style>
