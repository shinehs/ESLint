#ESLint (js语法检测工具)
###集成```Sublime Text ```
炒鸡简单，呜呜呜开车了！跟着我做就好了！

1.```Sublime```集成 ```ESLint``` 需要两个插件 ```SublimeLinter``` 和 ```SublimeLinter-contrib-eslint``` 直接在Package Controll中安装就好（```Install package->SublimeLinter  and  Install package->SublimeLinter-contrib-eslint```）

2.然后再安装```ESLint```的全局环境： ```npm i -g eslint```(全局安装就好了)

3.安装后修改SublimeLinter的配置文件，让你环境中的eslint与```sublime```关联，在```Package Settings```中打开其```Setting-User```，将下列代码复制进去内容如下：```(Preferences->Package Settings->SublimeLinter)```

```javascript
    {
    "user": {
        "debug": true,
        "delay": 0.25,
        "error_color": "D02000",
        "gutter_theme": "Packages/SublimeLinter/gutter-themes/Default/Default.gutter-theme",
        "gutter_theme_excludes": [],
        "lint_mode": "background",
        "linters": {
            "eslint": {
                "@disable": false,
                "args": [],
                "excludes": []
            },
            "jshint": {
                "@disable": false,
                "args": [],
                "excludes": []
            },
            "php": {
                "@disable": false,
                "args": [],
                "excludes": []
            }
        },
        "mark_style": "outline",
        "no_column_highlights_line": false,
        "passive_warnings": false,
        "paths": {
            "linux": [],
            "osx": [],
            "windows": [
                "C:/Users/Administrator/AppData/Roaming/npm/eslint.cmd" //注意这个路径，对应是你安装ESLint的位置
            ]
        },
        "python_paths": {
            "linux": [],
            "osx": [],
            "windows": []
        },
        "rc_search_limit": 3,
        "shell_timeout": 10,
        "show_errors_on_save": false,
        "show_marks_in_minimap": true,
        "syntax_map": {
            "html (django)": "html",
            "html (rails)": "html",
            "html 5": "html",
            "javascript (babel)": "javascript",
            "magicpython": "python",
            "php": "html",
            "python django": "python",
            "pythonimproved": "python"
        },
        "warning_color": "DDB700",
        "wrap_find": true
    }
}
```
 so : 以上为笔者环境下的```SublimeLinter->Setting-User``` 内容，其中注意修改本机对应```cmd```的命令路径，配置完成后就可以开始使用辣~
 
不过在配置之前我们还是先对```ESLint```进行一下设置，（配置文件为```.eslint```，window用户可用命令提示符生成该文件：```echo {} > .eslintrc ```）配置比较大气，你可以扔在你物理盘的根目录（不需要扔在项目中），这样的做法很好，比如说我的项目都在```D://``` 下那我直接扔一个```.eslintrc```在```D://```根目录下。（配置文件，如果只是一个人用，不考虑团队习惯，那么在D盘扔下一个就行了！他会对整个D盘目录中的项目生效）

如果想对当前项目再独立一份配置，那么就在```D://project/```项目目录下再扔一个```.eslintrc```，这样每个项目就可以单独配置了(比较适合团队协作！)。
上作者本人的配置，当然每个人的习惯都不同，可以根据自己的习惯慢慢修改：

