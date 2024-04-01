<template>
  <v-row class="justify-center filters-row">
    <v-col v-for="(filter, key) in filters" :key="key" class="flex-grow-0 pt-0">
    <!-- Render filter components based on their type -->
    <template v-if="filter.type === 'range'">
      <!-- Render range filter component -->
      <Range :filterData="filter" :name="key"/>
    </template>
    <template v-else-if="filter.type === 'checkbox'">
      <!-- Render checkbox filter component -->
      <MultiCheckbox :filterData="filter" :name="key"/>
    </template>
    <!-- <template v-else-if="filter.type === 'select'"> -->
      <!-- Render select filter component -->
      <!-- <SelectFilter :filterData="filter" /> -->
    <!-- </template> -->
    </v-col>
  </v-row>
</template>


<script lang="ts">
  export default {
    name: 'FiltersRow',
    props: {
      filters: {
        type: Object,
        default: () => ({}),
      },
    },
  }
</script>


<style scoped>
  .filters-row {
    animation: slide-in 0.5s;
  }
</style>
