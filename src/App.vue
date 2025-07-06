<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script setup lang="ts">
import { StatusBar, Style } from '@capacitor/status-bar';
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { onMounted } from 'vue';

onMounted(async () => {
  // Oculta a status bar (toolbar do Android)
  await StatusBar.setOverlaysWebView({ overlay: true });
  await StatusBar.setStyle({ style: Style.Light }); // Opcional: define o estilo
});
</script>

<style>
.fade-in {
  animation: fadeIn .5s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.logo-font {
  font-family: 'Pacifico', cursive;
  font-size: 1.5rem;
}
</style>