<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>First Name</label>
      <input type="text" v-model="firstName" name="firstName" placeholder="First Name" />
    </div>
    <div class="form-control">
      <label>Last Name</label>
      <input
        type="text"
        v-model="lastName"
        name="lastName"
        placeholder="Last Name"
      />
    </div>

    <div>
        <label>Gender</label><br>
        <input type="radio" id="male" name="gender" v-model="gender" value="male">
        <label for="male">Male</label><br>
        <input type="radio" id="female" name="gender" v-model="gender" value="female">
        <label for="female">Female</label><br>
    </div>

    <div>
      <br><label for="age">Age</label>
      <input type="number" name="age" v-model="age" min="1" max="100">
    </div>

    <br><input type="submit" value="Register" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: 'addPerson',
  data() {
    return {
      firstName: '',
      lastName: '',
      gender: '',
      age: '',
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault()
      if (!this.firstName) {
        alert('Please enter your first name')
        return
      }
      if (!this.lastName) {
        alert('Please enter your last name')
        return
      }
      if (!this.gender) {
        alert('Please enter your gender')
        return
      }
      if (!this.age) {
        alert('Please enter your age')
        return
      }
      const newPerson = {
        firstName: this.firstName,
        lastName: this.lastName,
        gender: this.gender,
        age: this.age,
      }
      this.$emit('add-person', newPerson)
    },
  },
}
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>