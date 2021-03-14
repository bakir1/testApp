<template>
 <fragment>
  <h1>Heros</h1>
   <ul>
      <li v-for:="(hero, index) in Heros" :key="index">
      {{ hero.name }} 
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
  },
  removeHero(){

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