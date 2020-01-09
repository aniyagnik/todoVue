<template>
  <v-app>
    <h1>to list is here</h1>
    <v-container class="my-5">
      <v-layout row class='ma-6'>
          <v-btn small flat class='mx-6 pa-4' @click="sortBy('name')">
            <v-icon left small>mdi-folder</v-icon>
            <span class="body-1 text-lowercase">sort by todo name</span>
          </v-btn>
          <v-btn small flat class='mx-6  pa-4' @click="sortBy('priority')">
            <v-icon left small>mdi-check-circle</v-icon>
            <span class="body-1 text-lowercase">sort by todo status</span>
          </v-btn>
      </v-layout>
      <v-card class="todos" v-for='(todo,i) in todos' :key="i">
        <v-layout row wrap :class="` pa-4 ${todo.status}`">
          <v-flex xs12 md6 class='px-4'>
            <div class="title grey--text">TODO WORK</div>
            <div>{{ todo.content }}</div>
          </v-flex>
          <v-flex xs6 s4 md2 class='px-4'>
            <div class="title grey--text">USERNAME</div>
            <div>{{ todo.username }}</div>
          </v-flex>
          <v-flex xs6 s4 md2 class='px-4'>
            <div class="title grey--text">DATE</div>
            <div>{{ todo.date }}</div>
          </v-flex>
          <v-flex style='float:right' xs6 s4 md2 class='px-4'>
            <div class="title grey--text">STATUS</div>
            <div>
              <v-chip small :class="`${todo.status}1`">{{ todo.status }}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name:'content',
  data () {
    return {
      todos: [
        { content: `consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'anirudh', date: '19th jan 2020', status: 'ongoing', priority: '1' },
        { content: `consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'yagnik', date: '19th jan 2020', status: 'complete', priority: '2' },
        { content: `consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'shankar', date: '19th jan 2020', status: 'ongoing', priority: '1' },
        { content: `consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'vagish', date: '19th jan 2020', status: 'overdue', priority: '0' },
      ]
    }
  },
  methods: {
      sortBy (val) {
          this.todos.sort((a,b) => a[val] < b[val] ? -1 : 1)
      }
  }
}
</script>

<style >
.todos .complete{
    border-left:10px solid rgb(76, 186, 230);
}
.todos .ongoing{
    border-left:10px solid gold;
}
.todos .overdue{
    border-left:10px solid rgb(212, 124, 124);
}
v-component.todos .complete1{
    background-color: rgb(76, 186, 230);
}
.todos .ongoing1{
    background-color: gold;
}
.todos .overdue1{
    background-color: rgb(212, 124, 124);
}
</style>