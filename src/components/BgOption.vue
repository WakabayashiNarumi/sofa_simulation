<template>
  <section>
      <div class="sm-bg-option">
        <h2 class="sm-option_title">背景</h2>
        <ul class="sm-bg-option_list">
          <li v-on:click="bg01Select" class="sm-bg-option_item sm-bg01">ウッディー</li>
          <li v-on:click="bg02Select" class="sm-bg-option_item sm-bg02">ストリート</li>
          <li v-on:click="bg03Select" class="sm-bg-option_item sm-bg03">エレガント</li>
          <li v-on:click="bg04Select" class="sm-bg-option_item sm-bg04">オーシャン</li>
        </ul>
        <div v-on:click="btnClose" class="sm-btn_close">
          <div class="sm-btn_close_line"></div>
          <div class="sm-btn_close_line"></div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  name: 'BgOption',
  props: {
    bgImg: [String, Number],
    roomActive: Boolean
    },
  methods: {
    bg01Select: function () {
      this.$parent.bgImg = 'simu_bg01.jpg'
    },
    bg02Select: function () {
      this.$parent.bgImg = 'simu_bg02.jpg'
    },
    bg03Select: function () {
      this.$parent.bgImg = 'simu_bg03.jpg'
    },
    bg04Select: function () {
      this.$parent.bgImg = 'simu_bg04.jpg'
    },
    btnClose: function () {
      this.$parent.roomActive = false
    }
  }
}
</script>

<!-- 背景選択 CSSカプセル化 -->
<style scoped lang="scss">
// シミュレーション開閉
.sm-btn_close {
  position: absolute;
  top: -1.6rem;
  right: 1.6rem;
}
.sm-btn_close_line {
  width: 2rem;
  height: 3px;
  position: absolute;
  top: 2rem;
  bottom: 0;
  right: 0;
  left: 0;
  background: #ffffff;
  &:nth-child(1) {
    transform:translateY(0) rotate(-45deg);
  }
  &:nth-child(2) {
   transform:translateY(0) rotate(45deg);
  }
}
.sm-bg-option {
  position: relative;
}
.sm-bg-option_list {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.sm-bg-option_item {
  color: #fff;
  font-weight: bold;
  width: 35%;
  height: auto;
  padding: 10vmin 3vmin;
  margin: 0 0 1rem 0;
  cursor: pointer;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  z-index: 0;
  &::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background: inherit;
    filter: brightness(0.9);
    z-index: -1;
  }
}
.sm-bg01 {
  background-image: url('/img/simulation/simu_bg01.jpg');
}
.sm-bg02 {
  background-image: url('/img/simulation/simu_bg02.jpg');
}
.sm-bg03 {
  background-image: url('/img/simulation/simu_bg03.jpg');
}
.sm-bg04 {
  background-image: url('/img/simulation/simu_bg04.jpg');
}
</style>
