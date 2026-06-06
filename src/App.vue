<template>
  <main class="container">
    <AppHeader />

    <section class="intro">
      <h2>網站功能說明</h2>
      <p>
        本網站把「通貨膨脹」這個概念轉換成生活化的奶茶價格紀錄。
        使用者可以新增不同日期的奶茶價格，並透過表格觀察價格變化。
      </p>
    </section>

    <AddRecordForm @add-item="handleAddItem" />

    <PriceTable :items="priceList" />
  </main>
</template>

<script setup>
import { ref } from 'vue'
import AppHeader from './component/AppHeader.vue'
import AddRecordForm from './component/AddRecordForm.vue'
import PriceTable from './component/PriceTable.vue'

const priceList = ref([
  {
    id: 1,
    name: '珍珠奶茶',
    price: 45,
    date: '2023-06-01'
  },
  {
    id: 2,
    name: '珍珠奶茶',
    price: 50,
    date: '2024-06-01'
  },
  {
    id: 3,
    name: '珍珠奶茶',
    price: 55,
    date: '2025-06-01'
  }
])

const handleAddItem = (newItem) => {
  priceList.value.push(newItem)
}
</script>

<style scoped>
.container {
  max-width: 960px;
  margin: 0 auto;
  padding: 32px 20px;
}

.intro {
  background: white;
  padding: 24px;
  border-radius: 20px;
  margin-bottom: 24px;
  box-shadow: 0 10px 30px rgba(124, 45, 18, 0.08);
}

.intro h2 {
  color: #7c2d12;
  margin-top: 0;
}

.intro p {
  color: #9a3412;
  line-height: 1.8;
}
</style>

<style>
body {
  margin: 0;
  background: #fff7ed;
  font-family: Arial, "Noto Sans TC", sans-serif;
}
</style>