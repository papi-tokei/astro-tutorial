<template>
  <div class="counter">
    <p v-if="!isValid">文字数は1以上10以下にしてください</p>
    <input type="text" v-model="message" />
    <button @click="submit" :disabled="!isValid">送信</button>
  </div>
</template>

<script lang="ts">
import { ref, computed } from "vue";
export default {
  setup() {
    const message = ref("");
    const isValid = computed(
      () => 0 < message.value.length && message.value.length <= 10
    );
    const submit = function (_data) {
      console.log(message.value);
    };
    return {
      isValid,
      message,
      submit,
    };
  },
};
</script>
