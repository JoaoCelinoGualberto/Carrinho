<template>
  <div>
    <div class="p-3" v-for="item in this.$attrs" :key="item.id">
      <div class="card-bg--color">
        <div class="d-flex flex-row align-content-center align-items-center">
          <img class="img-size bg-white" :src="item.imageUrl" alt="" />
          <div class="ml-3">
            <p class="product-name">
              {{ item.name }}
            </p>
            <p class="product-name--dark">
              R$: {{ item.priceTags[0].value * -1 }}
            </p>
          </div>
        </div>
        <button v-on:click.stop.prevent="send(item)" class="btn ml-2 mb-2">
          <img
            class="car-size"
            src="../assets/img/adicionar-carrinho-de-compras.svg"
            alt=""
          />
          <span class="it__shelf--text"> Adicionar ao carrinho </span>
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    send: function (product) {
      this.$emit("carrinho", { payload: product });
    },
  },
};
</script>

<style scoped>
.img-size {
  max-width: 175px;
}
.car-size {
  width: 20px;
  margin: 0 0 10px 0px;
}

.card-bg--color {
  border: 0.1px solid #d1d8e5;
  border-radius: 5px;
}

.btn {
  background: #00fa9a;
}
</style>