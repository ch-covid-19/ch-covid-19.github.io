<template>
    <section id="about" class="section section-lg bg-primary">
      <div class="container shape-container d-flex">
        <div class="col text-white">
          <h1 class="display-3 text-white">{{ $t('about.title') }}</h1>

          <h3 class="text-white">{{ $t('about.headWho') }}</h3>
          <p>{{ $t('about.who') }}</p>

          <h3 class="text-white">{{ $t('about.headNeedYou') }}</h3>
          <p>{{ $t('about.needYou') }}</p>

          <h3 class="text-white">{{ $t('about.headData') }}</h3>
          <p>{{ $t('about.data') }}</p>

          <h3 class="text-white">{{ $t('about.headDataUpdate') }}</h3>
          <p>{{ $t('about.dataUpdate') }}</p>

          <h3 class="text-white">{{ $t('about.headPublicData') }}</h3>
          <p>{{ $t('about.publicData') }}</p>

          <h3 class="text-white">{{ $t('about.headDataCare') }}</h3>
          <p>{{ $t('about.dataCare') }}</p>

          <h3 class="text-white">{{ $t('about.headImprovement') }}</h3>
          <p>{{ $t('about.improvement') }}</p>
        </div>
      </div>
    </section>
</template>

<script>

  export default {
    name: "about",
    components: {},
  };

</script>

<style scoped>
  .headline {
    font-size: 1.1em;
    font-weight: bolder;
  }
</style>
