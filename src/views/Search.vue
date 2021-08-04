<template>
  <div class="wrapper">
    <Claim />
    <SearchInput />
      <!-- <input id="search" name="search" v-model="searchValue" @input="handleInput"
      /> -->
      <!-- <ul>
        <li v-for="item in results" :key="item.data[0].nasa_id">
          <p>{{ item.data[0].description}}</p>
        </li>
      </ul> -->
    </div>
</template>
<script>
import axios from 'axios';
import debounce from 'lodash.debounce';
import Claim from '@/components/Claim.vue';
import SearchInput from '@/components/SearchInput.vue';

const api = 'https://images-api.nasa.gov/search';
export default {
  components: {
    Claim,
    SearchInput,
  },
  name: 'Search',
  data() {
    return {
      searchValue: '',
      results: [],
    };
  },
  methods: {
    handleInput: debounce(function () {
      axios.get(`${api}?q=${this.searchValue}&media_type=image`).then((response) => {
        this.results = response.data.collection.items;
      }).catch((error) => {
        console.log(console.log(error));
      });
    }, 500),
  },
};
</script>
<style lang="scss" scoped>
  .wrapper{
    display: flex;
    flex-direction: column;
    align-items:center;
    justify-content: center;
    margin: 0;
    width:100%;
    height: 100vh;
    padding: 30px;
    width:100% ;
    background-image:url('../assets/heroimage.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 80% 0%;
  }
  // .search{
  //   width: 300px;
  //   display: flex;
  //   flex-direction: column;
  // }
  // input{
  //   height: 30px;
  //   border: 0;
  //   border-bottom: 1px solid black ;
  // }
</style>
