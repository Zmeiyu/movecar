<template>
  <div>
    <div class="foot" @click='ff()'>
      {{ text }}
    </div>
  </div>
</template>

<script>
import Tj from './../../page/Zmy/tj'
export default {
  props:['text'],
  data() {
    return {
<<<<<<< HEAD
      bol:true,
    }
  },
  methods: {
    ff(){
      // this.bol =! this.bol;
      console.log(this.bol);
      Tj.$emit('cz',this.bol)
    }
=======
    }
  },
  methods: {
>>>>>>> origin/master
  },
  components: {
  }
}
</script>

<style scoped lang='less'>
.foot{
<<<<<<< HEAD
  position: fixed;
  bottom: 0;
  margin: 0 .16rem .1rem .16rem;
=======
  // position: absolute;
  // bottom: 0;
  margin: 0.06rem .16rem .16rem .16rem;
>>>>>>> origin/master
  width: 3.43rem;
  height: .39rem;
  background: #F9C307;
  color: white;
  line-height: .39rem;
  font-size:.16rem;
  border-radius: .2rem
}
</style>
