<template>
  <div class="searchWrapper">
      <!-- <label for="search">Search</label> -->
      <input id="search" name="search" v-model="searchValue" @input="handleInput"
      />
 </div>
</template>

<script>
export default {
  name: 'SearchInput',
};
</script>

<style lang="scss" scoped>

.searchWrapper{
    margin-top:50px ;
    width: 250px;
    display: flex;
    flex-direction: column;
  }
  input{
      background: none;
    height: 30px;
    border: 0;
    border-bottom: 1px solid black ;
  }
</style>
