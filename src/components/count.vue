<script setup lang="ts">
import { ref, computed } from 'vue'

const count = ref(0)

const doubled = computed(() => count.value * 2)
</script>

<template>
  <main class="page">
    <div class="card">
      <div class="sparkle">✦</div>

      <p class="label">VERENAS COUNTER</p>
      <h1>Counter</h1>

      <div class="number">
        {{ count }}
      </div>

      <p class="doubled">
        Doppelt so viel:
        <strong>{{ doubled }}</strong>
      </p>

      <div class="buttons">
        <button @click="count--">−</button>
        <button @click="count++">+</button>
      </div>
    </div>
  </main>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.page {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background:
    radial-gradient(circle at 15% 20%, #ff8fbd 0%, transparent 30%),
    radial-gradient(circle at 85% 80%, #ff4f9a 0%, transparent 30%),
    #fff5f9;
}

.card {
  width: 370px;
  padding: 45px 40px;
  text-align: center;
  background: rgba(255, 255, 255, 0.88);
  border: 1px solid #ffffff;
  border-radius: 30px;
  box-shadow:
    0 25px 60px rgba(221, 56, 126, 0.18),
    0 5px 20px rgba(0, 0, 0, 0.05);
  backdrop-filter: blur(15px);
}

.sparkle {
  width: 48px;
  height: 48px;
  margin: 0 auto 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background: linear-gradient(135deg, #ff72ad, #ff3f8f);
  color: white;
  font-size: 23px;
  box-shadow: 0 8px 25px rgba(255, 63, 143, 0.3);
}

.label {
  margin: 0;
  color: #e9438b;
  font-size: 11px;
  font-weight: bold;
  letter-spacing: 3px;
}

h1 {
  margin: 8px 0 20px;
  font-size: 30px;
}

.number {
  margin: 25px 0;
  font-size: 95px;
  font-weight: bold;
  line-height: 1;
  background: linear-gradient(135deg, #ff72ad, #e92f7d);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  transition: 0.2s;
}

.doubled {
  margin-bottom: 30px;
  color: #8f6c7a;
}

.doubled strong {
  color: #e9438b;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 15px;
}

button {
  width: 65px;
  height: 52px;
  border: 2px solid #ffd1e2;
  border-radius: 16px;
  background: white;
  color: #e9438b;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.2s;
}

button:hover {
  background: #ff4f9a;
  border-color: #ff4f9a;
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(255, 79, 154, 0.3);
}

button:active {
  transform: translateY(0);
}
</style>