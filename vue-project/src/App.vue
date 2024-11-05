<script setup>
import { ref } from 'vue';
import { provide } from 'vue';
import Producte from './components/Producte.vue';

const orderName= ref('') 
const menu=[
  { name: "Hamburger 🍔.", price: 5 },
  { name: "Cheeseburger 🧀", price: 6 },
  { name: "Impossible Burger 🥕", price: 7 },
  { name: "Fries 🍟", price: 2 }
  ]
  const currency= ref('€')
  provide("currency", currency)
  const orderList=ref([])
  const gestionarLlista=(producte)=>{
    orderList.value.push(producte)
    const alertText=orderList.value.join(",")
    alert(alertText)
  }
</script>

<template>
 <main>
  <h1>{{ orderName }}</h1>
  <input type="text" v-model="orderName" placeholder="Command name"/>
  <br/>
  <br/>
  <label>
    Currency
    <select v-model="currency">
      <option value="€">Euro</option>
      <option value="$">Dollar</option>
    </select>
  </label>

  <ul>
    <Producte v-for="producte in menu" :key="producte.name" :product-name="producte.name" :product-price="producte.price" 
    @enviarProducte="gestionarLlista"/>
  </ul>


 </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
