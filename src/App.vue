<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { Alert, MainButton, usePopup, useMiniApp  } from 'vue-tg'

import { ref } from 'vue';

const { showAlert } = usePopup()
const { initDataUnsafe } = useMiniApp()
const username = initDataUnsafe.user?.username
const userFirstName = initDataUnsafe.user?.first_name


const a = ref(0);

// Метод для увеличения значения a
const incrementA = () => {
  a.value++; // Обращаемся к значению через .value
};




</script>
<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      
      <HelloWorld msg="Привет" />
      
      <MainButton  text="Нажми на кнопку" @click=" () => showAlert('Result!')"/>
        <button type="button" @click = "incrementA">Классная кнопка</button>
        <p> У тебя очков {{ a }}</p>
      

      

    </div>
  </header>

  <main>
    <h3>
        Вот что мы знаем о тебе:
        <p>{{ username }}</p>
        <p>{{ userFirstName }}</p>
        
      </h3>
      
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
