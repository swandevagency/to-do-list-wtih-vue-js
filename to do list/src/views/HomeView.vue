<script>
  import searchIcon from '../components/icons/search-icon.vue'
  import closeIcon from '../components/icons/close-icon.vue'
  import up from '../components/icons/up.vue'
  import { looseIndexOf } from '@vue/shared'
  import { ref, onMounted } from 'vue'

  const el = ref()
  onMounted(() => {
    el.value // <div>
  })

  export default {
    data() {
      return {
        add: true,
        VTitle:"",
        VDescription:"",
        VTime:"",
        index: "",
        tasks: [],
        newTasks: null
      }
    },
    components: {
      searchIcon,
      closeIcon,
      up
    },
    mounted() {
      const savedTasks = localStorage.getItem('tasks')
      if (savedTasks) {
        this.tasks = JSON.parse(localStorage.getItem('tasks'));
      }
    },
    methods: {
      addTask(){

        const newTask = {
          title: this.VTitle,
          description: this.VDescription,
          time: this.VTime,
        }
        this.tasks.push(newTask)
        this.saveTasks()
        this.VTitle = ""
        this.VDescription = ""
        this.VTime = ""
      },
      
      saveTasks() {
        const parsed = JSON.stringify(this.tasks);
        localStorage.setItem('tasks', parsed);
      },

      deleteTask(index){
        
        this.tasks[index] = null;

        this.tasks = this.tasks.filter((task) => task);
        this.saveTasks()

      },
      onScroll(){
        document.querySelector('#getStarted').scrollIntoView({
          behavior: 'smooth',
        });
      },
      upClick(){
        document.querySelector('header').scrollIntoView({
          behavior: 'smooth',
        });
      },
      currentDateTime() {
        const current = new Date();
        const date = current.toLocaleString();
        const dateTime = date;

        return dateTime;
      } 

    }
    
  }
</script>

<template>
  <hero>
    <div class="left-part-of-hero">
      <h1>Company Name To Do List</h1>
      <p>have discipline in your life</p>
      <button @click="onScroll()">Get Started</button>
    </div>
    <div class="right-part-of-hero">
      
    </div>
  </hero>
  <Section class="list-section" id="getStarted">
    <div class="list-section-wrapper">

      <div class="introduction-part">
        <h3>You Have <span>{{tasks.length}} Task</span> To Do For Today</h3>
        <p>{{currentDateTime()}}</p>
      </div>
      <div class="introduction-part">
        <p class="greeting">Good Afternoon <span>Arsam</span> </p>
        <button class="add-task-button" @click="add = !add">
          <p v-if="add">Add Task</p>
          <p v-else>Close</p>
        </button>
        
      </div>
      <input  class="task-search-bar" type="text" placeholder="Search for Task...">
      <searchIcon />
      

      <section>
        <div class="section" v-if="!add">
          <div class="add-task-container">
                <label>Title:</label>
                <input v-model="VTitle" type="text" class="titleInput" />

                <label>Description:</label>
                <input v-model="VDescription" class="descriptionInput">
                
                
                <label>Time:</label>
                <input v-model="VTime" type="time" class="timeInput">

                <button @click="addTask()" class="add-task-button-in-container">Add</button>
          </div>
        </div>
      </section>


      <section class="task-container-wrapper">
        <div class="task-container" :key="index" v-for="(task, index) in tasks" >
            <div class="task-first-part">
              <h4>{{task.title}}</h4>
              <button @click="deleteTask(task.index)"><closeIcon /></button>
            </div>
            <p class="task-description">{{task.description}}</p>
            <div class="task-last-part">
              <p>Task {{index +  1}}</p>
              <p>{{task.time}}</p>
            </div>
        </div>
      </section>

    </div>
  </Section> 
  <button @click="upClick()" class="up-button">
    <up />
  </button> 
</template>

<style scoped lang="scss">
*{
  margin: 0;
}

hero{
  width: 100%;
  display: flex;
  padding: 0px 60px;
}

.right-part-of-hero{
  width: 47%;
  height: 65vh;
  background: url('@/assets/hero.png');
  background-size: cover;
}

