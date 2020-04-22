# 每周总结可以写在这里

1. 编程语言通识 与 JavaScript语言设计
   
    乔姆斯基谱系 
        0类
        1
        2
        3

    产生式（BNF 巴克斯诺尔范式） ： 定义语言 可递归
        | or
        * any
        + more than one

        eg: 定义十进制数字
        <Number>="0" | "1" |...| "9"
        <DecimalNumber>="0"|(("1" |...| "9") <Number>*) ----------递归

        eg:定义加法
        <AdditiveExpression> = <DecimalNumber> "+" <DecimalNumber>
        <AdditiveExpression> = <AdditiveExpression> "+" <DecimalNumber>

        eg：定义乘法
        <Multiplacative>

2. 
    unicode:
        超过BNP的字符：string.fromCodePoint  "".pointCodeAt
        \u 转译

    InputElement
        WhiteSpace:
                - Tab：制表符（打字机时代：制表时隔开数字很方便）
                - VT：纵向制表符
                - FF: FormFeed
                - SP: Space
                - NBSP: NO-BREAK SPACE（和 SP 的区别在于不会断开、不会合并）
        LineTerminator 换行符
                - LF: Line Feed `\n`
                - CR: Carriage Return `\r`
        
        Comment 注释

        Token 记号：一切有效的东西
            Punctuator: 符号 比如 `> = < }`
            Keywords:
            IdentifierName：标识符，可以以字母、_ 或者 $ 开头，代码中用来标识**[变量][函数][属性]
            Literal:直接量
                Number:
                    DecimalLiteral 
                        • 0.
                        • .2
                        • 1e3
                    BinaryIntegerLiteral  - Ob
                        • 0b111
                    OctalIntegerLiteral  - 0o 
                        • 0o10
                    HexIntegerLiteral -0x
                        • 0xFF
                    -- 比较浮点是否相等：Math.abs(0.1 + 0.2 - 0.3) <= Number.EPSILON
                String：
                    Character 
                        Code Point
                        Encoding
                            unicode编码 - utf
                            utf-8 可变长度 （控制位的用处）
                        Grammar
                        接受三种表达方式`''`、`""`、``` `（反引号）
                Boolean
                Null
                Undefind