<template>
  <div class="animals">
    <form @submit.prevent="addNewAnimal">
      <label for="name">Name</label>
      <input type="text" id="name" v-model="newAnimal.name">
      <label for="species">Species</label>
      <input type="text" id="species" v-model="newAnimal.species">
      <label for="date">Date of birth</label>
      <input type="date" id="date" v-model="newAnimal.dateOfBirth">
      <label for="sector">Select sector</label>
      <select id="sector" v-model="newAnimal.sector">
        <option v-for="(sector, key) in sectors" :key="key" :value="sector.name">{{ sector.name }}</option>
      </select>
      <button type="submit">Add new animal</button>
    </form>
    <table>
      <thead>
        <th>Name</th>
        <th>Species</th>
        <th>Born on</th>
        <th>Sector</th>
        <th>&nbsp;</th>
        <th>&nbsp;</th>
      </thead>
      <tr v-for="(animal, key) in animals" :key="key">
        <td>{{ animal.name  }}</td>
        <td>{{ animal.species  }}</td>
        <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'unknown' }}</td>
        <td>{{ animal.sector  }}
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
        { name: 'Polly', species: 'Parrot', dateOfBirth: '15/02/1899', sector: 'Rain forest' },
        { name: 'Molly', species: 'Antilope', sector: 'Ravanah' },
        { name: 'Dumbo', species: 'Elephant', dateOfBirth: '15/02/1989', sector: 'Ravanah' },
        { name: 'Peter', species: 'Rabbit', dateOfBirth: '15/02/1969', sector: 'Forest' },
        { name: 'Bagira', species: 'Panther', dateOfBirth: '', sector: 'Rain forest' }
      ],
      newAnimal: {
        name: '',
        species: '',
        dateOfBirth: '',
        sector: ''
      },
      sectors: [
        { name: 'Forest animals', surface: 'Cages' },
        { name: 'Rain forest animals', surface: 'Cages' },
        { name: 'Ocean animals', surface: 'Aquarium' },
        { name: 'Savannah animals', surface: 'Cages' }
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
    },
    addNewAnimal() {
      this.animals.push(this.newAnimal);
      this.newAnimal = {};
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
