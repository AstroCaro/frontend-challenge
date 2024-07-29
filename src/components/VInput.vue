<script setup>
const props = defineProps([
  'type',
  'placeholder',
  'icon',
  'color',
  'default',
  'fontSize',
]);
</script>

<template>
  <div class="input-content" :style="{ color: props.color }">
    <span class="material-symbols-outlined">{{ props.icon }} </span>
    <input
      :type="props.type"
      :placeholder="props.placeholder"
      :style="{ color: props.color, 'font-size': props.fontSize }"
      v-model="props.default"
    />
  </div>
</template>

<style scoped>
.input-content {
  background-color: var(--color-background-form);
  border-radius: 4px;
  width: 100%;
  display: flex;
  flex: 1;
  align-items: center;
  gap: 16px;
  padding: 12px 16px;
  min-height: 54px;
}

.input-content input {
  background-color: transparent;
  border: none;
  width: 100%;
  font-size: 18px;
  font-weight: 300;
}

.input-content input:focus-visible {
  outline: none;
}

::webkit-input-placeholder {
  /* WebKit, Blink, Edge */
  color: white;
}
:-moz-placeholder {
  /* Mozilla Firefox 4 to 18 */
  color: white;
  opacity: 1;
}
::-moz-placeholder {
  /* Mozilla Firefox 19+ */
  color: white;
  opacity: 1;
}
:-ms-input-placeholder {
  /* Internet Explorer 10-11 */
  color: white;
}
::-ms-input-placeholder {
  /* Microsoft Edge */
  color: white;
}

::placeholder {
  /* Most modern browsers support this now. */
  color: white;
}
</style>
