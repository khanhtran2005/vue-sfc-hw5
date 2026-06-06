<template>
  <section class="card">
    <h2>新增奶茶價格紀錄</h2>

    <form @submit.prevent="submitForm" class="form">
      <div class="form-group">
        <label>飲料名稱</label>
        <input
          v-model="drinkName"
          type="text"
          placeholder="例如：珍珠奶茶"
        >
      </div>

      <div class="form-group">
        <label>價格</label>
        <input
          v-model.number="price"
          type="number"
          min="1"
          placeholder="例如：55"
        >
      </div>

      <div class="form-group">
        <label>日期</label>
        <input
          v-model="date"
          type="date"
        >
      </div>

      <button type="submit">加入紀錄</button>
    </form>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add-item'])

const drinkName = ref('')
const price = ref('')
const date = ref(new Date().toISOString().slice(0, 10))

const submitForm = () => {
  if (!drinkName.value || !price.value || !date.value) {
    alert('請完整輸入飲料名稱、價格與日期')
    return
  }

  const newItem = {
    id: Date.now(),
    name: drinkName.value,
    price: price.value,
    date: date.value
  }

  emit('add-item', newItem)

  drinkName.value = ''
  price.value = ''
  date.value = new Date().toISOString().slice(0, 10)
}
</script>

<style scoped>
.card {
  background: white;
  padding: 24px;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(124, 45, 18, 0.08);
  margin-bottom: 24px;
}

h2 {
  margin-top: 0;
  color: #7c2d12;
}

.form {
  display: grid;
  gap: 16px;
}

.form-group {
  display: grid;
  gap: 8px;
}

label {
  font-weight: 700;
  color: #7c2d12;
}

input {
  padding: 12px;
  border: 1px solid #fed7aa;
  border-radius: 12px;
  font-size: 16px;
}

button {
  border: none;
  padding: 12px 18px;
  border-radius: 12px;
  background: #ea580c;
  color: white;
  font-size: 16px;
  font-weight: 700;
  cursor: pointer;
}

button:hover {
  background: #c2410c;
}
</style>