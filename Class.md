## 类(Class)
### 简介
- 类(Class)是ES6为了使得之前生成实例的方法更接近于面向对象的语法
- 类中的 `constructor()` 方法，就是构造函数，`this`关键字和之前一样还是指向实例对象
  - `constructor()` 是内置方法，不可改变
- 非 `constructor()` 方法，也就是，直接写在Class里的方法，相当于定义在 `Class名.prototype` 上的。
- 创建的方法是否是赋值写法，区别是赋值写法相当于在构造函数中创建的，括号写法相当于在原型中创建的
``` js
class Cat {
            constructor(name, age, nickname) {
                this.name = name
                this.age = age
            }
            say() {
                console.log(1111);
            }
            move = () => {
                console.log(2222);
            }
        }
        const cat1 = new Cat('wang', 3) //Cat {name: 'wang', age: 3, move: ƒ}
        console.log(cat1) //{constructor: ƒ, say: ƒ}
        
```
  - 在 class 类中可以直接使用 get 和 set 对属性进行存取描述
    - get 计算属性，对原有的属性进行计算
    - set 修改计算属性 get ，其实就是修改计算属性的来源
  - 静态方法 
    - 就是之前直接使用 构造函数名.xx 创建的
    ``` js
    Person.aaa = '111'
    ```
    - 写法：是直接绑定在 class 上的，也就是 Cat.fun  
      ``` js
      static sayInfo() {
      console.log()
      }
      Cat.sayInfo() 
      ```
    
   - class的继承
   ```js
   class Homecat extends Cat {
            constructor(name, age) {
                super(name, age)
            }
        }
   ```
   