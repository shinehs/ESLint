#ESLint (js�﷨��⹤��)
###����Sublime Text 
1.Sublime���� ESLint ��Ҫ������� SublimeLinter �� SublimeLinter-contrib-eslint ��ֱ����Package Controll�а�װ�ͺ�
(Preferences->Package Settings->SublimeLinter)
2.��װESLint�� npm i -g eslint(ȫ�ְ�װ�ͺ���)
3.��װ���޸�SublimeLinter�������ļ�����Package Settings�д���Setting-User�������д��븴�ƽ�ȥ��

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
                "C:/Users/Administrator/AppData/Roaming/npm/eslint.cmd"
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
����Ϊ���߻����µ�SublimeLinter->Setting-User ���ݣ�����ע���޸ı�����Ӧcmd������·����������ɺ�Ϳ��Կ�ʼʹ����~����������֮ǰ���ǻ����ȶ�ESLint����һ�����ã�eslint�����ñȽϴ���������������������̵ĸ�Ŀ¼����Ҫ������Ŀ�У������������ܺã�����˵�ҵ���Ŀ����D:// ������ֱ����һ��.eslintrc�������ļ������ֻ��һ�����ã��������Ŷ�ϰ�ߣ���ô��D������һ�������ˣ�����D://�£�Ȼ��������D://project/   Ŀ¼������һ��.eslintrc������ÿ����Ŀ�Ϳ��Ե���������(�Ƚ��ʺ��Ŷ�Э����)��
�����߱��˵����ã���Ȼÿ���˵�ϰ�߶���ͬ�����Ը����Լ���ϰ�������޸ģ�

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
        //ȫ�ֱ���
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
        "accessor-pairs": 2,  // ��������set��ȡ������ʱ��ǿ�ƶ���get
         // ָ�������Ԫ��֮��Ҫ�Կո����(,����)�� never������[ ֮ǰ�� ] ֮���ܴ��ո�always������[ ֮ǰ�� ] ֮�������ո�  
        "array-bracket-spacing": [2, "never"],  
        "block-scoped-var": 0,  // �ڿ鼶����������ʿ��ڶ���ı����Ƿ񱨴���ʾ  
        "brace-style": [2, "1tbs", { "allowSingleLine": true }],  // if while function �����{������if��ͬһ�У�java��� 
        "camelcase": 2,  // ˫����������ʽ 
        // ����Ͷ����ֵ�����һ�����ţ� never���������ܴ�ĩβ�Ķ���, always�����������ĩβ�Ķ��ţ�  
        // always-multiline������ģʽ��������ţ�����ģʽ���ܴ�����  
        "comma-dangle": [2, "never"],  
        // ���ƶ���ǰ��Ŀո�  
        "comma-spacing": [2, { "before": false, "after": true }],  
        // ���ƶ�������β���ֻ��������׳���  
        // http://eslint.org/docs/rules/comma-style  
        "comma-style": [2, "last"],  
        // Ȧ���Ӷ�  
        "complexity": [2,9],  
        // �Է�����ȡ��������ʱ��[ ����� ] ǰ���Ƿ���Ҫ�ո�, ��ѡ���� never, always  
        "computed-property-spacing": [2,"never"],  
        // ǿ�Ʒ������뷵��ֵ��TypeScriptǿ���ͣ�������  
        "consistent-return": 0,  
        // ����ָͳһ�ڻص�������ָ��this�ı���������ͷ�����е�this�Ѿ�����ָ���������ߣ�Ӧ��û������  
        // e.g [0,"that"] ָ��ֻ�� var that = this. that����ָ�������κ�ֵ��thisҲ���ܸ�ֵ��that���������ֵ  
        "consistent-this": 0,  
        // ǿ�������๹�캯������super()���ø��๹�캯����TypeScrip�ı�����Ҳ����ʾ  
        "constructor-super": 0,  
        // if else while for do����Ĵ�����Ƿ���Ҫ{ }��Χ��������  
        //    multi  ֻ�п����ж������ʱ����Ҫ{ }��Χ  
        //    multi-line  ֻ�п����ж������ʱ����Ҫ{ }��Χ, ���ǿ��е�ִ�����ֻ��һ��ʱ��  
        //                   ���е����ֻ�ܸ���if�����ͬһ�С�if (foo) foo++; else doSomething();  
        //    multi-or-nest ֻ�п����ж������ʱ����Ҫ{ }��Χ, ������е�ִ�����ֻ��һ�У�ִ��������������һ��Ҳ���Ը���if������  
        //    [2, "multi", "consistent"] ����ǰ������{ }һ��  
        //    default: [2, "all"] ȫ����Ҫ{ }��Χ  
        "curly": [2, "all"],  
        // switch���ǿ��default��֧��Ҳ����� // no default ע��ȡ���˴ξ���  
        "default-case": 2,  
        // ǿ��object.key �� . ��λ�ã�����:  
        //      property��'.'��Ӧ��������ͬһ��  
        //      object, '.' ��Ӧ���������ͬһ��  
        "dot-location": [2, "property"],  
        // ǿ��ʹ��.��ȡ����  
        //    ������ allowKeywords��true ʹ�ñ�������������ʱ��ֻ��ʹ��.��ʽȡ����  
        //                          false ʹ�ñ�������������ʱ, ֻ��ʹ��[]��ʽȡ���� e.g [2, {"allowKeywords": false}]  
        //           allowPattern:  ��������ƥ���ṩ��������ʽʱ������ʹ��[]��ʽȡֵ,����ֻ����.��ȡֵ e.g [2, {"allowPattern": "^[a-z]+(_[a-z]+)+$"}]  
        "dot-notation": [2, {"allowKeywords": true}],  
        // �ļ�ĩβǿ�ƻ���  
        "eol-last": 0,  
        // ʹ�� === ��� ==  
        "eqeqeq": [0, "allow-null"],  
        // �������ʽ�Ƿ���Ҫ����  
        "func-names": 0,  
        // ���������񣬲�����  
        //    declaration: ǿ��ʹ�÷��������ķ�ʽ��function f(){} e.g [2, "declaration"]  
        //    expression��ǿ��ʹ�÷������ʽ�ķ�ʽ��var f = function() {}  e.g [2, "expression"]  
        //    allowArrowFunctions: declaration����������ͷ������ e.g [2, "declaration", { "allowArrowFunctions": true }]  
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
    "destructuring": true,  // �⹹��ֵ 
    "classes": true,  
    "defaultParams": true,  // http://es6.ruanyifeng.com/#docs/function#����������Ĭ��ֵ  
    "blockBindings": true,  // �鼶����������ʹ��let const 
    "modules": true, //����ʹ��ģ�飬ģ����Ĭ���ϸ�ģʽ 
    "objectLiteralComputedProperties": true, // �����������������ʱ���ñ��ʽ��������  
    "no-dupe-args": 2, // �����Ĳ������Ʋ����ظ�
    "no-dupe-keys": 2, // ������������Ʋ����ظ�
    "no-duplicate-case": 2, // switch��case�����ظ�
    "objectLiteralShorthandMethods": true, // ���������������������д 
    "restParams": true,  // http://es6.ruanyifeng.com/#docs/function#rest����  
    "spread": true,// http://es6.ruanyifeng.com/#docs/function#��չ�����
    "forOf": true,  // http://es6.ruanyifeng.com/#docs/iterator#for---ofѭ��  
    "generators": true,  
    "templateStrings": true,  // http://es6.ruanyifeng.com/#docs/string#ģ���ַ���  
    "superInFunctions": true,  
    "experimentalObjectRestSpread": true  // http://es6.ruanyifeng.com/#docs/object#�������չ�����
}


�������������ϵ�ʱ�򣬾Ϳ��Կ�ʼʹ��ESLint�Ĵ�����鹦���ˣ���ǿ����һ����
CMD��ʽ��ʹ��eslint ***.js �ķ�ʽ��������eslint�Ļ���Ŀ¼���������⣬��Ȼ���������ʾ���ֶ���ֱ�۵��ڿ���̨��������л���������Ҳ�������������Ի����Ƿ����úã�������eslint������һ���¡�
![Alt text](./1482219512774.png)

�ռ�Ч����
![Alt text](./1482219632641.png)

������ߵ�С�����ô��������﷨���Ľ������Ȼ�㲢��֪����Щ�澯�����壬�𼱣�������eslintһ�£�
![Alt text](./1482219698680.png)

��ô��ֱ��ô��
��ʵESLint������������ĺ�ϸ�£����뵽��������֣���ϡ��������һ���õı���ϰ����ÿ���˶�Ӧ�������ģ����㣡
[���ٷ����ĵ�ַ]( http://eslint.cn/)  http://eslint.cn/
