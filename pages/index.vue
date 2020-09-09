<template>
  <div class="home">
    <h1 class="home__title">{{ $t('homeIntro.title') }}</h1>
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
    <!-- <p v-t="'message.hello'"></p> -->
    <!-- <p>{{ $t('message.hello') }}</p> -->

    <div class="content home__content">
      <h3 class="content__title">{{ $t('homeInfo.title') }}</h3>
      <p class="content__info">{{ $t('homeInfo.content') }}</p>
      <p>{{ test.testRu }}</p>
      <p>{{ $t('tests.test2') }}</p>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const data = await $axios.$get('http://localhost:1337/i-18-ns')
    return { test: data[0] }
  },
  i18n: {
    messages: {
      ru: {
        tests: {
          test1: 'тееест',
          test2: 'тессссст',
        },
      },
      en: {
        tests: {
          test1: 'tessssts',
          test2: 'T E S T',
        },
      },
    },
    // content: {
    //   ru: {
    //     tests: {
    //       test1: 'тееест',
    //       test2: 'тессссст',
    //     },
    //   },
    //   en: {
    //     tests: {
    //       test1: 'tessssts',
    //       test2: 'T E S T',
    //     },
    //   },
    // },
  },
}
</script>

<style lang="less" scoped>
.home {
  width: 100%;
  min-height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  color: var(--white);
  background: var(--black);

  padding-top: 30vh;

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
    transition: 0.2s;
    text-align: center;
    border-radius: 10px;

    padding: 20px;
    margin-bottom: 10px;

    &:hover {
      color: var(--black);
      background-color: var(--white);
    }
  }
}
.content {
  max-width: 500px;

  color: var(--white);
  font-weight: 300;
  text-align: center;

  margin: 50px 0;

  &__title {
    margin-bottom: 10px;
  }
}
</style>
