<template>
  <div class="re">
    <Header txt="充值">
      <router-link to="/wallet" slot="left" class="left">
        <img src="./../img/icon_back@2x.png" />
      </router-link>
    </Header>
    <!-- <Banner></Banner> -->
    <div class="swiper-container lunbo">
      <div class="swiper-wrapper">
        <div class="swiper-slide lia">
          <p>2000平驾币</p>
          <p>
            <img src="./1.png" />送300积分
          </p>
        </div>
        <!-- <div class="swiper-slide lib">
          <p>1000平驾币</p>
          <p>
            <img src="./1.png" />送100积分
          </p>
        </div> -->
        <!-- <div class="swiper-slide lic">
          <p>3000平驾币</p>
          <p>
            <img src="./1.png" />送400积分
          </p>
        </div> -->
        <!-- <div class="swiper-slide lid">
          <p>5000平驾币</p>
          <p>
            <img src="./1.png" />送600积分
          </p>
        </div> -->
        
      </div>
    </div>
    <div class="text">1积分=1元,每单最高可使用积分冲抵40%的租车费用</div>
    <div class="cen">
      <ul>
        <li @click="fn()">
          <p>25%首选</p>
          <p>{{num1}}</p>
        </li>
        <li @click="fn1()">
          <p>30%首选</p>
          <p>{{num2}}</p>
        </li>
        <li @click="fn2()">
          <p>55%首选</p>
          <p>{{num3}}</p>
          <div class="tj">推荐</div>
        </li>
      </ul>
    </div>
    <div class="botm">
      <div class="pay">
        <span>充值金额:</span> ￥
        <input type="text" :value="this.$store.state.num" @input="changenum()" />
      </div>
      <div class="p_style">
        支付方式
        <ul>
          <li>账户余额</li>
          <li>支付宝支付</li>
          <li>微信支付</li>
        </ul>
      </div>
      <p class="check">
        <van-checkbox
          v-model="checked"
          checked-color="#FFCC00"
          shape="square"
          icon-size=".13rem"
        >同意平驾分时租车租赁协议</van-checkbox>
      </p>
    </div>
    <Foot text="确认支付"  @click='ff()'></Foot>
    <!-- <router-link to="/recharge_success"> 
    </router-link> -->
    <Zhifu></Zhifu>
  </div>
</template>
<script src='./jquery-3.4.0.min.js'></script>
<script>
</script>
<script>
import Header from "./../../../components/Zmy/head/head";
import jquery from "./jquery-3.4.0.min.js";
import Foot from "./../../../components/Zmy/foot";
import Swiper from './../../../../node_modules/swiper/dist/js/swiper';
import Zhifu from './../../../components/Zmy/zhifu'

export default {
  data() {
    return {
      checked: true,
      c_color: false,
      num1: 200,
      num2: 300,
      num3: 500,
      bol:false
      
    };
  },
  methods: {
    changenum() {
      let a = $("input").val();
      this.$store.commit("changes", a);
      console.log(a);
    },
    fn() {
      this.$store.commit("change", this.num1);
    },
    fn1() {
      this.$store.commit("change", this.num2);
    },
    fn2() {
      this.$store.commit("change", this.num3);
    },
    ff(){
      this.bol=!this.bol;
      console.log(this.bol);
    }
  },
  components: {
    Header,
    Foot,
    Zhifu
    // Banner
  },
  mounted() {
    var mySwiper = new Swiper(".lunbo", {
      direction: "horizontal", // 垂直切换选项
      loop: true, // 循环模式选项
      slidesPerView: "auto",
      centeredSlides: true,
      spaceBetween: 16
    });
    $(function() {
      $(".cen li").on("click", function() {
        $(this).toggleClass("cor");
        $(this)
          .siblings("li")
          .removeClass("cor");
      });
    });
  }
};
</script>

