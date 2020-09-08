<template>
  <div class="home">
    <h1 class="home__title">{{ $t('message.hello') }}</h1>
    <div class="buttons home__buttons">
      <nuxt-link
        :to="switchLocalePath('ru')"
        class="buttons__btn buttons__btn--ru"
        >{{ $t('button.russian') }}</nuxt-link
      >
      <nuxt-link
        :to="switchLocalePath('en')"
        class="buttons__btn buttons__btn--en"
        >{{ $t('button.english') }}</nuxt-link
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
    font-weight: 700;
    background-color: var(--red);
    text-decoration: none;
    transition: 0.1s;
    text-align: center;

    padding: 20px;

    &:hover {
      color: var(--black);
      background-color: var(--green);
    }
  }
}
</style>
