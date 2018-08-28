<template>
  <input type="text" v-model="localValue"/>
</template>

<script lang="ts">
  import {
    Component,
    Emit,
    Prop,
    Vue,
  } from 'vue-property-decorator';
  
  @Component
  export default class ChildComponent extends Vue {
    @Prop() public value!: string;

    @Emit()
    public input(value: string) { /* */ }

    private get localValue(): string {
      return this.value;
    }

    private set localValue(value: string) {
      this.input(value);
    }
  }
</script>
