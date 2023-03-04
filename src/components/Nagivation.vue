<template>
    <header class="sticky top-0 bg-weather-primary shadow-md">
        <nav
          class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6"
        >
          <RouterLink :to="{ name: 'home' }">
            <div class="flex items-center gap-3">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z" />
                </svg>
              <p class="text-1xl font-Roboto">The Local Weather</p>
            </div>
          </RouterLink>

          <div class="flex gap-3 flex-1 justify-end">
            <svg @click="toggleModal" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-xl hover:text-weather-secondary duration-150 cursor-pointer">
                <path stroke-linecap="round" stroke-linejoin="round" d="M11.25 11.25l.041-.02a.75.75 0 011.063.852l-.708 2.836a.75.75 0 001.063.853l.041-.021M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9-3.75h.008v.008H12V8.25z" />
            </svg>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-xl hover:text-weather-secondary duration-150 cursor-pointer">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5v15m7.5-7.5h-15" />
            </svg>
          </div>

          <BaseModal :modal-active="modalActive" @close-modal="toggleModal">
            <div class="text-black">
              <h1 class="text-1xl mb-1">About:</h1>
              <p class="mb-4">
                The Local Weather allows you to track the current and
                future weather of cities of your choosing.
              </p>
              <h2 class="text-1xl">How it works:</h2>
              <ol class="list-decimal list-inside mb-4">
                <li>
                  Search for your city by entering the name into the
                  search bar.
                </li>
                <li>
                  Select a city within the results, this will take
                  you to the current weather for your selection.
                </li>
                <li>
                  Track the city by clicking on the "+" icon in the
                  top right. This will save the city to view at a
                  later time on the home page.
                </li>
              </ol>

              <h2 class="text-1xl">Removing a city</h2>
              <p>
                If you no longer wish to track a city, simply select
                the city within the home page. At the bottom of the
                page, there will be am option to delete the city.
              </p>
            </div>
          </BaseModal>
        </nav>
      </header>
</template>

<script setup lang="ts">
    import { ref } from "vue";
    import BaseModal from "./BaseModal.vue";
    const modalActive = ref(false);
    const toggleModal = () => {
        modalActive.value = !modalActive.value;
    };
</script>