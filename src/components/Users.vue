<template>
  <div :key="person.id" v-for="person in users">
    <Person
      :person="person"
    />
  </div>
</template>

<script>
import Person from './Person'

export default {
  name: 'Users',
  props: {
    users: Array,
  },
  components: {
    Person,
  },
}
</script>