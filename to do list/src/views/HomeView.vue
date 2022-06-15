<script>
  import searchIcon from '../components/icons/search-icon.vue'
  import closeIcon from '../components/icons/close-icon.vue'
  export default {
  components: {
    searchIcon,
    closeIcon
  }
}
</script>

<template>
  <hero>
    <div class="left-part-of-hero">
      <h1>Company Name To Do List</h1>
      <p>have discipline in your life</p>
      <a>Get Started</a>
    </div>
    <div class="right-part-of-hero">
      
    </div>
  </hero>
  <Section class="list-section">
    <div class="list-section-wrapper">
      <div class="introduction-part">
        <h3>You Have <span>10 Task</span> To Do For Today</h3>
        <p>Thusday, JUNE 9</p>
      </div>
      <p class="greeting">Good Afternoon <span>Arsam</span> </p>
      <input class="task-search-bar" type="text" placeholder="Search for Task...">
      <searchIcon />
    
      <div class="task-container">
        <div>
          <div class="task-first-part">
            <h4>TITLE</h4>
            <button><closeIcon /></button>
          </div>
          <p class="task-description">Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit Lorem ipsum dolor sit amet, elit elit consectetur adipiscing elit</p>
          <div class="task-last-part">
            <p>TASK 1</p>
            <p>12:00 PM</p>
          </div>
        </div>
      </div>
    </div> 
  </Section>  
</template>

<style scoped lang="scss">
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

  a{
    background-color: #FFC85D;
    margin-top: 20px;
    padding: 8px 15px;
    font-weight: 800;
    border-radius: 5px;
    color: #004655;
    box-shadow: 2px 2px #d5d5d5;
  }
  a:hover{
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
    margin-top: 10px;
    margin-bottom: 35px;
    font-weight: 200;
    color: #818181;
    span{
      font-weight: 600;
    }
  }

  .task-search-bar{
    width: 100%;
    border: none;
    outline: none;
    border-radius: 40px;
    font-size: 14px;
    padding: 15px 75px;
    box-shadow: 0px 4px 4px rgb(0 0 0 / 25%);
    margin-bottom: 100px;
    position: relative;
    &::placeholder{
      color:#b5b5b5;
      font-weight: 100;
    }  
  }
}

.search-icon{
    position: absolute;
    left: 95px;
    margin-top: 12px;
}

.task-container{
  width: 100%;
  background-color: #08D5FF;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  padding: 20px 35px;
  box-shadow: 0px 4px 4px rgb(0 0 0 / 25%);


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

</style>
