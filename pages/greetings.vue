<template>
    <div class="container">
      <h1>{{ $t('Greeting') }}</h1>
      <div class="select-container">
        <label for="language-select">Choose a language:</label>
        <select id="language-select" @change="changeLanguage($event)">
          <option
            v-for="locale in $i18n.locales"
            :key="locale.code"
            :value="locale.code"
          >
            {{ locale.name }}
          </option>
        </select>
      </div>
    </div>
  </template>
  
  <script setup>
  const changeLanguage = (event) => {
    const { $i18n } = useNuxtApp()
    $i18n.setLocale(event.target.value)
  }
  </script>
  
  <style scoped>
  /* Basic Reset */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  /* Fullscreen container for centering */
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-color: #f4f4f9;
  }
  
  /* Greeting Styling */
  h1 {
    font-size: 3rem;
    color: #333;
    margin-bottom: 20px;
  }
  
  /* Select container */
  .select-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 0.5rem;
  }
  
  /* Select element styling */
  select {
    padding: 10px 20px;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #fff;
    cursor: pointer;
    transition: border-color 0.3s;
  }
  
  select:focus {
    border-color: #007bff;
  }
  
  label {
    font-size: 1.2rem;
    margin-bottom: 15px;
  }
  </style>
  