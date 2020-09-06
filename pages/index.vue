<template>
  <div class="home">
    <h2>{{ $t('hello') }}</h2>
    <div class="buttons home__buttons">
      <nuxt-link :to="switchLocalePath('ru')" class="buttons--ru">{{
        $t('buttons.ru')
      }}</nuxt-link>
      <nuxt-link :to="switchLocalePath('en')" class="buttons--en">{{
        $t('buttons.en')
      }}</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="less" scoped>
.home {
  width: 100%;
  height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
