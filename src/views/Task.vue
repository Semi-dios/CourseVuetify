<template>
  <v-row>
    <v-col class="pa-0" xs12 md6>
     <v-row v-for="(item,index) in listTask" :key="index">
       <v-col xs12  lg12>
          <v-card>
        <v-card-title>
             <v-chip
              class="ma-2"
            
              color="indigo darken-3"
              outlined
            >
              <v-icon left>
                mdi-fire
              </v-icon>
            {{item.title}}-{{item.id}}
            </v-chip>
        </v-card-title>
        <v-card-text>
          <p>{{item.description}}</p>
        </v-card-text>
        <v-card-actions>
          <v-btn color="warning" class="mr-3" @click="edit(index)">
            Edit
          </v-btn>
          <v-btn color="error" @click="deleteTask(item.id)">
            Delete
          </v-btn>
        </v-card-actions>
      </v-card>
       </v-col>
     </v-row>
    
    </v-col>
    <v-col xs12 md6 >
      <v-card class="pa-3" v-if="add">
          <v-form @submit.prevent="addTask">
            <v-text-field label="title task" v-model="title">
            </v-text-field>
            <v-textarea v-model="description"
              label="Description "
            >

            </v-textarea>
            <v-btn block  color="success" type="submit">Add task</v-btn>
          </v-form>
           <v-snackbar
            v-model="snackbar"
            
          >
            {{ message }}

            <template v-slot:action="{ attrs }">
              <v-btn
                color="red"
                text
                v-bind="attrs"
                @click="snackbar = false"
              >
                Close
              </v-btn>
            </template>
          </v-snackbar>
      </v-card>
      <v-card class="pa-3" v-if="!add">
          <v-form @submit.prevent="editTask">
            <v-text-field label="title task" v-model="title">
            </v-text-field>
            <v-textarea v-model="description"
              label="Description "
            >

            </v-textarea>
            <v-btn block  color="warning" type="submit">Edit task</v-btn>
          </v-form>
           <v-snackbar
            v-model="snackbar"
            
          >
            {{ message }}

            <template v-slot:action="{ attrs }">
              <v-btn
                color="red"
                text
                v-bind="attrs"
                @click="snackbar = false"
              >
                Close
              </v-btn>
            </template>
          </v-snackbar>
      </v-card>

    </v-col>
  </v-row>
</template>
<script>
export default {
  data() {
    return {
      title:' ',
      description: '',
      message: '',
      snackbar: false,
      add: true,
      indexTask: '',

      listTask: [
        {
          id:1,title: 'Task 1', description: 'First Task'
        },
        {
          id:2,title: 'Task 2', description: 'Second Task'
        },
        {
          id:3,title: 'Task 3', description: 'Third Task'
        },
        {
          id:4,title: 'Task 4', description: 'Fourth Task'
        },
        {
          id:5,title: 'Task 5', description: 'Fifth Task'
        },
      ],

    }
  },
  methods: {
    addTask() {
      console.log(this.title, this.description)
      if(!this.title || !this.description) {
        this.message="the fields are empty"
        this.snackbar= true
      }else  {
        this.listTask.push({
          id: Date.now(),
          title: this.title,
          description: this.description
        })

        this.title= ''
        this.description= ''
         this.message="Created new Task"
        this.snackbar= true
      }
    },
    deleteTask(id) {
        this.listTask= this.listTask.filter(e =>  e.id != id )
    },
    edit(index) {
      this.add= false;
     this.title = this.listTask[index].title
     this.description = this.listTask[index].description
     this.indexTask = index

     
    },
    editTask() {
      this.listTask[this.indexTask].title= this.title  
      this.listTask[this.indexTask].description= this.description  
      
      this.add= true;
      this.title = ''
      this.description  = ''
      this.message="Edited"
      this.snackbar= true
    }
  }
}
</script>