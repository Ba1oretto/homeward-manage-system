<template>
  <div class="render">
    <div class="layer-regular"/>
    <div class="layer-hover"/>
  </div>
</template>

<script>
export default {
  name: "PostAnimation"
}
</script>

<style scoped>
.categories .category.category-article .render div {
  background-size: 240px auto;
  background-position: bottom 0 left 10px;
}

.categories .category.category-article .render .layer-regular {
  background-image: url(./src/assets/images/homepage/extras.png);
}

@screen lg {
  .categories .category.category-article .render div {
    background-size: 240px auto;
    background-position: bottom 10px left 30px;
  }
}

.categories .category.category-article .render .layer-hover {
  background-image: url(./src/assets/images/homepage/extras_hover.png);
}

@screen lg {
  .categories .category.category-article .render div {
    background-size: 240px auto;
    background-position: bottom 10px left 30px;
  }
}
</style>