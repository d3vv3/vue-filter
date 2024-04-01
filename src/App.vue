<template>
  <v-app>
    <v-main>
      <FilterSearch :filters="filters"/>
    </v-main>
  </v-app>
</template>

<script setup lang="ts">
  // Example people to test the search filters
  const people = [
    { name: 'Pepe', age: 42, salary: 1200, single: true, skills: ['Python', 'C', 'Rust', 'Go']},
    { name: 'Juan', age: 32, salary: 1500, single: false, skills: ['C++', 'SQL', 'HTML', 'PHP']},
    { name: 'Maria', age: 22, salary: 2000, single: true, skills: ['Vue', 'React', 'Javascript', 'Typescript']},
    { name: 'Ana', age: 52, salary: 1000, single: false, skills: ['Java', 'C#', 'Ruby', 'Perl']},
    { name: 'Luis', age: 62, salary: 800, single: true, skills: ['Cobol', 'Fortran', 'Pascal', 'Basic']}
  ]

  const filters = {
    age: {
      min: 18,
      max: 65,
      type: 'range',
    },
    salary: {
      min: 800,
      max: 2000,
      type: 'range',
    },
    status: {
      type: 'checkbox',
      options: [
        {checked: true, label: 'Single', value: 'single'},
        {checked: true, label: 'Married', value: 'married'},
      ],
    },
    skills: {
      type: 'checkbox',
      options: [
        {checked: true, label: 'Python', value: 'python'},
        {checked: false, label: 'C', value: 'c'},
        {checked: false, label: 'Rust', value: 'rust'},
        {checked: false, label: 'Go', value: 'go'},
        {checked: false, label: 'C++', value: 'c++'},
        {checked: false, label: 'SQL', value: 'sql'},
        {checked: false, label: 'HTML', value: 'html'},
        {checked: false, label: 'PHP', value: 'php'},
        {checked: false, label: 'Vue', value: 'vue'},
        {checked: false, label: 'React', value: 'react'},
        {checked: false, label: 'Javascript', value: 'javascript'},
        {checked: false, label: 'Typescript', value: 'typescript'},
        {checked: false, label: 'Java', value: 'java'},
        {checked: false, label: 'C#', value: 'c#'},
        {checked: false, label: 'Ruby', value: 'ruby'},
        {checked: false, label: 'Perl', value: 'perl'},
        {checked: false, label: 'Cobol', value: 'cobol'},
        {checked: false, label: 'Fortran', value: 'fortran'},
        {checked: false, label: 'Pascal', value: 'pascal'},
        {checked: false, label: 'Basic', value: 'basic'},
      ],
    },
  }
</script>
