<template>
  <v-app>
    <h1>to list is here</h1>
    <v-container class="my-5">
      <v-card class="todos" v-for='(todo,i) in todos' :key="i">
        <v-layout row wrap :class="` pa-4 ${todo.status}`">
          <v-flex xs12 md6 class='px-4'>
            <div class="title grey--text">topic/work</div>
            <div>{{ todo.content }}</div>
          </v-flex>
          <v-flex xs6 s4 md2 class='px-4'>
            <div class="title grey--text">username</div>
            <div>{{ todo.username }}</div>
          </v-flex>
          <v-flex xs6 s4 md2 class='px-4'>
            <div class="title grey--text">Date</div>
            <div>{{ todo.date }}</div>
          </v-flex>
          <v-flex style='float:right' xs6 s4 md2 class='px-4'>
            <div class="title grey--text">Status</div>
            <div>
              <v-chip small>{{ todo.status }}</v-chip>
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
        { content: `mi quae earum magnam, aperiam distinctio vitae fugiat repudiandae voluptate consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'anirudh', date: '19th jan 2020', status: 'ongoing' },
        { content: `mi quae earum magnam, aperiam distinctio vitae fugiat repudiandae voluptate consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'yagnik', date: '19th jan 2020', status: 'complete' },
        { content: `mi quae earum magnam, aperiam distinctio vitae fugiat repudiandae voluptate consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'shankar', date: '19th jan 2020', status: 'ongoing' },
        { content: `mi quae earum magnam, aperiam distinctio vitae fugiat repudiandae voluptate consequatur quas totam ab labore exercitationem accusantium voluptatem?`, username: 'vagish', date: '19th jan 2020', status: 'overdue' },
      ]
    }
  }
}
</script>

<style >
.todos .complete{
    border-left:6px solid rgb(76, 186, 230);
}
.todos .ongoing{
    border-left:6px solid gold;
}
.todos .overdue{
    border-left:6px solid rgb(212, 124, 124);
}
</style>