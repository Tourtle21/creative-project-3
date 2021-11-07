<template>
<div>
  <form class="pure-form">
        <p>Name:</p>
        <input v-model="name" />
        <p>Location:</p>
        <input v-model="location" />
        <p>Picture URL</p>
        <input v-model="url" />
        <p>Country</p>
        <input v-model="country" />
        <button @click.prevent='addNewLocation' id='submit'>Create new Climbing Location</button>
      </form>
</div>
</template>

<script>
export default {
  name: 'Home',
  components: {

  },
  data() {
    return {
      name: '',
      location: '',
      url: '',
      country: ''
    }
  },
  methods: {
    addNewLocation() {
      this.$root.$data.products.push({name:this.name, location:this.location, url:this.url, country:this.country})
      this.name = '';
      this.location = '';
      this.url = '';
      this.country = '';
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

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}
#submit {
  display: block;
  margin-top: 20px;
  padding: 10px;
}

form {
  width: 100%;
  border-bottom: none;
}

input {
  font-size: 20px;
  border: 1px solid black !important;
  border-bottom: none;
  width: 20%;
  height: 40px;
}
</style>