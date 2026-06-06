<template>
  <section class="card">
    <h2>奶茶價格紀錄表</h2>

    <table v-if="items.length > 0">
      <thead>
        <tr>
          <th>日期</th>
          <th>飲料名稱</th>
          <th>價格</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="item in items" :key="item.id">
          <td>{{ item.date }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.price }} 元</td>
        </tr>
      </tbody>
    </table>

    <p v-else class="empty">
      目前尚無紀錄，請先新增一筆奶茶價格資料。
    </p>
  </section>
</template>

<script setup>
defineProps({
  items: {
    type: Array,
    required: true
  }
})
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

table {
  width: 100%;
  border-collapse: collapse;
}

th {
  background: #ffedd5;
  color: #7c2d12;
}

th,
td {
  padding: 14px;
  border-bottom: 1px solid #fed7aa;
  text-align: left;
}

.empty {
  color: #9a3412;
  background: #fff7ed;
  padding: 16px;
  border-radius: 12px;
}
</style>