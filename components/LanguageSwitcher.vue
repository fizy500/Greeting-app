<template>
    <div class="language-switcher">
      <label for="language-select">Choose a language:</label>
      <select id="language-select" @change="switchLanguage($event)">
        <option
          v-for="locale in $i18n.locales"
          :key="locale.code"
          :value="locale.code"
          :selected="locale.code === $i18n.locale"
        >
          {{ locale.name }}
        </option>
      </select>
    </div>
  </template>
  
  <script setup>
  const switchLanguage = (event) => {
    const { $i18n } = useNuxtApp()
    $i18n.setLocale(event.target.value)
  }
  </script>
  
  <style scoped>
  .language-switcher {
    margin: 1rem 0;
    font-size: 1rem;
  }
  
  select {
    padding: 5px 10px;
    font-size: 1rem;
  }
  </style>
  