<template>
  <div
    class="condiment-checkbox"
    :class="{ 'condiment-checkbox--checked': checked }"
    :style="{
      '--background-image': `url(${condiment.styles['--background-image']})`,
      '--background-size': condiment.styles['--background-size'],
      '--border-color--hover': condiment.styles['--border-color--hover'],
      '--background-color--hover':
        condiment.styles['--background-color--hover'],
      '--background-color--checked':
        condiment.styles['--background-color--checked']
    }"
  >
    <input
      id="condiment.id"
      v-model="checked"
      type="checkbox"
      class="condiment-checkbox__input"
      :value="condiment.id"
    />
    <label :for="condiment.id" class="condiment-checkbox__label">
      {{ condiment.name }}
    </label>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'CondimentCheckbox',
  props: {
    condiment: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {
      checked: null
    }
  }
})
</script>
<style lang="scss" scoped>
.condiment-checkbox {
  background-repeat: no-repeat;
  background-position: center;
  background-size: var(--background-size, 30%);
  background-image: var(--background-image);
  box-sizing: border-box;
  width: 60px;
  height: 60px;
  border: 1px solid #fff;
  border-radius: 50%;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.28);
  margin: 0 10px 30px;
  transition: 0.3s;
  border-color: rgba(222, 222, 222, 0.1);
  background-color: rgba(222, 222, 222, 0.1);
  &:hover {
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.28);
    border-color: var(--border-color--hover);
    background-color: var(--background-color--hover);
  }
  &:active {
    opacity: 0.7;
    box-shadow: 0 1px 10px rgba(0, 0, 0, 0.2) inset;
  }
  &--checked {
    opacity: 0.6;
    box-shadow: 0 1px 12px rgba(0, 0, 0, 0.2) inset;
    background-color: var(--background-color--checked);
  }
  &--checked:hover {
    opacity: 0.8;
    box-shadow: 0 1px 12px rgba(0, 0, 0, 0.2) inset;
    background-color: var(--background-color--hover);
  }

  &__input {
    width: 100%;
    height: 100%;
    opacity: 0;
    appearance: none;
    -webkit-appearance: none;
    -webkit-tap-highlight-color: transparent;
    &:hover {
      cursor: pointer;
    }
  }
  &__label {
    display: block;
    margin-top: 5px;
    text-align: center;
    font-size: 10px;
  }
}
</style>
