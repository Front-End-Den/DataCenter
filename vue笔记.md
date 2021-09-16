# Vue的使用笔记

## Vue里面的模板语法

    1、插值语法、{{data}}这种形式
    ```html
        <div>{{data}}</div>
    ```
    2、指令语法、在标签体里面写v-xxx这种形式
    ```html
        <div v-on:click="methods">内容</div>
        <div v-bind:href="url">内容</div>
    ```

## Vue里面的数据绑定

    1、v-bind单向数据绑定(该绑定一般是对属性标签进行绑定,绑定之后的内容是JS表达式)
    ```html
        <div v-bind:href="url">绑定一个链接</div>
    ```

    2、v-model双向数据绑定(该绑定只能对有value值的标签进行绑定,接收value值)
    ```html
        <input v-model:value="" />
    ```

## Vue里面事件处理

    1、事件绑定：使用v-on或者@进行绑定事件,绑定的事件需要在methods中配置
    2、事件修饰符：默认行为的阻止和立即执行,使用捕获模式,阻止冒泡,事件只触发一次
    3、键盘事件：绑定keyup或者keydown事件即可,注意有些只能在input里面使用

## Vue里面的计算属性

    1、computed配置,该属性适用于对数据的加工,使用了return返回数据
    ```js
        computed:{
            计算属性名:{
                get(){ return this.属性1 + this.属性2 }
                set(value){ this.属性1 = value }
            }
        }
        // 当只有get时,也就是只考虑对数据进行读取,不进行修改时,可以简写
        computed:{
            计算属性名(){
                retrun this.某个属性;
            }
        }
    ```

## Vue里面的侦听属性

    1、watch来侦听某属性的变化,侦听的属性需要提前备好,数据变化会调用handler方法
    ```js
        watch:{
            侦听的属性:{
                deep:true,
                handler(newvalue,oldvalue){
                    console.log("数据改变时,方法被调用。");
                }
            }
        }
    ```

## 条件渲染(v-if、v-else-if、v-else这几个在html结构上需要连着使用,分开使用会报错)

## 列表渲染(v-for="p in data" :key="p.id")

## 列表过滤(本质上是对数据的加工,可以使用计算属性、侦听属性来过滤解决、过滤不会引起原数据的改变)

## 若项目在挂载后需要添加响应式的数据，可以使用Vue.set()进行添加

## 过滤器，Vue.filter(name,callback) / filters:{ },使用在插值语法中用单|来过滤

## v-text显示文本、v-html渲染结构、v-clock、v-once、v-pre

## 自定义指令directives:{ big(){},big:{bind(){},inserted(){},updata(){}}}