 <template>
  <div id="app">
    <HeaderTitle />
    <TodosList />
  </div>
</template>
 
 <script>
import HeaderTitle from './components/title.vue'
import TodosList from './components/Todos.vue'

export default {
  name: 'App',
  components: { 
    HeaderTitle ,
    TodosList
    },
 
}
</script>
 
 <style>
#app {
  font-family: 'Times New Roman', Times, serif;
}
</style>