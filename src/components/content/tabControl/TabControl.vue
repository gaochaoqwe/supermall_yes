<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles" :key="item" 
    class="tab-control-item" :class="{active:index === currentIndex}" @click="btnClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
  export default {
    name:'TabControl',
    data(){
      return {
        currentIndex:0
      }
    },
    props:{
      titles:{
        type:Array,
        default(){
          return []
        }

      }
    },
    methods:{
      btnClick(index){
        this.currentIndex = index;
        this.$emit('tabclick',index)
      }
    }
  }
</script>

<style scoped>
  .tab-control {
    display:flex;
    text-align:center;
    font-size:15px;
    background-color: #fff;
  }
  .tab-control-item {
    flex:1;
    height:40px;
    line-height:40px;
  }
  .tab-control-item span{
    padding:5px;
  }
  .active {
    color:pink;
    
  }
  .active span {
    border-bottom:3px solid pink;
  }
</style>