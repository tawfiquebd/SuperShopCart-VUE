<template>
  <div id="app">

    <navbar></navbar>

    <div class="container pt-2">
      <div class="row">
        <div class="col-md-9">
            <inventory @newItemAdded="addCartItem" :items="items"></inventory>
        </div>
        <div class="col-md-3">
          <div class="row">
            <div class="col-md-12">
              <cart :items="carts"></cart>
            </div>
          </div>
        </div>
      </div>
    </div>
      
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Cart from './components/Cart'
import Inventory from './components/Inventory'
import data from './data.js'

export default {
  components: {
    Navbar,
    Cart,
    Inventory
  },
  data() {
    return {
      items: [],
      carts: [
        {
          id: 1,
          title: 'Motorbike',
          price: '100',

        }
      ],
    }
  },
  mounted() {
    this.items = data
  },
  methods: {
    addCartItem(item) {
      this.carts.push(item);
    }
  }
}
</script>

<style>

</style>
