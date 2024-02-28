<script>
import { ref } from "vue";

export default {
  setup() {
    const count = ref(0);
    const handleChange = (type) => {
      type === 'inc' ? count.value++ : count.value > 0 && count.value--;
    };
    return {
      count,
      handleChange,
    };
  },
};
</script>

<template>
  <div>
    <p>The value is: {{ count }}</p>
    <div class="button-container">
      <button @click="handleChange('inc')">Increment</button>
      <button @click="handleChange('dec')">Decrement</button>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  button {
    height: 50px;
    width: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
.button-container {
  display: flex;
  gap: 10px;
  justify-content: space-between;
}
p {
  text-align: center;
}
</style>
