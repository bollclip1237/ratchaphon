<template>
  <div class="layout">
    <header class="navbar">
      <nav class="nav-container">
        <!-- ซ้ายสุด: icon + ชื่อเว็บ -->
        <div class="logo-area">
          <span class="logo-icon">🌐</span>
          <span class="site-name">WEB-IT</span>
        </div>

        <!-- กลาง: เมนูหลัก -->
        <ul class="nav-center">
          <li><NuxtLink to="/">หน้าหลัก</NuxtLink></li>
          <li><NuxtLink to="/base/about">ข้อมูลบุคลากร</NuxtLink></li>
          <li><NuxtLink to="/base/student">ข้อมูลนักเรียน</NuxtLink></li>
        </ul>

        <!-- ขวาสุด: ข้อมูลผู้จัดทำ -->
        <div class="nav-right">
          <NuxtLink to="/base/by" class="by-link">ข้อมูลผู้จัดทำ</NuxtLink>
        </div>
      </nav>
    </header>
    <main>
      <slot />
    </main>
  </div>
</template>

<style scoped>
.layout {
  background-color: #111;
  color: white;
  min-height: 100vh;
}

.navbar {
  background-color: #222;
  padding: 1rem;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-area {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-icon {
  font-size: 1.5rem;
}

.site-name {
  font-weight: bold;
  font-size: 1rem;
  color: white;
}

.nav-center {
  display: flex;
  gap: 1.5rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-center li a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.nav-right .by-link {
  color: white;
  text-decoration: none;
  font-weight: bold;
}
</style>
