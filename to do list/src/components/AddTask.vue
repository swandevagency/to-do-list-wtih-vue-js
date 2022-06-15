<script>
    export default {
    data() {
        return {
            title: '',
            description: ''
        }
    }
    }
</script>


<template>
    <section>
        <div class="blured-background"> 
        </div>
        <div class="add-task-container">
              <label>Title:</label>
              <input v-model="title" type="text" class="titleInput" />

              <label>Description:</label>
              <textarea v-model="description" class="descriptionInput"></textarea>
              <button class="add-task-button">Add</button>
        </div>
    </section>
</template>


<style scoped lang="scss">
*{
    margin: 0;
}

section{
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.blured-background{
  position: absolute;
  width: 100%;
  height: 100%;
  filter: blur(4px);
}

.add-task-container{
  padding: 50px 30px;
  border-radius: 10px;
  background-color: #00000010;
  width: 100vh;
  height: 42vh;
  display:flex;
  flex-direction:column;
}

.titleInput{
  background-color: #00D1FF;
  padding: 8px 15px;
  font-weight: 300;
  border-radius: 5px;
  border: none;
  color: #004655;
  box-shadow:inset 2px 2px #00000030;
  margin-bottom:10px;
}

.descriptionInput{
  background-color: #00D1FF;
  padding: 8px 15px;
  font-weight: 300;
  border-radius: 5px;
  border: none;
  color: #004655;
  box-shadow:inset 2px 2px #00000030;
  height:100px;
  margin-bottom:20px;
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
</style>