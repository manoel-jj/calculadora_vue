<script setup>
  import { ref, computed } from 'vue'

  const number1 = ref('')
  const number2 = ref('')
  const operator = ref('+')

  const calculate = () => {
    let result

    switch (operator.value) {
      case '+':
        result = Number(number1.value) + Number(number2.value)
        break
      case '-':
        result = Number(number1.value) - Number(number2.value)
        break
      case '*':
        result = Number(number1.value) * Number(number2.value)
        break
      case '/':
        result = Number(number1.value) / Number(number2.value)
        break
      default:
        result = 0
    }

    return result
  }

  const result = computed(() => {
    return calculate()
  })
</script>

<template>
  <container>
  <div class="calculator">
    <input class="calculator-display" type="number" v-model="number1" @input="calculate">
    <select class="operador" v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input class="calculator-display" type="number" v-model="number2" @input="calculate">
    <p>{{ result }}</p>
  </div>
</container>
</template>





