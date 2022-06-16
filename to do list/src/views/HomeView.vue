<script>
  import searchIcon from '../components/icons/search-icon.vue'
  import closeIcon from '../components/icons/close-icon.vue'
  import up from '../components/icons/up.vue'
  
  export default {
    data() {
        return {
          add: true,
        }
    },
    components: {
      searchIcon,
      closeIcon,
      up
    },
    methods: {
      onclick(){
        console.log('clicked')
        
      },
      closeClick(){
        console.log('close');
        let closableDiv = document.querySelector('.task-container')
        closableDiv.remove()
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
        <h3>You Have <span>10 Task</span> To Do For Today</h3>
        <p>Thusday, JUNE 15</p>
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
                <input v-model="title" type="text" class="titleInput" />

                <label>Description:</label>
                <input v-model="description" class="descriptionInput">
                <button @click="onclick()" class="add-task-button">Add</button>
          </div>
        </div>
      </section>


      <section>  
        <div class="task-container">
          <div>
            <div class="task-first-part">
              <h4>TITLE</h4>
              <button @click="closeClick()"><closeIcon /></button>
            </div>
            <p class="task-description">Lorem consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit</p>
            <div class="task-last-part">
              <p>TASK 1</p>
              <p>09:00 PM</p>
            </div>
          </div>
        </div>

        <div class="task-container">
          <div>
            <div class="task-first-part">
              <h4>TITLE</h4>
              <button @click="closeClick()"><closeIcon /></button>
            </div>
            <p class="task-description">Lorem ipsum dolor sit amet, elorem tur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit</p>
            <div class="task-last-part">
              <p>TASK 1</p>
              <p>12:30 PM</p>
            </div>
          </div>
        </div>

        <div class="task-container">
          <div>
            <div class="task-first-part">
              <h4>TITLE</h4>
              <button @click="closeClick()"><closeIcon /></button>
            </div>
            <p class="task-description">Lorem ipsum dolor amet, elit elit consectetur amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit</p>
            <div class="task-last-part">
              <p>TASK 1</p>
              <p>14:50 PM</p>
            </div>
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
      font-weight: 200;
      color: #818181;
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
  height: 45vh;
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
  height:100px;
  margin-bottom:20px;
  color: #004655;
  font-size: 18px;
  font-weight: 600;
}

.add-task-button{
  background-color: #FFC85D;
  padding: 8px 15px;
  font-weight: 600;
  border-radius: 5px;
  border: none;
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
