<template>
  <v-container class="fill-height">
    <v-responsive class="flex justify-center overflow-visible">
      <v-row class="justify-center align-top">
        <!-- Search input -->
        <v-col class="flex-grow-0">
          <SearchBox />
        </v-col>
        <v-col class="flex-grow-0">
          <FilterToggle @click="toggleFilters"/>
        </v-col>
      </v-row>
      <v-expand-transition>
        <FilterRow :filters="filters" v-if="showFilters" />
      </v-expand-transition>
    </v-responsive>
  </v-container>
</template>

<script lang="ts">
  import FilterRow from '@/components/filterSearch/FilterRow.vue';
  export default {
    name: 'Filter',
    props: {
      filters: {
        type: Object,
        default: () => ({}),
      },
    },
    setup() {
      //
    },
    data() {
      return {
        showFilters: false,
      }
    },
    methods: {
      toggleFilters() {
        // Toggle the value of showFilters when clicking on FilterToggle
        this.showFilters = !this.showFilters;
      }
  }
  }
  </script>
