<template>
  <form>
    <input type="text" placeholder="Việc mới ..." v-model="title">
    <input type="submit" value="thêm" class="add-btn">
  </form>
</template>

<script>
import { ref } from 'vue'
export default {
    
    name: 'AddTodo',
setup(){
    const title = ref('')
    const check = () =>{
        console.log(title.value)
    }
    return{
        title, 
        check
    }
}
}
</script>

<style scoped>
form{
    display: flex;
}
input[type='text']{
    flex: 10;
    padding: 5px;
}
input[type='submit']{
    flex: 2;
 }
</style>