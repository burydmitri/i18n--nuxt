<template>
  <div class="home">
    <h2>{{ $t('hello') }}</h2>
    <div class="buttons home__buttons">
      <nuxt-link class="buttons--ru">{{ $t('buttons.ru') }}</nuxt-link>
      <nuxt-link class="buttons--en">{{ $t('buttons.en') }}</nuxt-link>
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
  align-items: center;
  justify-content: center;
}
</style>
