<template>
  <div class="animals">
    <table>
      <thead>
        <th>Name</th>
        <th>Species</th>
        <th>Born on</th>
        <th>&nbsp;</th>
        <th>&nbsp;</th>
      </thead>
      <tr v-for="(animal, key) in animals" :key="key">
        <td>{{ animal.name  }}</td>
        <td>{{ animal.species  }}</td>
        <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'unknown' }}</td>
        <td><button @click="removeAnimal(animal)">x</button></td>
        <td><button @click="moveToTop(animal)">Move to top</button></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'AnimalsList',
  props: {
    
  },
  data() {
    return {
      animals: [
        { name: 'Polly', species: 'Parrot', dateOfBirth: '15/02/1899' },
        { name: 'Molly', species: 'Antilope' },
        { name: 'Dumbo', species: 'Elephant', dateOfBirth: '15/02/1989' },
        { name: 'Peter', species: 'Rabbit', dateOfBirth: '15/02/1969' },
        { name: 'Bagira', species: 'Panther', dateOfBirth: '' }
      ]
    }
  },
  methods: {
    removeAnimal(animal) {
      this.animals.splice(this.animals.indexOf(animal), 1);
    },
    moveToTop(animal) {
      let temp = this.animals.splice(this.animals.indexOf(animal), 1)
      this.animals.unshift(temp[0]);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
