<script setup>
import { ref } from "vue";
const usedSpace = ref(815);
</script>

<template>
  <main class="main">
    <h1 class="sr-only">Data storage</h1>
    <div class="main__options-container">
      <img
        class="main__options-container__logo"
        src="/assets/logo.svg"
        alt="fylo logo"
      />
      <div class="main__options-container__options">
        <img src="/assets/icon-document.svg" alt="document icon" />
        <img src="/assets/icon-folder.svg" alt="folder icon" />
        <img src="/assets/icon-upload.svg" alt="upload icon" />
      </div>
    </div>
    <div class="main__space-indicator-container">
      <div class="main__space-indicator-container__info">
        You've used <span>{{ usedSpace }} GB</span> of your storage
      </div>
      <div class="main__space-indicator-container__indicator">
        <div
          class="main__space-indicator-container__indicator__used"
          :style="{ width: `${(usedSpace / 1000) * 100}%` }"
        >
          <div
            class="main__space-indicator-container__indicator__used__circle"
          ></div>
        </div>
        <div class="main__space-indicator-container__indicator__tooltip">
          <div class="main__space-indicator-container__indicator__tooltip__number">
            {{ 1000 - usedSpace }}
          </div>
          <div class="main__space-indicator-container__indicator__tooltip__text">GB LEFT</div>
        </div>
      </div>
      <div class="main__space-indicator-container__limits">
        <div class="main__space-indicator-container__limits__min">0 GB</div>
        <div class="main__space-indicator-container__limits__max">1000 GB</div>
      </div>
    </div>
  </main>
</template>

<style scoped></style>
