<template>
  <view class="container">
    <view class="main">
      <text-input
        :on-add='_onPress'
      />
        <text>testst</text>

        <view class='todo-list-container'>
                <view
                    class='todo-list'
                    v-for='(item, index) in list' :key='index'
                >
                    <todo-item
                            :on-done='index'
                            :on-delete='index'
                            :item="item"
                            :text="item.text"
                    />
                </view>

            <!--<scroll-view>-->
            <!--<view class='todo-wrapper' v-for='(text, index) in list' :key='index'>-->
                <!--<todo-item-->
                        <!--:text='text'-->
                        <!--:selected-index='index'-->
                        <!--:edit-pressed='onEditPressed'-->
                        <!--:edit-todo='editTodo'-->
                        <!--:delete-todo='deleteTodo'-->
                        <!--:cancel-edit='cancelEdit'-->
                        <!--:toggle-task-status='toggleTaskStatus'-->
                <!--/>-->
            <!--</view>-->
            <!--</scroll-view>-->
    </view>
  </view>
</template>

<script>
  import TextInput from './src/TodoInput';
  import TodoItem from './src/TodoItem';
  export default {
    data: {
      newTodo: '',
      list: []
    },
    components: {
      TextInput,
      TodoItem
    },
    methods: {
      _onPress : function(text) {
        this.list.push({
          text: text,
          done: false
        })
        console.log("list",this.list);
      },
      _done: function(index) {
        this.todos[index].isCompleted = !this.todos[index].isCompleted
      },
      _delete: function(index) {
        this.list.splice(index, 1)
      },
    }
  }
</script>

<style>
.container {
  background-color: #333;
  flex: 1;
  padding-top: 40px;
  align-items: center;
}
.main {
  flex: 1;
  max-width: 400px;
  align-items: center;
}
.todo-list-container {
    flex-direction: row;
    flex: 1;
    background-color: orange;
}
.todo-list {
    padding-left: 10px;
    padding-right: 10px;
    color: white;
    background-color: blue;
}

.todo-wrapper {
    margin-horizontal: 15;
    background-color: beige;
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
    margin-vertical: 2.5;
    padding: 10;
    border-radius: 5;
}
</style>

<!--_delete = (index) => () => {-->
<!--const list = [].concat(this.state.list);-->
<!--list.splice(index, 1);-->
<!--this.setState({-->
<!--list,-->
<!--});-->
<!--}-->

<!--_done = (index) => () => {-->
<!--const list = [].concat(this.state.list);-->
<!--list[index].done = !list[index].done;-->

<!--this.setState({-->
<!--list,-->
<!--});-->
<!--}-->