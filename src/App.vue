<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
    <input type="text" v-model="href">
    <a :href="href" v-show="isShow">{{href}}</a>
    <button @click="toggleLink"> click me</button>

    <hr>
    <button @click="selectFirst"> select first </button>
      <div v-for="product in products" :key="product.id" :class="{select : isSelect}">
          <h2>
            {{product.id}}
          </h2>
          <h3>{{product.name}}</h3>
        </div>

        <hr>
        <product :class="{select : isSelect}"></product>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      href : '',
      isShow : true,
      isSelect : true,
      products : [
        {id: 1, name: 'iPhone7'},
        {id: 2, name: 'iPhone6'}
      ]
    }
  },
  methods : {
    toggleLink(){
      this.isShow = !this.isShow
    },
    selectFirst(){
      this.isSelect = !this.isSelect
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.select{
  background: red;
}
</style>
