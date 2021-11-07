<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
      <form class="pure-form">
        <i class="fas fa-search"></i><input v-model="searchText" />
      </form>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      searchText: ''
    }
  },
  computed: {
    products() {
      if (!this.searchText) {
        return this.$root.$data.products;
      } else {
        return this.$root.$data.products.filter(product => product.name.toLowerCase().includes(this.searchText.toLowerCase()));
      }
    }
  },
  methods: {
    select(country) {
      this.country = country;
    }
  }
}
</script>

<style>
form {
  display: table;
  width: 100%;
  border-bottom: 2px solid black;
}

/* i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
} */

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>