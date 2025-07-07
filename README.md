# 📸 InstaClone - Clone do Instagram com Vue + Ionic + Capacitor

Este projeto é um clone funcional da interface do Instagram, desenvolvido com foco em aprendizado de **interfaces mobile híbridas** usando **Vue 3**, **Ionic Framework** e **Capacitor**.

---

## 🖼️ Demonstrações

### 🔻 Feed
<img src="./screenshots/feed.jpg" alt="Feed do app" width="250"/>

### 🔍 Explorar
<img src="./screenshots/explore.jpg" alt="Explorar do app" width="250"/>

---

## ⚙️ Tecnologias Utilizadas

- [Vue 3](https://vuejs.org/)
- [Ionic Framework](https://ionicframework.com/)
- [Capacitor](https://capacitorjs.com/)
- [Vuetify (opcional)](https://vuetifyjs.com/) para componentes adicionais
- [TypeScript](https://www.typescriptlang.org/)

---

## 📱 Funcionalidades

- [x] Interface de feed com postagens
- [x] Explorar com galeria de vídeos e fotos
- [x] Navegação por abas inferior
- [x] Ações básicas (curtir, comentar, compartilhar, salvar)
- [ ] Upload de fotos e stories *(em desenvolvimento)*
- [ ] Integração com backend *(futuro)*

---

## 🚀 Como rodar

1. **Clone o projeto**
   ```bash
      git clone https://github.com/seu-usuario/instaclone.git
      cd instaclone
   ```

2. **Instale as dependências**

   ```bash
      npm install
   ```

3. **Rode em ambiente web**

   ```bash
      ionic serve
   ```

4. **Rode no Android**

   ```bash
      ionic build
      npx cap sync
      npx cap open android
   ```

---

## 📁 Estrutura de Pastas

```
   src/
   ├── components/
   ├── views/
   │   ├── FeedPage.vue
   │   ├── ExplorePage.vue
   │   └── ...
   ├── router/
   ├── App.vue
   └── main.ts
```

---

## 🎯 Objetivo

Este projeto tem fins **educacionais** e foi criado para praticar:

* Criação de interfaces mobile com Vue + Ionic
* Uso de navegação por abas
* Layout semelhante a apps reais (como Instagram)
* Empacotamento com Capacitor para Android

---

## 📌 Autor

**Luiz Trindade**
Desenvolvedor Full Stack
[LinkedIn](https://www.linkedin.com/) | [Instagram](https://instagram.com/) | [GitHub](https://github.com/)

---

## 📝 Licença

MIT © 2025 Luiz Trindade

---

### 👇 Para deixar seu projeto ainda melhor:
- Adicione uma pasta `screenshots/` e renomeie as imagens que você enviou como `feed.jpg` e `explore.jpg`, por exemplo.
- Use o GitHub Pages ou Netlify para mostrar uma versão web do app (mesmo que só o layout).

Se quiser, posso gerar também o `package.json`, `capacitor.config.ts` ou estrutura inicial de pastas. É só pedir.
