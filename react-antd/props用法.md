## 父子组件之间的传值
```
// 父组件传值
<Modal>
    <TaskForm
        item={editItem}
    />
</Modal>

// 子组件获取父组件传递的值
function() {
    const { item } = this.props
}
```