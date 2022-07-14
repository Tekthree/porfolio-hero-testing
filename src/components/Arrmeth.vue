<template>
  <h2 class="text-[2vw]">Filtered{{filteredItems}}</h2>
  <h2 class="text-[3vw]">Prices{{ItemPrices}}</h2>
  <h2 class="text-[4vw]">Names{{ItemNames}}</h2>
  <h2 class="text-[4vw]">foundItem{{foundItem}}</h2>
  
  
</template>

<script>
  const navigation = [
    { name: "WORK", price: 100 },
    { name: "Bike", price: 200 },
    { name: "Tv", price: 10 },
    { name: "Book", price: 5 },
    { name: "Computer", price: 500 },
    { name: "laptop", price: 1000 },
    { name: "toaster", price: 25 },
    { name: "crazy lamp", price: 240 }
  ];


  // using filters
  const filteredItems = navigation.filter((item) => {
    return item.price <= 100
  })

  // using maps
  const ItemPrices = navigation.map((item)=>{
    return item.price
  })

  const ItemNames = navigation.map((item)=>{
    return item.name
  })

  // using the find method
  const foundItem = navigation.find((item)=>{
    return item.name === 'crazy lamp'

  })

  console.log(filteredItems)

  export default {
    setup() {
      return {
        navigation,
        filteredItems,
        ItemNames,
        ItemPrices,
        foundItem,
      };
    },
  };
</script>

<style></style>
