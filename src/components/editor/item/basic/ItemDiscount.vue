<template>
  <button :class="cache.clickable" @click="changeDiscountShowCaseCondition" class="item-count">
    <span>折扣</span>
  </button>
  <transition name="item">
    <div v-show="moduleCondition.discountShowCase" class="item-discount pointer-events-none grid grid-cols-2 my-auto transition-all ease-in-out duration-200 z-50">
      <div v-show="cache.categories.crate" class="discount-inner pointer-events-auto">
        <h3 class="text-white font-bold">额度 (%)</h3>
        <input v-model="cache.discount" maxlength="2" type="number" placeholder="78%" class="appearance-none"/>
      </div>
      <div v-show="!cache.categories.crate" class="discount-inner c pointer-events-auto">
        <h3 class="text-white font-bold ml-8">额度 (%)</h3>
        <div class="inline-flex items-center">
          <div class="font-bold m-2">1x</div>
          <input v-model="cache.multiDiscount.x1" maxlength="2" type="number" placeholder="98%" class="appearance-none"/>
        </div>
        <div class="inline-flex items-center">
          <div class="font-bold m-2">5x</div>
          <input v-model="cache.multiDiscount.x5" maxlength="2" type="number" placeholder="92%" class="appearance-none"/>
        </div>
        <div class="inline-flex items-center">
          <div class="font-bold m-2">10x</div>
          <input v-model="cache.multiDiscount.x10" maxlength="2" type="number" placeholder="88%" class="appearance-none"/>
        </div>
        <div class="inline-flex items-center">
          <div class="font-bold m-2">20x</div>
          <input v-model="cache.multiDiscount.x20" maxlength="2" type="number" placeholder="78%" class="appearance-none"/>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "ItemDiscount"
}
</script>

<script setup>
const props = defineProps(['moduleCondition', 'cache']);

const moduleCondition = props.moduleCondition
const cache = props.cache

function changeDiscountShowCaseCondition() {
  moduleCondition.discountShowCase = !moduleCondition.discountShowCase
  moduleCondition.categoryShowCase = false
}
</script>

<style>
.editor .item-count {
  font-size: 1.25rem;
  grid-column: 2;
  grid-row: 1;
}

.editor .item-discount {
  grid-column: 2;
  grid-row: 2;
}
.item-discount .discount-inner {
  grid-column: 2;
}
.item-discount .discount-inner.c {
  margin-top: 0.4rem;
}
</style>