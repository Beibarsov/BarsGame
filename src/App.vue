<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { Alert, MainButton, usePopup, useMiniApp  } from 'vue-tg'



const { showAlert } = usePopup()
const { initDataUnsafe } = useMiniApp()
const username = initDataUnsafe.user?.username
const userFirstName = initDataUnsafe.user?.first_name
let a = 1;






</script>
<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      
      <HelloWorld msg="Привет" />
      
      <MainButton  text="Нажми на кнопку" @click=" () => showAlert('Result!')"/>
      
      

      

    </div>
  </header>

  <main>
    <h3>
        Вот что мы знаем о тебе:
        <p>{{ username }}</p>
        <p>{{ userFirstName }}</p>
        <p> У тебя очков {{ a }}</p>
      </h3>
      <button @click=" () =>showAlert('Result!')">Классная кнопка</button>
      <router-link to="/products">Products</router-link>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
