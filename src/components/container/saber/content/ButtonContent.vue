<template>
  <button @click="logout" class="bg-gray-750 border border-light text-gray-500 font-bold text-sm flex items-center justify-center py-3 px-5 w-full transition-colors duration-150 ease-in-out hover:bg-yellow-400 hover:text-yellow-800 focus:bg-yellow-300 focus:outline-none focus:text-yellow-800">
    <svg class="w-4 h-4 mr-3 opacity-75" viewBox="0 0 512 512" fill="currentColor">
      <path d="M0 168v-16c0-13.255 10.745-24 24-24h381.97l-30.467-27.728c-9.815-9.289-10.03-24.846-.474-34.402l10.84-10.84c9.373-9.373 24.568-9.373 33.941 0l82.817 82.343c12.497 12.497 12.497 32.758 0 45.255l-82.817 82.343c-9.373 9.373-24.569 9.373-33.941 0l-10.84-10.84c-9.556-9.556-9.341-25.114.474-34.402L405.97 192H24c-13.255 0-24-10.745-24-24zm488 152H106.03l30.467-27.728c9.815-9.289 10.03-24.846.474-34.402l-10.84-10.84c-9.373-9.373-24.568-9.373-33.941 0L9.373 329.373c-12.497 12.497-12.497 32.758 0 45.255l82.817 82.343c9.373 9.373 24.569 9.373 33.941 0l10.84-10.84c9.556-9.556 9.341-25.113-.474-34.402L106.03 384H488c13.255 0 24-10.745 24-24v-16c0-13.255-10.745-24-24-24z"/>
    </svg>
    <span>登出当前账户</span>
  </button>
</template>

<script>
export default {
  name: "ButtonContent"
}
</script>

<script setup>
import {useCookies} from "vue3-cookies";
import {useRouter} from "vue-router";
import pubsub from "pubsub-js";

const router = useRouter();
const {cookies} = useCookies();

function logout() {
  cookies.remove('username', '/')
  cookies.remove('authorization')
  pubsub.publish('changeSaberCondition')
  router.replace('login')
}
</script>