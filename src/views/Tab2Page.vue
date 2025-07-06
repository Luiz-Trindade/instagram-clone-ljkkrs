<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-searchbar placeholder="Pesquisar" :search-icon="search" cancel-button-icon="close-outline"
          show-cancel-button="focus" animated class="custom-searchbar"></ion-searchbar>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <!-- Pull-to-refresh -->
      <ion-refresher slot="fixed" @ionRefresh="doRefresh">
        <ion-refresher-content pulling-icon="lines" refreshing-spinner="circles"></ion-refresher-content>
      </ion-refresher>

      <!-- Categorias -->
      <div class="categories-container">
        <ion-chip v-for="category in categories" :key="category" outline>
          <ion-label>{{ category }}</ion-label>
        </ion-chip>
      </div>

      <!-- Grade de posts -->
      <div class="grid-container">
        <div v-for="post in posts" :key="post.id" class="post-item" :class="post.type === 'video' ? 'video-post' : ''">
          <img :src="post.image" :alt="'Post de ' + post.username">
          <ion-icon v-if="post.type === 'video'" :icon="playCircleOutline" class="video-icon"></ion-icon>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonSearchbar,
  IonContent,
  IonChip,
  IonLabel,
  IonIcon,
  IonRefresher,
  IonRefresherContent,
  RefresherCustomEvent // Importação importante
} from '@ionic/vue';
import { playCircleOutline, search } from 'ionicons/icons';

// Dados de exemplo
const categories = [
  'Para você', 'Ao vivo', 'Jogos', 'Reels', 'Futebol',
  'Música', 'Moda', 'Comida', 'Animais', 'Viagem'
];

const posts = [
  { id: 1, image: 'https://picsum.photos/300/300?random=1', type: 'image', username: 'user1' },
  { id: 3, image: 'https://picsum.photos/300/300?random=3', type: 'image', username: 'user3' },
  { id: 4, image: 'https://picsum.photos/300/300?random=4', type: 'image', username: 'user4' },
  { id: 3, image: 'https://picsum.photos/300/300?random=3', type: 'image', username: 'user3' },
  { id: 5, image: 'https://picsum.photos/300/300?random=5', type: 'video', username: 'user5' },
  { id: 6, image: 'https://picsum.photos/300/300?random=6', type: 'image', username: 'user6' },
  { id: 1, image: 'https://picsum.photos/300/300?random=1', type: 'image', username: 'user1' },
  { id: 3, image: 'https://picsum.photos/300/300?random=3', type: 'image', username: 'user3' },
  { id: 4, image: 'https://picsum.photos/300/300?random=4', type: 'image', username: 'user4' },
  { id: 3, image: 'https://picsum.photos/300/300?random=3', type: 'image', username: 'user3' },
  { id: 4, image: 'https://picsum.photos/300/300?random=4', type: 'image', username: 'user4' },
  { id: 5, image: 'https://picsum.photos/300/300?random=5', type: 'video', username: 'user5' },
  { id: 5, image: 'https://picsum.photos/300/300?random=5', type: 'video', username: 'user5' },
  { id: 5, image: 'https://picsum.photos/300/300?random=5', type: 'video', username: 'user5' },
  { id: 6, image: 'https://picsum.photos/300/300?random=6', type: 'image', username: 'user6' },
  { id: 1, image: 'https://picsum.photos/300/300?random=1', type: 'image', username: 'user1' },
  { id: 2, image: 'https://picsum.photos/300/300?random=2', type: 'video', username: 'user2' },
  { id: 2, image: 'https://picsum.photos/300/300?random=2', type: 'video', username: 'user2' },
  { id: 4, image: 'https://picsum.photos/300/300?random=4', type: 'image', username: 'user4' },
  { id: 6, image: 'https://picsum.photos/300/300?random=6', type: 'image', username: 'user6' },
  { id: 1, image: 'https://picsum.photos/300/300?random=1', type: 'image', username: 'user1' },
  { id: 2, image: 'https://picsum.photos/300/300?random=2', type: 'video', username: 'user2' },
  { id: 1, image: 'https://picsum.photos/300/300?random=1', type: 'image', username: 'user1' },
  { id: 6, image: 'https://picsum.photos/300/300?random=6', type: 'image', username: 'user6' },
  { id: 2, image: 'https://picsum.photos/300/300?random=2', type: 'video', username: 'user2' },
  { id: 2, image: 'https://picsum.photos/300/300?random=2', type: 'video', username: 'user2' },
  { id: 3, image: 'https://picsum.photos/300/300?random=3', type: 'image', username: 'user3' },
  { id: 4, image: 'https://picsum.photos/300/300?random=4', type: 'image', username: 'user4' },
  { id: 5, image: 'https://picsum.photos/300/300?random=5', type: 'video', username: 'user5' },
  { id: 6, image: 'https://picsum.photos/300/300?random=6', type: 'image', username: 'user6' },
  // Adicione mais posts conforme necessário
];

function doRefresh(event: RefresherCustomEvent) {
  setTimeout(() => {
    window.location.reload(); // Simula uma atualização completa
    event.detail.complete();
  }, 1000);
}
</script>

<style scoped>
/* Barra de pesquisa */
.custom-searchbar {
  padding-top: 5px;
  padding-bottom: 5px;
}

/* Categorias */
.categories-container {
  padding: 10px 0;
  overflow-x: auto;
  white-space: nowrap;
  border-bottom: 1px solid var(--ion-color-light);
}

.categories-container ion-chip {
  margin: 0 3px;
}

/* Grade de posts */
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
}

.post-item {
  position: relative;
  aspect-ratio: 1/1;
  overflow: hidden;
}

.post-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Estilo para posts de vídeo */
.video-post::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.3);
}

.video-icon {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 48px;
  color: white;
  z-index: 10;
}
</style>