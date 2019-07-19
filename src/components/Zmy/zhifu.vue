<template>
  <div class="bg" :class="{aaa:bol_}">
    <!-- <div class="gg"></div> -->
    <div class="conte">
      <div class="ti">
        <img src="./icon_1.png" @click="fff()">
        <span>确认付款</span>
      </div>
      <!-- <div class="money">￥ {{ list.Integral }}</div> -->
      <div class="money">
        <p>
          ￥
          <span>{{ list }}</span>
        </p>
      </div>
      <div class="userid">
        <span>订单编号:</span>
        
        <!-- <span>{{ list.id }}</span> -->
        <span>{{ li }}</span>
      </div>
      <div class="userid two">
        <span>付款方式:</span>  
        <span>
          支付宝
          <img src="./icon_2.png" />
        </span>
      </div>
      <router-link to='/recharge_success'>
        <div class="btn">立即付款</div>
      </router-link>
     
    </div>
  </div>
</template>

<script>
import Tj from './../../page/Zmy/tj'
export default {
  data() {
    return {
      list: [],
      li:[],
      bol_:null
    };
  },
  methods: {
    fff(){
      this.bol_=false;
    }
  },
  components: {},
  mounted() {
    this.axios
      .post(
        "http://172.25.1.194:8080/user/recharge",
        this.qs.stringify({
          money: this.$store.state.num,
          id:this.$store.state.id
        })
        // money:
        //后台传值
      )
      .then(res => {
        console.log(res);
        this.list = res.config.data.split('=')[1].slice(0,3);
        this.li = res.config.data.split('=')[2]
        console.log(this.list)
        console.log(this.li)
      })
      .catch(err => {
        console.log(err);
      });
      var vm = this;
      Tj.$on('cz',(data)=>{
        vm.bol_=data;
      })
  }
};
</script>

<style scoped lang='less'>

.bg {
  font-size: 0.16rem;
  height: 100%;
  width: 100%;
  z-index: 5;
  position: relative;
  background: rgba(0, 0, 0, .3);
  transform:translateX(-15rem);
  position: absolute;
  top:0;
  left: 0;
  .conte {
    z-index: 10;
    position: absolute;
    bottom: 0;
    width: 100%;
    background: white;
    .ti {
      height: 0.44rem;
      line-height: 0.44rem;
      text-align: center;
      overflow: hidden;
      color: #333333;
      border-bottom: 1px solid #e8e8e8;
      img {
        float: left;
        width: 0.18rem;
        height: 0.18rem;
        margin-top: 0.13rem;
        margin-left: 0.16rem;
      }
      span {
        margin-right: 0.16rem;
      }
    }
    .money {
      padding: 0.35rem 1.4rem 0.25rem 1.38rem;
      text-align: center;
      span {
        font-size: 0.38rem;
      }
    }
    .userid {
      font-size: 0.16rem;
      color: #666666;
      padding-left: 0.17rem;
      padding-right: 0.17rem;
      overflow: hidden;
      padding-bottom: 0.13rem;
      border-bottom: 1px solid #e8e8e8;
      span:nth-child(1){
        float: left;
      }
      span:nth-child(2) {
        float: right;
      }
      img {
        display: inline-block;
        width: 0.08rem;
        height: 0.14rem;
        vertical-align: middle;
        margin-bottom: 0.02rem;
      }
    }
    .two {
      padding-top: 0.12rem;
    }
    .btn {
      margin: 1rem 0.15rem 0.24rem 0.15rem;
      height: 0.44rem;
      line-height: 0.44rem;
      border: none;
      background: #f9c307;
      color: white;
      font-size: 0.16rem;
      text-align: center;
      border-radius: 0.22rem;
    }
  }
}
.aaa{
  transform: translateX(0rem);
}
</style>
