<template>
  <div class="col-md-6">
    <div class="panel panel-success">
      <div class="panel-heading">
        <h3 class="panel-title">
          {{ stock.name }}
          <small>(Price: {{ stock.price }})</small>
        </h3>
      </div>
      <div class="panel-body">
        <div class="pull-left">
          <input type="number"
          class="form-control"
          placeholder="Quantity"
          v-model="quantity" >
        </div>
        <div class="pull-right">
          <button
          :disabled="quantity <= 0" 
          class="btn btn-success" 
          @click="buyStock">Buy</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['stock'],
    data() {
      return {
        quantity: 0
      }
    },
    methods: {
      buyStock() {
        console.log("Buy Stock!");
        const order = {
          stockId: this.stock.id,
          stockPrice: this.stock.price,
          quantity: parseInt(this.quantity)
        };
        console.log("The order is: ", order);
        this.quantity = 0;
      }
    }
  }
</script>

<style>

</style>
