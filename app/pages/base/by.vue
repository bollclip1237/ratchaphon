<script setup>
const creators = [
  {
    name: 'ชื่อ : รัชพล สุขโต',
    role: 'รหัสนักศึกษา : 68319010014 | สทส.1/2',
    photo: '/Images/me.png',
    bio: '',
    tech: ['Vue', 'Nuxt', 'Tailwind CSS',],
    contact: 'IG: @hurakan.nt | FB: Ratchapon MB', 
  }
]
</script>

<template>
  <div class="by-page">
    <h1 class="page-title">ข้อมูลผู้จัดทำ</h1>

    <div class="creator-grid">
      <div v-for="person in creators" :key="person.name" class="creator-card">
        <img :src="person.photo" alt="creator photo" class="creator-img" />
        <h2 class="creator-name">{{ person.name }}</h2>
        <p class="creator-role">{{ person.role }}</p>
        <p class="creator-bio">{{ person.bio }}</p>

        <div class="tech-stack">
          <span v-for="tech in person.tech" :key="tech" class="tech-badge">{{ tech }}</span>
        </div>

        <p class="creator-contact">{{ person.contact }}</p>
        <p class="creator-date">จัดทำเมื่อ: 18/11/2568</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.by-page {
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

.creator-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.creator-card {
  background-color: #222;
  padding: 1.5rem;
  border-radius: 1rem;
  text-align: center;
  box-shadow: 0 0 10px rgba(0,0,0,0.5);
}

.creator-img {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border-radius: 50%;
  margin-bottom: 1rem;
  border: 2px solid #3b82f6;
}

.creator-name {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.creator-role {
  font-size: 1rem;
  color: #ccc;
  margin-bottom: 1rem;
}

.creator-bio {
  font-size: 0.95rem;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.tech-stack {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.tech-badge {
  background-color: #3b82f6;
  color: white;
  padding: 0.3rem 0.6rem;
  border-radius: 0.5rem;
  font-size: 0.8rem;
}

.creator-contact {
  font-size: 0.9rem;
  color: #aaa;
  margin-bottom: 0.5rem;
}

.creator-date {
  font-size: 0.8rem;
  color: #666;
}
</style>
