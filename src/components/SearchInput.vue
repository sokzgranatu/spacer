<template>
      <!-- <label for="search">Search</label> -->
      <input id="search" name="search" :value="value" @input="handleChange" :class="{dark:dark}"/>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    value: {
      type: String,
      required: true,
    },
    dark: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleChange(e) {
      this.$emit('input', e.target.value);
    },
  },
};
</script>

<style lang="scss" scoped>

// .searchWrapper{
//     margin-top:50px ;
//     width: 250px;
//     display: flex;
//     flex-direction: column;
//   }
  input{
    color: white;
    background: none;
    font-weight: 300;
    font-size: 18px;
    height: 30px;
    border: 0;
    text-align: center;
    border-bottom: 1px solid white;
    transition: box-shadow .5s ease-in-out;
    margin-top:50px ;
    width: 250px;
    display: flex;
    flex-direction: column;
  }
  input:focus{
    outline: none;
    box-shadow: 0 10px 20px -8px rgba(255, 255, 255, .3);
  }
  .dark{
    color: #1e3d4a;
    border-bottom-color:#1e3d4a ;
  }
  .dark:focus{
    outline: none;
    box-shadow: 0 10px 20px -8px (#1e3d4a .3);
  }

</style>
