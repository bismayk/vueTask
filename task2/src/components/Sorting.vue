<template>
  <div>
    <h3>Products</h3>
    <button @click="sort">Sort by price</button>
    <br/><br/>
    <input type="radio" id="one" value="l2h" v-model="sortBy" />
    <label for="one">Ascending</label>
    <input type="radio" id="two" value="h2l" v-model="sortBy" />
    <label for="two">Descending</label>
    <br/>
    <br />
    <table>
      <tr>
        <th>Product</th>
        <th>Price</th>
      </tr>
      <tr v-for="(p,i) in products" :key="i">
        <td>{{p.name}}</td>
        <td>{{p.price}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "ProductList",
  data() {
    return {
      products: [
        { name: "Television", price: 20000 },
        { name: "Laptop", price: 30000 },
        { name: "Phone", price: 10000 },
        { name: "Soap", price: 40 },
        { name: "Powder", price: 90 },
        { name: "bag", price: 2000 },
        { name: "earphones", price: 600 },
        { name: "Table", price: 5000 }
      ],
      sortBy: ""
    };
  },
  methods: {
    sort() {
      if (this.sortBy == "l2h")
        this.products.sort(function(a, b) {
          return a.price - b.price;
        });
      else
        this.products.sort(function(a, b) {
          return b.price - a.price;
        });
    }
  }
};
</script>
<style>
</style>