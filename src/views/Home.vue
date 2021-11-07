<template>
<div>
  <div class="wrapper hero-wrapper">
    <img id='hero' src='/images/hero.jpg' />
  </div>
  <div class="text-wrapper">
    <h1 id='question'>Looking for a place to climb?</h1>
    <p>All of the different rock climbing places have been documented to make sure that no matter where you are you can find a fun place to climb. Look down there to find the place or use the search bar.</p>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Home',
  components: {
    ProductList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    products() {
    return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
  },
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.text-wrapper {
  padding: 50px;
}
.hero-wrapper {
  height: 400px;
  overflow: hidden;
}
#question {
  text-align: center;
}
.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}



input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
#hero {
  width: 100%;
  min-height: 400px;
}
</style>