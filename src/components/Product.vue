<template>
  <div class="m-auto">
    <div class="card w-50 m-3">
      <img
        :src="image"
        :alt="description"
        class="card-img-top"
        height="400px"
        width="120px"
      />
      <div class="card-body">
        <h4 class="card-header">{{ title }}</h4>
        <p class="card-text">{{ description }}</p>
        <p class="card-text">£{{ price }}</p>
      </div>
      <router-link :to="{name: 'ProductItem', params: {id: id}}">
        <button class="btn btn-primary btn-block">
          View
        </button>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    title: String,
    description: String,
    image: String,
    price: Number,
    id: Number
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
