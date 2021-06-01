<template>
    <div>
    <addPerson @add-person="displayUser" />
    </div>
</template>

<script>
import addPerson from './addPerson'

export default {
  name: 'Person',
  props: {
    person: Object,
  },
  components: {
    addPerson,
  },
  methods: {
    displayUser (newPerson) {
        const { firstName, lastName, gender, age } = newPerson;
        <div>
        <h3> {{ firstName, lastName }} </h3>
        <p> {{ age, gender }} </p>
        </div>
    }
  }
}
</script>

<style scope>
.fas {
  color: red;
}
.person {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.person.reminder {
  border-left: 5px solid green;
}
.person h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>