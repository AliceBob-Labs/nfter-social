<template>
  <div class="IE-flex-fix">
    <div id="site-wrapper" style="opacity: 1; transform: translate(0px, 0px);">
      <g-header />
      <div id="site-inner" data-page-container="true">
        <div class="xhr-page-contents" style="">
          <div data-widget="page-draw#pageDrawer, url-reloader">
            <Intro />
            <Feature />
            <Roadmap />
            <FAQ />
            <Team />
          </div>
        </div>
      </div>
      <g-footer />
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import Intro from '../../components/Home/Intro.vue'
import Feature from '../../components/Home/Feature.vue'
import Roadmap from '../../components/Home/Roadmap.vue'
import FAQ from '../../components/Home/FAQ.vue'
import Team from '../../components/Home/Team.vue'
import { isEmptyAddress } from '@/utils/index'
// import socialMoneyContractInstace from '@/api/eth/contract.js'
export default {
  components: {
    Intro,
    Feature,
    Roadmap,
    FAQ,
    Team
  },
  computed: {
    ...mapState(['token']),
    noToken() {
      return isEmptyAddress(this.token.tokenAddress)
    }
  },
  methods: {}
}
</script>

<style scoped lang="less" >
.font-center {
  text-align: center;
  color: #26498d;
}
.issue-section {
  text-align: left;
  li {
    margin: 1rem 0;
  }
}
.a-issue {
  color:#26498d;
  text-decoration: underline;
}
.site-title {
  .site-logo {
    font-size: 4rem;
  }
}
.human-coin {
  display: flex;
  align-items: center;
  justify-content: center;
  .coin {
    width: 5rem;
    height: 5rem;
    background: url(../../assets/coin.png);
    background-repeat: no-repeat;
    background-size: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .fh {
      font-size: 4rem;
      margin: 0 10px;
  }
  .p1 {
      width: 5rem;
  }
  .p2 {
      width: 5rem;
  }
  .icon {
      font-size: 4rem;
  }
  .icon2 {
      font-size: 3rem;
  }
}
.card-special-border {
  border: 2px #231f20 dashed;
}
</style>
