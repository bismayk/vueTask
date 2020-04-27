<template>
  <div >
    <div>
    <h1>Product Deatils</h1>

    <span>Category  </span>
    <select class="form-control" v-model="categorySelected">
      <option value selected disabled>Choose</option>
      <option v-for="product in products" :value="product.id" :key="product.id" >{{ product.name }}</option>
    </select>
  </div><br>
    <div>
      <span>Product  </span>
    <select class="form-control" v-model="itemSelected" >
      <option value selected disabled>Choose</option>
      <option v-for="item in items[categorySelected]" :value="item.price" :key="item.name">{{ item.name }}</option>  
    </select>
  </div><br>
  <span>Quantity</span>
  <input class="form-control" v-model.number="amount" type="number" placeholder=" Enter Quantity">
  <div>
    <p>Total price: {{totalPrice}} </p>
  </div>
  <button :disabled="!amount" @click="findSum">Submit</button>
  <button @click="clear">Clear</button>
  </div>
  
</template>

<script>
export default {
  name: "Products",
  data() {
    return {
      products: [
        { name: "Electronics", id: 1 },
        { name: "Grocery", id: 2 }
      ],
items:{
      1: [
        {name: "Television", price: 20000},
        {name: "Laptop", price: 30000},
        {name: "Phone", price: 10000}
      ],

      2: [
        {name: "soap", price: 40},
        {name: "powder", price: 90}
      ]
},
      categorySelected: '',
      itemSelected: '',
      amount: '',
      totalPrice: ''
    };
  },
  methods: {
    findSum() {
      this.totalPrice = this.amount * this.itemSelected
    },
    clear() {
      this.categorySelected = null,
      this.itemSelected= null,
      this.amount= null,
      this.totalPrice= null
    }

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
