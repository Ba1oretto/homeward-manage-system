<template>
  <div class="container-body homepage row-start-1 col-start-1">
    <div class="container mx-auto">
      <bread-crumb/>
      <router-view/>
    </div>
  </div>
</template>

<script>
import BreadCrumb from "./body/BreadCrumb.vue";

export default {
  name: "ContainerBody",
  components: {BreadCrumb}
}
</script>

<script setup>

import EditorPanel from "../../pages/EditorPanel.vue";
</script>