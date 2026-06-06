<template>
  <header class="header">
    <p class="tag">🧋 奶茶觀測指數</p>
    <h1>通貨膨脹奶茶觀測站</h1>
    <p class="subtitle">
      透過記錄奶茶價格，觀察生活中的通貨膨脹現象。
    </p>
  </header>
</template>

<style scoped>
.header {
  text-align: center;
  padding: 40px 24px;
  background: linear-gradient(135deg, #fff7ed 0%, #ffedd5 100%);
  border-radius: 24px;
  margin-bottom: 32px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05), 0 4px 6px -2px rgba(0, 0, 0, 0.025);
  border: 1px solid rgba(254, 215, 170, 0.5);
  transition: all 0.3s ease;
}

.header:hover {
  transform: translateY(-4px);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.05), 0 10px 10px -5px rgba(0, 0, 0, 0.02);
}

.tag {
  display: inline-block;
  padding: 6px 16px;
  background: white;
  border-radius: 999px;
  color: #ea580c;
  font-weight: 700;
  font-size: 14px;
  margin-bottom: 16px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  border: 1px solid #ffedd5;
  letter-spacing: 1px;
}

h1 {
  margin: 0;
  font-size: 38px;
  color: #7c2d12;
  font-weight: 800;
  letter-spacing: 0.5px;
  text-shadow: 1px 1px 0 rgba(255, 255, 255, 0.6);
}

.subtitle {
  margin-top: 16px;
  color: #9a3412;
  font-size: 18px;
  line-height: 1.6;
  font-weight: 500;
  opacity: 0.9;
}
</style>