<template>
  <div >
    <div>
    <h3>Select States</h3>
    <br/><br/>
    <span>State  </span>
    <select class="form-control" v-model="stateSelected">
      <option value selected disabled>Choose</option>
      <option v-for="state in states" :value="state.id" :key="state.id" >{{ state.name }}</option>
    </select>
  </div><br>
    <div>
      <span>City  </span>
    <select class="form-control" v-model="citySelected" >
      <option value selected disabled>Choose</option>
      <option v-for="(city,i) in cities[stateSelected]" :value="city" :key="i">{{ city }}</option>  
    </select>
  </div><br>
  <button>Submit</button>
  <button @click="clear">Clear</button>
  </div>
  
</template>

<script>
export default {
  name: "Products",
  data() {
    return {
      states: [
        { name: "Odishsa", id: 1 },
        { name: "Maharastra", id: 2 },
        { name: "Telangana", id: 3 },
        { name: "Tamil Nadu", id: 4 },
        { name: "West Benagl", id: 5 },
        { name: "Karnataka", id: 6 },
      ],
cities:{
      1: ["Cuttack","Bhubnesswar", "Puri"],

      2: ["Mumbai","Pune", "Nagpur"],

      3: ["Hyderabad","Secudrabad", "Warangal"],

      4: ["Chennai","Coimbatore", "Madurai"],

      5: ["Kolkata","Khadakpur", "Durgapur"],

      6: ["Bangalore","Mysore", "Mangalore"]
},
      stateSelected: '',
      citySelected: ''
    };
  },
  methods: {
    clear() {
      this.stateSelected = null,
      this.citySelected= null
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
