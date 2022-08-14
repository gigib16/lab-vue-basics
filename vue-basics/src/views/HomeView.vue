<template>

<h1> This is Home</h1>
<input type="number" v-model="num1"/>
<input type="number" v-model="num2"/>
<input type="text" v-model="color"/>
<div :style="myColor">Cambio de color</div>
<p> {{ result }} </p>
<button @click="result">Calcular</button>
<button @click="change">Cambiar de color</button>

<h2 v-if="show">Solo mostrarlo si true</h2>
<h2 v-else> Oh no</h2>

<h2 v-show="show">Solo mostrarlo si true</h2>

<div v-if="type === 'A'">A</div>
<div v-else-if="type === 'B'">A</div>
<div v-else-if="type === 'C'">A</div>
<div v-else>Not A/B/C</div>
<br>

<article>
  <button @click="hideUnhide" v-if="!signedIn">Log In</button>
  <button @click="hideUnhide" v-else>Log Out</button>
</article>
<br>

<div v-for="post in posts">
  <h2> {{post.title}} </h2>
  <p>{{post.description}}</p>
  <a :href="post.url">Click</a>

</div>

</template>

<script>

export default {  
  name: 'HomeView',
      data(){
        return {
          num1: 1,
          num2: 2,
          result: null,
          color: "",
          show: true,
          type: "A",
          signedIn:true,
          posts: [
            {
              id:1,
              title: "Título 1",
              description: "Descripción 1",
              url:"#",
            },
             {
              id:2,
              title: "Título 2",
              description: "Descripción 2",
              url:"#",
            },
             {
              id:3,
              title: "Título 3",
              description: "Descripción 3",
              url:"#",
            },
        ],
        };
      },

methods:{
  hideUnhide(){
    if (this.signedIn === false) {
    this.signedIn = true;}
    else { 
    this.signedIn = false
   }
}
},


      computed:{
        myColor (){
          return `background-color: ${this.color}`;
        },

      },

// methods: {},
     // computed: {
       // result(){
         // return this.num1 + this.num2;
       // },
      //},
//

mounted () {
this.result = this.num1 + this.num2;
},

  };

</script>
