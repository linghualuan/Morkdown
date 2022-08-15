在vue组件中使用原生的点击事件（@click），要在@click后加上'.native'，否则@click会被当成自定义事件

如（<Student @click.native='show'/>）



使用@在父组件中给子组件绑定事件， 如<Student @addTodo='addTodo'/>,

要在子组件中的使用this.$emit('addTodo',要向父组件传递的数据)



向一个对象中添加属性：this.$set(对象名,'属性','属性名')