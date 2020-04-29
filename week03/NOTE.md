# 每周总结可以写在这里

##JavaScript Atom
    ###Grammer
        *简单语句
            ExpressionStatement - a = 1 + 2;
            EmptyStatemen - ;
            DebuggerStatement - debugger;
            ThrowStatement - throw a; runtime error generate type throw;
            ContinueStatement - continue label1; 
            BreakStatement - break label2;
            ReturnStatement - return a;
        *复合语句
            BlockStatement - type:normal
                {
                    xxx - 如果非normal语句出现 执行中断 eg: throw 1;
                }
            LabelledStatement
            IterationStatement
                while(){}
                do{} while();
                for(;;;){} - () 可以放var const let 声明 作用域在forloop之外； var 声明在function内所有地方等效
                for( in ){} - 循环所有的属性 {a:1,b:2}
                for( of ){} - 循环interator - 数组/generator所有元素
                    generator:
                    function *g(){
                        yield 0;
                        yield 1;
                        yield 4;
                    }
            ContinueStatement
            BreakStatement
            SwitchStatement
            Try --type: return ; target:label
            ```
            try() {

            } catch() {

            } finally {

            }
            ```
        *声明
            FunctionDeclaration
            GeneratorDeclaration funtion* foo(){} only contain yield - 分步产生多个值；形成一个无限数列
            AsyncFunctionDeclaration
            AsyncGeneratorDeclaration - for await(){}
            VariableStatement
                ```
                var x=0;
                function foo(){
                    var o = {x:1};
                    x=2
                    with(o){
                        var x=3; //this var make difference. if no var here, 
                                //var 要写在最前面 第一次出现的地方；不要在子结构里用var
                    }
                }
                ```
            ClassDeclaration
                Pre-process BoundNames
            LexicalDeclaration

    ###Runtime 
        Completion Record
            *字段 
                type: normal, break, continue, return, throw
                value: Types
                target: label
        Lexical Environment
    


    ###Types:Object 
        - 任何object都是唯一的；即使object状态一样 也并不相等； **唯一性**
        - 用**状态**描述 object
        - object的改变 即**行为**
            Exercise 狗咬人 咬是谁的行为？， bite 不是狗的行为，anger是狗的行为； hurt是人的行为 - 行为改变状态
            ```
            class Human（）{
                hurt(damage){
                    ...
                }
            }
            ```
        

        - 封装 encapsulation 
        - 复用
        - 结耦 coupling？
        - 多态 ph
        - 继承 heritage

        Object -- Class based
            - 归类 多继承 菱形 c++
            - 分类 单一继承 并且有一个基类

        Object -- Prototype -采用**相似**这样的方式去描述对象;任何对象只描述它**与原型的区别**即可

        Object in javascript
            Object  =>    
                        +    Prototype
            properties =>
                pv对：symbol, string => Data, Accessor
                    Data Property (描述状态): [[value]],writable, enumarable(枚举)， configuratble　
                    Accessor property（访问器 描述行为）: get set enumarable configurable

            访问 - 原型链
            Object API 
                - {}. [] Object.defineProperty
                - Object.create / Object.setPrototypeOf / Object.getPropertyOf
                - new Class extend
                - new Function prototype

           #### Objects in javascript
                Funtion object [[call]]
                    Date() ->return string
                    new Date() =>return object
                **Spectial Objects: **作业** 
                    [Reference Link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
                    Array [[length]] 
                    Object.prototype [[setPropertyOf]]
                    Boolean : Object wrapper of boolean value 
                    ```
                        var x= new Boolean(false); 
                        if(x){//...will execute}
                        
                        var x=false;
                        if(x){//..will NOT execute}
                    ```
                    Symbol Object:
                    ```
                        Symbol('foo') === Symbol('foo')  // false
                        let sym = new Symbol()  // TypeError
                    ```
                
                    WebAssembly : the namespace for all WebAssembly-related functionality.
                    Math: a namespace object for mathematical constants and functions. 
                        All properties and methods are static.
                    Intl: the namespace object for internationalization constructors and other language-sensitive functions
                    Reflect:  a built-in object that provides methods for interceptable JavaScript operations. not constructible, 
                        All properties and methods of Reflect are static
                    Atomatic: provides atomic operations as static methods/
                        Atomics is not a constructor. You cannot use it with a new operator or invoke the Atomics object as a function. 
                        All properties and methods of Atomics are static
                    JSON: The JSON object contains methods for parsing JavaScript Object Notation (JSON) and converting values to JSON. 
                        It can't be called or constructed, and aside from its two method properties, 
                        it has no interesting functionality of its ow
                Host Object: [[call]] [[construct]]

            

       
