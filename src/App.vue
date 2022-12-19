


<template>
  <div class="container">
    <div class="logo" />
    <h1 class="title">Vue Testing App</h1>
    <div class="render_div">
      <button class="btn" @click="renderElements(1000)">Render 1000</button>
      <button class="btn" @click="renderElements(10000)">Render 10000</button>
      <button class="btn" @click="renderElements(25000)">Render 25000</button>
      <button class="btn" @click="renderElements(50000)">Render 50000</button>
    </div>
        <button class="btn" @click="copyArray">Copy Array</button>
        <button class="btn" @click="editArray">Edit Elements</button>
        <button class="btn">Delete Elements</button>
    <div class="line" />
    <ul class="list" v-for="element in array" v-bind:key="element">
      <li>{{element}}</li>
    </ul>
  </div>
</template>



<script>
  export default {
    name: 'App',
    data(){
      return {
        array: [],
        coppiedArray: []
      }
    },
    methods: {
      renderElements(number){
        console.log('test');
        for(let i=0; i<number;i++){
          this.array[i] = `Element nr: ${i+1}`
        }

      },
      copyArray(){
        console.log('copied');
        for(let i=0; i<this.array.length;i++){
          this.coppiedArray[i] = this.array[i];
        }
        console.log(this.coppiedArray)
      },
      editArray(){
        console.log('aaa');
        for(let i=0; i<this.array.length;i++){
          this.array[i] = this.array[i] + '+ edited'
        }
      }
    }
  }
</script>


<style lang="scss">
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  max-width: 100vw;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

body{
  background-color: #344b5c;
}

.container{
  width: 35%;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  text-align: center;

  background-color: #3c676a;
}

.logo{
  background-image: url('./assets/logo.png');
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  width: 100%;
  height: 200px;
}

.title{
  color: #41b883;
  margin: 1rem 0;
  text-align: center;
}

.render_div{
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  
  .btn{
    width: 24%;
  }
}

.line{
  margin-top: 1.5rem;
  height: 1px;
  width: 100%;
  background-color: white;
}

ul{
  list-style: none;
  text-align: left;
  
  margin: 1rem 0;

  li{
    background-color: #41b883;
    font-size: 0.85rem;
    text-align: center;
    color: white;
    padding: 1rem;
    margin: 0.5rem 0;
  }
}

.btn{
  width: 100%;
  margin-top: 1rem;
  padding: 1rem 0;
  background-color: #41b883;
  color: white;
  border: none;
  cursor: pointer;
  transition: 0.2s ease;

  &:hover{
    background-color: #349469;
  }
  
}

</style>
