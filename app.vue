<script setup lang="ts">
import { SpeedInsights } from '@vercel/speed-insights/vue';



</script>

<template>
  <SpeedInsights />
  <div>
    <!-- <NuxtRouteAnnouncer />
    <NuxtWelcome /> -->
    <NuxtLoadingIndicator />
      <NuxtLayout>
        <!-- <Navbar /> -->
        <DomainWarning />
        <NuxtPage />
      </NuxtLayout>
  </div>
</template>
