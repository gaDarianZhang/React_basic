- state是一个对象，state属性存在于组件对象上，用于保存可以引起状态变化的属性。这里边的值发生变化时，虚拟DOM就会更新，也会去更新真实DOM。不是通过组件标签的属性传入的。（可以通过props间接传入？？）
- props用于获取组件标签的一些自定义属性，props属性存在于组件对象上，并可以指定特定属性的类型和默认值。是通过组件标签的属性传入的。
- ref是组件标签内的标签的一个特定属性，类似于id的作用。
    1. refs属性存在于组件对象上，自动收集了组件内各个ref的值(当ref的值是一个字符串时)。
    2. `ref={(var1)=>{this.onlyOne=var1}}`箭头函数里边的形参被回调时传入的就是所在的节点，this是组件对象（如果不是箭头函数的话，那this就是undefined了），那么在组件内的函数内`this.anyOne`就是取到了这个节点了。
    3. `ref={this.onlyOne}`,同时实例化对象上还要加上`onlyOne=React.creatRef()`,需要找到该节点时用`this.onlyOne.current`，`this.onlyOne`是一个只包括一个`current`属性的对象。而且，组件内有多少个ref，就要多少个`onlyOne=React.creatRef()【onlyOne为自定义的名字】`

