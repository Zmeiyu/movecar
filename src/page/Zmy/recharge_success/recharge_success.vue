<template>
  <div class="res">
    <Header txt="充值">
      <router-link to='/recharge' slot="left" class="left">
        <img src="./../img/icon_back@2x.png"/>
      </router-link>      
    </Header>
    <div class="pic">
      <img src="./img/car.png">
      <p>您已充值成功</p>
    </div>
    <div class="suc">
      <img src="./img/ok.png" alt="">
      <p>您已充值 (元)</p>
      <p>{{ $store.state.num }}</p>
      <p>获得{{ $store.state.num }}积分</p>
    </div>
<<<<<<< HEAD
    <router-link to='/Carlist'>
      <Foot text='去租车吧'></Foot>
    </router-link>
    
=======
    <Foot text='去租车吧' class="footr"></Foot>
>>>>>>> origin/master
  </div>
</template>

<script>
import Header from "./../../../components/Zmy/head/head";
import Foot from './../../../components/Zmy/foot'
export default {
  data() {
    return {
    }
  },
  methods: {
  },
  components: {
    Header,
    Foot
  },
  mounted(){
    this.axios.post('http://172.25.1.194:8080/user/recharge',
    this.qs.stringify({
      money:this.$store.state.num,
      id:this.$store.state.id
    })
    ).then((res)=>{
      console.log(res);
      
    }).catch((err)=>{
      console.log(err)
    })
  }
}
</script>

<style scoped lang='less'>
.res{
  text-align: center;
  .pic{
  width: 100%;
  height: 2.19rem;
  background: #F9C307;
  padding: .28rem .87rem .82rem 1rem;
  img{
    width: 1.88rem;
    height: 1.09rem;
  }
  p{
    color: white;
    font-size: .18rem;
    font-weight: bold;
    margin-top: .34rem;
  }
}
.suc{
  width: 100%;
  height: 3.72rem;
  img{
    // padding: .2rem 1.33rem 0 1.53rem;
    width: .89rem;
    height: .59rem;
    margin:.2rem 1.33rem .46rem 1.53rem;
  }
  p:nth-child(2){
    font-size: .12rem;
    color:#666666;
  }
  p:nth-child(3){
    // padding: .15rem 0 .17rem 0;
    font-size: .36rem;
    font-weight: bold;
    color:#333333;
    padding-bottom: .02rem;
  }
  p:nth-child(4){
    font-size: .12rem;
    color:#333333;
  }
}
.footr{
  margin-top: 1.3rem;
  // margin-right: .16rem;
}


}

</style>
