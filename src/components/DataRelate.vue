<template>
    <div id="dataRelate">
      <h1>{{loading}}</h1>
      <h1>Hello,{{name}}! Now you can use Vue.JS!</h1>
<!--      <h1>{{getTime()}}</h1>-->
    </div>
</template>

<script type="text/javascript">
  export default {
    name:'dataRelate',
    el:'#dataRelate',
    data () {
      return {
        loading: "A fresh man is loading...",
        name: "Phil"
      }
        // getTime: function () {
        //   var date = new Date();
        //   return this.name + "start to use Vue.JS at" + date;
    }
  }
</script>

