<template>
  <div class="hello">
    <h1 class="tp-heading">{{ msg }}</h1>
    <p class="tp-home_text">PWA対応した仮想のシミュレーションアプリです。当アプリはSPAを採用し、Vue.jsで開発されています。</p>
    <router-link class="sw-btn" to="/about">シミュレーションスタート <font-awesome-icon icon="chevron-right" class="tp-home_icon" /></router-link>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- CSSカプセル化 -->
<style scoped lang="scss">
.tp-heading {
  font-size: 2rem;
  color: #3c9a7b
}
.tp-home_text {
  width: 80%;
  margin: 0 auto 2rem auto;
  line-height: 1.6;
}
.sw-btn {
  display: inline-block;
  font-weight: bold;
  text-decoration: none;
  background: #34845A;
  color: #ffffff;
  border-radius: 2rem;
  padding: 1rem;
}
// トップページアイコン
.tp-home_icon {
  font-size: 1.2rem;
}
</style>
