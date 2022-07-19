<template>
  <h2 class="text-[2vw]">Filtered{{ filteredItems }}</h2>
  <h2 class="text-[3vw]">Prices{{ ItemPrices }}</h2>
  <h2 class="text-[4vw]">Names{{ ItemNames }}</h2>
  <h2 class="text-[4vw]">foundItem{{ foundItem }}</h2>
  <h2 class="text-[4vw]">
    is there inexspensive items {{ hasInexpensiveItems }}
  </h2>
  <h2 class="text-[4vw]">total price for all items {{ total }}</h2>
  <h2 class="text-[4vw]">includes {{ includesTwo }}</h2>
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
    { name: "crazy lamp", price: 240 },
  ];

  const items = [1, 3, 5, 7, 8];

  // using filters
  const filteredItems = navigation.filter((item) => {
    return item.price <= 100;
  });

  // using maps
  const ItemPrices = navigation.map((item) => {
    return item.price;
  });

  const ItemNames = navigation.map((item) => {
    return item.name;
  });

  // using the find method
  const foundItem = navigation.find((item) => {
    return item.name === "crazy lamp";
  });

  // using the for each

  navigation.forEach((item) => {
    console.log("inside the for each", item.name);
  });

  // using the sum
  const hasInexpensiveItems = navigation.some((item) => {
    return item.price <= 100;
  });

  // reduce
  const total = navigation.reduce((currenTotal, item) => {
    return item.price + currenTotal;
  }, 0);

  //includes

  const includesTwo = items.includes(2);

  console.log("filtered items", filteredItems);

  export default {
    setup() {
      return {
        navigation,
        filteredItems,
        ItemNames,
        ItemPrices,
        foundItem,
        hasInexpensiveItems,
        total,
        items,
        includesTwo,
      };
    },
  };
</script>

<style></style>