.left-part-of-hero{
  width: 50%;
    
  h1{
    color: #16697B;
    font-weight: bolder;
    padding-right: 170px;
    font-size: 60px;
    line-height: 60px;
    margin-top: 120px;    
  }

  p{
    color: #82C1CE;
    margin-top: 40px;
    margin-bottom: 45px;
    margin-left: 5px;
    font-size: 22px;
  }

  button{
    background-color: #FFC85D;
    margin-top: 20px;
    padding: 8px 15px;
    font-weight: 800;
    border-radius: 5px;
    outline: none;
    border: none;
    color: #004655;
    box-shadow: 2px 2px #d5d5d5;
  }
  button:hover{
    box-shadow: none;
  }
}

.list-section{
  width: 100%;
  background-color: #DFF6FF;
  margin-top: 100px;
}

.list-section-wrapper{
  padding: 30px 90px 80px 60px;
  

  .introduction-part{
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;

    h3{
      font-weight: bold;
      color: #007C97;
      font-size: 25px;
      span{
        color: #00D1FF;
        font-size: 27px;
        font-weight: bolder;
      }
    }
    p{
      font-weight: 400;
      color: #585757;
    }
  }

  .greeting{
    margin-top: 35px;
    margin-bottom: 45px;
    font-weight: 200;
    color: #818181;
    span{
      font-weight: 600;
    }
  }

  .add-task-button{
    background-color: #FFC85D;
    padding: 8px 15px;
    border: none;
    border-radius: 5px;
    box-shadow: 2px 2px #d5d5d5;

    p{
      font-weight: 700;
      color: #004655;      
    }
  }
  .task-search-bar{
    width: 100%;
    color: #004655;
    font-weight: 400;
    font-size: 18px;
    border: none;
    outline: none;
    border-radius: 40px;
    background-color: #dff6ff;
    font-size: 14px;
    padding: 15px 75px;
    box-shadow: 1px 1px 5px #00000085;
;
    margin-bottom: 50px;
    position: relative;
    &::placeholder{
      color:#868686;
      font-weight: 100;
    }  
  }
}

.search-icon{
    position: absolute;
    left: 95px;
    margin-top: 12px;
}






.section{
  width: 100%;
  margin-bottom: 100px;
  display: flex;
  justify-content: center;
  align-items: center;

  label{
    color: #004655;
    font-weight: 500;
    font-size: 18px;
  }
}

.add-task-container{
  padding: 50px 30px;
  border-radius: 10px;
  background-color: hsl(197deg 100% 94%);
  width: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: inset 1px 1px 6px #00000065;
}

.titleInput{
  background-color: #00D1FF;
  padding: 8px 15px;
  border-radius: 5px;
  border: none;
  box-shadow: 2px 2px #00000030;
  margin-bottom:10px;
  color: #004655;
  font-size: 18px;
  font-weight: 600;
}

.descriptionInput{
  background-color: #00D1FF;
  padding: 8px 15px;
  border-radius: 5px;
  border: none;
  box-shadow: 2px 2px #00000030;
  margin-bottom:20px;
  color: #004655;
  font-size: 18px;
  font-weight: 600;
}

.timeInput{
  background-color: #00D1FF;
  padding: 8px 15px;
  border-radius: 5px;
  border: none;
  box-shadow: 2px 2px #00000030;
  margin-bottom:25px;
  color: #004655;
  font-size: 18px;
  font-weight: 600;
}

.add-task-button-in-container{
  background-color: #FFC85D;
  padding: 8px 15px;
  font-weight: 600;
  border-radius: 5px;
  border: none;
  margin: 20px 0px;
  color: #004655;
  box-shadow: 2px 2px #00000030;
}






.task-container{
  width: 100%;
  background-color: #08D5FF;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  padding: 20px 35px;
  box-shadow: 0px 4px 4px rgb(0 0 0 / 25%);
  margin-bottom: 20px;


  .task-first-part{
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;

    h4{
      font-weight: 800;
      color: #fcff00e6;
      font-size: 25px;
      letter-spacing: 1px;
    }
    
    button{
      background: none;
      border: none;
      outline: none;
    }
  }

  .task-description{
    color: #0f6092;
    font-weight: 500;
    margin-top: 20px;
    margin-bottom: 40px;
    word-spacing: 0.3px;
    line-height: 25px;
  }
  .task-last-part{
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;
    
    p{
      color: #F1F4F6;
      font-weight:600;
    }
  }
}

.up-button[data-v-9ea40744] {
    display: flex;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    z-index: 10;
    position: fixed;
    bottom: 20px;
    right: 20px;
    border: none;
    background-color: #ffc85d;
    align-items: center;
    justify-content: center;
}

</style>