<style scoped lang='less'>
@import './../../../../node_modules/swiper/dist/css/swiper.min.css';
.re {
  text-align: center;
  height: 100%;
  .lunbo {
    padding: 0.12rem 0;
    .swiper-wrapper {
      .swiper-slide {
        width: 3.6rem;
        height: 1.17rem;
        border-radius: 0.1rem;
        font-size: 0.13rem;
        color: white;
        p:nth-child(1) {
          padding-top: 0.39rem;
        }
        p:nth-child(2) {
          padding-top: 0.1rem;
          img {
            width: 0.19rem;
            height: 0.17rem;
            display: inline-block;
            vertical-align: middle;
          }
        }
      }
<<<<<<< HEAD
      .lia {
        background: #f9c307;
=======
    }
  }
  .lia {
    background: #f9c307;
  }
  .lib {
    background: #33ccff;
  }
  .lic {
    background: yellowgreen;
  }
  .lid {
    background: #f55378;
  }
}
.text {
  font-size: 0.14rem;
  color: #333333;
  padding: 0 0.53rem 0 0.57rem;
  font-weight: bold;
  font-family: PingFang-SC-Bold;
  text-align: left;
}
.cen {
  padding: 0.23rem 0.16rem 0.25rem 0.16rem;
  width: 100%;
  ul {
    display: flex;
    flex-direction: row;
    li {
      flex-direction: column;
      justify-content: space-between;
      width: 0.92rem;
      height: 1.21rem;
      border: 1px solid #999999;
      border-radius: 0.05rem;
      font-size: 0.12rem;
      color: #333333;
      p:nth-child(1) {
        margin-top: 0.25rem;
>>>>>>> origin/master
      }
      .lib {
        background: #33ccff;
      }
      .lic {
        background: yellowgreen;
      }
      .lid {
        background: #f55378;
      }
    }
  }
<<<<<<< HEAD
  .text {
=======
}
.botm {
  padding: 0 0.29rem;
  text-align: left;
  width: 100%;
  height: 2rem;
  .pay {
>>>>>>> origin/master
    font-size: 0.14rem;
    color: #333333;
    padding: 0 0.53rem 0 0.57rem;
    font-weight: bold;
<<<<<<< HEAD
    font-family: PingFang-SC-Bold;
    text-align: left;
    height: .384rem;
  }
  .cen {
    padding: 0.27rem 0.16rem 0.25rem 0.16rem;
    width: 100%;
    height: 1.73rem;
=======
    padding: 0.1rem 0;
    border-bottom: 1px solid #e8e8e8;
    color: red;
    span{
      color:#333333;
    }
  }
  .p_style {
    font-size: 0.14rem;
    font-weight: bold;
    padding-top: 0.08rem;
>>>>>>> origin/master
    ul {
      display: flex;
      flex-direction: row;
      li {
<<<<<<< HEAD
        flex-direction: column;
        justify-content: space-between;
        width: 0.92rem;
        height: 1.21rem;
        border: 1px solid #999999;
        border-radius: 0.05rem;
        font-size: 0.12rem;
        color: #333333;
        p:nth-child(1) {
          margin-top: 0.25rem;
        }
        p:nth-child(2) {
          margin-top: 0.17rem;
          font-size: 0.16rem;
          color: #f4cd63;
        }
        .tj {
          font-size: 0.1rem;
          width: 0.37rem;
          height: 0.14rem;
          line-height: 0.14rem;
          color: white;
          background: #f4453c;
          border-radius: 0.07rem;
          margin-top: 0.14rem;
          margin-left: 0.27rem;
        }
      }
      .cor {
        border: 1px solid #f9c307;
=======
        font-weight: normal;
        padding: 0.1rem 0 0.1rem 0.42rem;
        border-bottom: 1px solid #e8e8e8;
        font-size: 0.13rem;
>>>>>>> origin/master
      }
      li:nth-child(2) {
        margin: 0 0.35rem;
      }
    }
  }
  .botm {
    padding: 0 0.29rem;
    text-align: left;
    width: 100%;
    height: 2.48rem;
    .pay {
      font-size: 0.14rem;
      font-weight: bold;
      padding-bottom: .12rem;
      border-bottom: 1px solid #e8e8e8;
      color: red;
      span {
        color: #333333;
      }
    }
    .p_style {
      font-size: 0.14rem;
      font-weight: bold;
      padding-top: 0.08rem;
      ul {
        li {
          font-weight: normal;
          padding: 0.1rem 0 0.12rem 0.42rem;
          border-bottom: 1px solid #e8e8e8;
          font-size: 0.13rem;
        }
        li:nth-child(3) {
          border: none;
        }
      }
    }
    .check {
      font-size: 0.12rem;
      input {
        width: 0.13rem;
        height: 0.13rem;
        z-index: 12;
      }
    }
  }
}
</style>
