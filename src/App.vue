<template>
  <div class="container">
    <div class="calculator">
      <div class="input">
        <p class="input-text">{{ screen }}</p>
        <div>
          <input @click ="clear()" type="button" value="AC">
          <input @click="undo()" type="button" value="undo">
          <input type="button" value="%">
          <input @click="append('/')" class="sign" type="button" value="/">
        </div>
        <div>
          <input @click ="append('7')" type="button" value="7">
          <input @click ="append('8')" type="button" value="8">
          <input @click ="append('9')" type="button" value="9">
          <input @click ="append('*')" class="sign" type="button" value="*">
        </div>
        <div>
          <input @click ="append('4')" type="button" value="4">
          <input @click ="append('5')" type="button" value="5">
          <input @click ="append('6')" type="button" value="6">
          <input @click ="append('-')" class="sign" type="button" value="-">

        </div>
        <div>
          <input @click ="append('1')" type="button" value="1">
          <input @click ="append('2')" type="button" value="2">
          <input @click ="append('3')" type="button" value="3">
          <input @click="append('+')" class="sign" type="button" value="+">

        </div>
        <div>
          <input @click ="append('0')" class="zero" type="button" value="0">
          <input @click="append('.')" type="button" value=".">
          <input @click="calculation()" class="sign" type="button" value="=">
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default{
  data() {
    return {
      screen: '',
    }
  },
  methods: {
    append(value){
      this.screen += value.toString();
    },
    clear(){
      this.screen = '';
    },
    undo(){
      this.screen = this.screen.slice(0, this.screen.length - 1);
    },
    calculation(){
      this.screen = eval(this.screen);
    }
  },
}
</script>


<style>
input{
  width: 50px;
  height: 50px;
  border: 0;
  border-radius: 5px;
  margin-top: 5px;
  margin-right: 5px;
  cursor: pointer;
  font-size: 20px;
  font-family:Arial, Helvetica, sans-serif;
}
.zero {
  width: 105px;
}
.container{
  width: 250px;
  height: 350px;
  background-color: rgb(69, 69, 69);
  border-radius: 15px;
}
.calculator{
  margin-left: 15px;
}
.input-text{
  font-size: 30px;
  margin-bottom: 0;
  height: 50px;
  width: 210px;
  border-radius: 10px;
  background-color: rgb(215, 215, 215);
  font-family: Arial, Helvetica, sans-serif;
}
.sign{
  background-color:orange;
}
</style>
