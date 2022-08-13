<template>
  <div>
    <div><input type="number" ref="price_input" /></div>
    <button @click="update_max_price">filter price</button>
    <section class="menu_container">
      <div v-for="(item, index) in items" :key="index">
        <div v-if="item[`price`] <= max_price">
          <h1>{{ item[`title`] }}</h1>
          <p>{{ item[`price`] }}</p>
          <p>{{ item[`description`] }}</p>
          <img :src="item[`image_url`]" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {

methods: {
  update_max_price() {
    this.max_price = this.$refs[`price_input`][`valueAsNumber`];
  }
},


  data() {
    return {
      max_price: 10,
      items: [
        {
          title: `item one`,
          price: 7,
          description: `description of food`,
          image_url: `https://images.unsplash.com/photo-1657299170936-0531a116c87c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80`,
        },
        {
          title: `item two`,
          price: 12,
          description: `description of food`,
          image_url: `https://images.unsplash.com/photo-1657299170936-0531a116c87c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80`,
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>