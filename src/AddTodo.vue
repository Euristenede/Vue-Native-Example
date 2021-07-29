<template>
  <view class="text-input-container">
    <view class="text-input-wrapper">
      <text-input placeholder="Enter new todo" v-model="newTodo"/>
    </view>
    <touchable-opacity class="add-button" title="Button" :on-press="addTodo" :disabled="(newTodo === '')">
      <text class="text-color-primary">ADD</text>
    </touchable-opacity>
    <button
        @press="goToHomeScreen"
        title=" > "
        color="#841584"
        accessibility-label="Próxima página"
    />
  </view>
</template>

<script>
export default {
  props: {
    onAdd: Function,
    navigation: {
      type: Object
    }
  },
  data: function() {
    return {
      newTodo: ''
    };
  },
  methods: {
    addTodo: function() {
      let todo = {
        task: this.newTodo,
        isCompleted: false,
        edited: false
      }
      this.onAdd(todo)
      this.newTodo = ''
    },
    goToHomeScreen() {
      this.navigation.navigate("Sobre");
    },
  }
}
</script>
 
<style>
.text-color-primary {
  color: rgba(0, 0, 0, 0.767);
}
.text-input-wrapper {
  flex: 1;
  border-width: 1;
  border-color: rgb(112, 84, 46);
  justify-content: center;
  padding: 10
}
.add-button {
  background-color: rgba(201, 29, 29, 0.534);
  padding-horizontal: 10;
  justify-content: center;
}
.text-input-container {
  margin-horizontal: 15;
  flex-direction: row;
  padding-bottom: 20
}
</style>
