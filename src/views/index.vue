<template>
  <div class="page">
    <page-header />
    <main>
      <page-sidebar />
      <div class="page-content">
        <about-section />
      </div>
    </main>
  </div>
</template>
<script setup>
import '@/assets/css/style.scss'
import PageHeader from '@/components/PageHeader'
import PageSidebar from '@/components/PageSidebar'
import AboutSection from '@/components/Sections/AboutSection'
</script>