<template>
  <div class="test">
    <input type="text" v-model="title"><br>
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else="showName">nobody</p>
    <ul>
      <li v-for="item in items">
        {{item.title}}
      </li>
    </ul>

    <button v-on:click="greet">Greeting</button>
    <br/>
    <input type="text" v-on:keyup="pressKey">
    <hr/>
    <label>First Name:</label> <input type="text" v-model="user.firstName">
    <br/>
    <label>Last Name: </label> <input type="text" v-model="user.lastName">
    <br/>
    <h3>
      {{fullName}}
    </h3>
    <h2>{{msg}}</h2>
  </div>

</template>

<script>
export default{
  name: 'test2',
  props: {
    msg: {
      type: String,
      default: 'Foobar'
    }
  },
  data (){
    return {
      title : 'Hello World',
      user : {
        firstName : 'John',
        lastName : 'Doe'
      },
      showName : true,
      items : [
        {title : "itemOne"},
        {title : "itemTwo"},
        {title : "itemThree"}
      ]
    }
  },
  methods: {
    greet: function(){
      alert("hello, you!");
    },
    pressKey: function(e){
      console.log(e.target.value);
    }
  },
  computed: {
    fullName: function(){
      return this.user.firstName + ' ' + this.user.lastName;
    }
  }

}
</script>

<style scoped>

</style>
