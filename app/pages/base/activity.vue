<script setup>
const acts = await $fetch(`${process.env.NUXT_PUBLIC_API_URL}/api/activity?status=1&limit=6`)
</script>

<template>
  <div class="activity-page">
    <h1 class="page-title">กิจกรรมภายในวิทยาลัย</h1>

    <div class="activity-grid">
      <div
        v-for="act in acts.data"
        :key="act.activity_id"
        class="activity-card"
      >
        <img :src="act.thumbnail" alt="pic" class="activity-img" />
        <h2 class="activity-title">{{ act.activity }}</h2>
        <p class="activity-detail">{{ act.detail }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.activity-page {
  padding: 2rem;
  background-color: #111;
  color: white;
}

.page-title {
  font-size: 1.8rem;
  color: #3b82f6;
  margin-bottom: 2rem;
  text-align: center;
}

.activity-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.activity-card {
  background-color: #222;
  padding: 1.5rem;
  border-radius: 1rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  transition: transform 0.2s ease;
}

.activity-card:hover {
  transform: translateY(-5px);
}

.activity-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 0.5rem;
  margin-bottom: 1rem;
}

.activity-title {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.activity-detail {
  font-size: 0.95rem;
  line-height: 1.6;
}
</style>