```javascript
    {
    "env": {
        "browser": true,
        "node": true,
	"shared-node-browser":true,
        "es6": true,
	"jquery": true,
	"mocha":true,
	"prototypejs":true,
	"nashorn":true,
	"embertest":true,
	"amd":true,
	"worker":true
    },
    "parser": "babel-eslint",
    "ecmaFeatures": {
       "jsx": true
    },
    "globals": {
        //全局变量
    	"_id": true,
    	"Swipe": true,
        "define":true,
	"user":true,
	"header":true,
	"chrome":true,
	"console":true
    },
    "extends": "eslint:recommended",
    "rules": {
        "semi": [2, "always"],
        "quotes": [2, "single"],
        "accessor-pairs": 2,  // 定义对象的set存取器属性时，强制定义get
         // 指定数组的元素之间要以空格隔开(,后面)， never参数：[ 之前和 ] 之后不能带空格，always参数：[ 之前和 ] 之后必须带空格  
        "array-bracket-spacing": [2, "never"],  
        "block-scoped-var": 0,  // 在块级作用域外访问块内定义的变量是否报错提示  
        "brace-style": [2, "1tbs", { "allowSingleLine": true }],  // if while function 后面的{必须与if在同一行，java风格。 
        "camelcase": 2,  // 双峰驼命名格式 
        // 数组和对象键值对最后一个逗号， never参数：不能带末尾的逗号, always参数：必须带末尾的逗号，  
        // always-multiline：多行模式必须带逗号，单行模式不能带逗号  
        "comma-dangle": [2, "never"],  
        // 控制逗号前后的空格  
        "comma-spacing": [2, { "before": false, "after": true }],  
        // 控制逗号在行尾出现还是在行首出现  
        // http://eslint.org/docs/rules/comma-style  
        "comma-style": [2, "last"],  
        // 圈复杂度  
        "complexity": [2,9],  
        // 以方括号取对象属性时，[ 后面和 ] 前面是否需要空格, 可选参数 never, always  
        "computed-property-spacing": [2,"never"],  
        // 强制方法必须返回值，TypeScript强类型，不配置  
        "consistent-return": 0,  
        // 用于指统一在回调函数中指向this的变量名，箭头函数中的this已经可以指向外层调用者，应该没卵用了  
        // e.g [0,"that"] 指定只能 var that = this. that不能指向其他任何值，this也不能赋值给that以外的其他值  
        "consistent-this": 0,  
        // 强制在子类构造函数中用super()调用父类构造函数，TypeScrip的编译器也会提示  
        "constructor-super": 0,  
        // if else while for do后面的代码块是否需要{ }包围，参数：  
        //    multi  只有块中有多行语句时才需要{ }包围  
        //    multi-line  只有块中有多行语句时才需要{ }包围, 但是块中的执行语句只有一行时，  
        //                   块中的语句只能跟和if语句在同一行。if (foo) foo++; else doSomething();  
        //    multi-or-nest 只有块中有多行语句时才需要{ }包围, 如果块中的执行语句只有一行，执行语句可以零另起一行也可以跟在if语句后面  
        //    [2, "multi", "consistent"] 保持前后语句的{ }一致  
        //    default: [2, "all"] 全都需要{ }包围  
        "curly": [2, "all"],  
        // switch语句强制default分支，也可添加 // no default 注释取消此次警告  
        "default-case": 2,  
        // 强制object.key 中 . 的位置，参数:  
        //      property，'.'号应与属性在同一行  
        //      object, '.' 号应与对象名在同一行  
        "dot-location": [2, "property"],  
        // 强制使用.号取属性  
        //    参数： allowKeywords：true 使用保留字做属性名时，只能使用.方式取属性  
        //                          false 使用保留字做属性名时, 只能使用[]方式取属性 e.g [2, {"allowKeywords": false}]  
        //           allowPattern:  当属性名匹配提供的正则表达式时，允许使用[]方式取值,否则只能用.号取值 e.g [2, {"allowPattern": "^[a-z]+(_[a-z]+)+$"}]  
        "dot-notation": [2, {"allowKeywords": true}],  
        // 文件末尾强制换行  
        "eol-last": 0,  
        // 使用 === 替代 ==  
        "eqeqeq": [0, "allow-null"],  
        // 方法表达式是否需要命名  
        "func-names": 0,  
        // 方法定义风格，参数：  
        //    declaration: 强制使用方法声明的方式，function f(){} e.g [2, "declaration"]  
        //    expression：强制使用方法表达式的方式，var f = function() {}  e.g [2, "expression"]  
        //    allowArrowFunctions: declaration风格中允许箭头函数。 e.g [2, "declaration", { "allowArrowFunctions": true }]  
        "func-style": 0,
	"no-console":0,
	"no-alert": 0,  
	"no-array-constructor": 2,  
	"no-caller": 1,  
	"no-catch-shadow": 1,  
	"no-cond-assign": 1,
	"no-debugger": 1
    },
    "arrowFunctions": true,  
    "destructuring": true,  // 解构赋值 
    "classes": true,  
    "defaultParams": true,  // http://es6.ruanyifeng.com/#docs/function#函数参数的默认值  
    "blockBindings": true,  // 块级作用域，允许使用let const 
    "modules": true, //允许使用模块，模块内默认严格模式 
    "objectLiteralComputedProperties": true, // 允许字面量定义对象时，用表达式做属性名  
    "no-dupe-args": 2, // 函数的参数名称不能重复
    "no-dupe-keys": 2, // 对象的属性名称不能重复
    "no-duplicate-case": 2, // switch的case不能重复
    "objectLiteralShorthandMethods": true, // 允许对象字面量方法名简写 
    "restParams": true,  // http://es6.ruanyifeng.com/#docs/function#rest参数  
    "spread": true,// http://es6.ruanyifeng.com/#docs/function#扩展运算符
    "forOf": true,  // http://es6.ruanyifeng.com/#docs/iterator#for---of循环  
    "generators": true,  
    "templateStrings": true,  // http://es6.ruanyifeng.com/#docs/string#模板字符串  
    "superInFunctions": true,  
    "experimentalObjectRestSpread": true  // http://es6.ruanyifeng.com/#docs/object#对象的扩展运算符
}
```
***当然你还可以把这些配置重写在你的文件中，比如：
```javascript
/* eslint-disable */
function demo(){
  return false;
}
/* eslint-enable */
```
这样这段代码就不会被eslint检测到，再比如：
```javascript
/* eslint no-debugger:1,aaa */
//no-debugger 1 为配置代码中是否可以出现debugger 配置需要这里我设置为出现警告而已 ，你可以可以设置他为error
//aaa为全局变量，这样写ESLint就不会检测他的声明。
function demo(){
  return false;
}

/*end*/
```
重写配置项
***
当你配置完以上的时候，就可以开始使用ESLint的代码审查功能了，来强势走一波！
CMD方式！使用```eslint ***.js``` 的方式在配置了eslint的环境目录下做代码检测，当然，错误和提示文字都会直观的在控制台输出，其中环境的问题也会输出在这里，所以环境是否配置好，可以用eslint命令检查一下下。

![事例](http://ww4.sinaimg.cn/large/639d3769jw1faxbqyv2w8j20hr05ndgn.jpg)

终极效果！
![事例](http://ww2.sinaimg.cn/large/639d3769jw1faxbrln9qgj20rf06qq5b.jpg)

看到左边的小红点了么！这就是语法检查的结果，当然你并不知道这些告警的意义，别急，我们来eslint一下！
![事例](http://ww1.sinaimg.cn/large/639d3769jw1faxbryv3rmj20h30bmq5g.jpg)

怎么样直观么？
其实ESLint的配置真的做的很细致，深入到骨髓的那种！老朽很稀饭！别嫌弃麻烦，少年！DFTBA！来一发吧！
![来一发](http://ww3.sinaimg.cn/large/639d3769jw1faxcslupfgj201b01a74b.jpg)

[附官方中文地址]( http://eslint.cn/)  http://eslint.cn/
