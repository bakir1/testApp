<template>
 <fragment>
  <h1>Heros : {{ Heros.length }} </h1>
   <ul>
      <li v-for:="(hero, index) in Heros" :key="index">
      <div> {{ hero.name }} <button v-on:click="remove(index)">x</button>
      </div> 
      </li>
   </ul>
   <form @submit.prevent="addHero">
     <input v-model="newHero" placeholder="Type Hero Name" />
     <button type="submit">Add Hero</button>
   </form>
 </fragment>
</template>

<script>
export default {
  methods: {
    addHero(){
    if(this.newHero != ""){
    this.Heros.push({ name: this.newHero });
    this.newHero = "";
     }
    },
      remove(index){
    this.Heros = this.Heros.filter((hero, i) => i != index);
   },
  },
  data() {
    return {
      newHero: "",
      Heros: [
        {name: "SuperWomen"},
        {name: "Flash"},
        {name: "Batman"},
        {name: "Arrow"},
      ],

    };
  },
};
</script>