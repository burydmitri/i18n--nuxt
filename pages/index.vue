<template>
  <div class="home">
    <h2 class="home__title">{{ $t('hello') }}</h2>
    <div class="buttons home__buttons">
      <nuxt-link
        :to="switchLocalePath('ru')"
        class="buttons__btn buttons__btn--ru"
        >{{ $t('buttons.ru') }}</nuxt-link
      >
      <nuxt-link
        :to="switchLocalePath('en')"
        class="buttons__btn buttons__btn--en"
        >{{ $t('buttons.en') }}</nuxt-link
      >
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

  color: var(--white);
  background: var(--black);

  &__title {
    font-size: 50px;

    margin-bottom: 50px;
  }
}
.buttons {
  display: flex;
  gap: 20px;

  &__btn {
    min-width: 100px;
    min-height: 50px;

    display: block;

    color: var(--white);
    background-color: var(--red);
    text-decoration: none;
    transition: 0.1s;

    padding: 20px;

    &:hover {
      background-color: darken(#f47265, 1 0%);
    }
  }
}
</style>
