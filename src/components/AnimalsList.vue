<template>
  <div class="animals">
    <table>
      <thead>
        <th>Name</th>
        <th>Species</th>
        <th>Born on</th>
      </thead>
      <tr v-for="(animal, key) in animals" :key="key">
        <td>{{ animal.name  }}</td>
        <td>{{ animal.species  }}</td>
        <td>{{ animal.dateOfBirth  }}</td>
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
        { name: 'Molly', species: 'Antilope', dateOfBirth: '15/02/1959' },
        { name: 'Dumbo', species: 'Elephant', dateOfBirth: '15/02/1989' },
        { name: 'Peter', species: 'Rabbit', dateOfBirth: '15/02/1969' },
        { name: 'Bagira', species: 'Panther', dateOfBirth: '16/03/1999' }
      ]
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
