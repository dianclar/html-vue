# 一、Js-api

```
const声明常量，里面的值不能更改。
但如果是声明数组、对象等非基础数据类型对象，建议使用const声明，原因是这种情况下声明的是指针对象，指向的是内存地址，对对象内容操作并不会影响指针值和地址。
DOM操作文档，BOM操作浏览器。
使用document.querySelector('css')获取css选择器第一个dom对象，document.querySelectorAll('css')获取匹配的伪数组（没有数组方法）。
其他获取对象方法：document.getElementById获取id属性dom对象，document.getElementsByClassName获取class属性dom对象，document.getElementsByTagName获取标签dom对象。
innerText获取/修改dom对象值，innerHTML在此基础上可以解析标签。
需要修改标签的属性就是修改dom对象下的对应属性，style属性中键的单词带连接符的换为小驼峰单词，值为带单位的字符串，中间用;隔开。
className、classList.add/remove/toggle修改class属性。
模板字符串``可以插入变量${}。
dataset获取自己设置的data-xx规范的属性。
函数里声明可以用const，因为函数执行完会销毁，再次调用会得到新的常量，注意函数内不要重新赋值。
环境对象this指向粗略为调用者。
将函数作为其他函数的参数时，该函数为回调函数。
console.log方法打印信息，dir方法打印对象属性。
Window.devicePixelRatio属性为物理像素与逻辑像素比。
Document.documentElement属性为html对象。
setInterval设置间歇定时器，填写函数名/引号内调用函数/匿名函数，需要声明时建议使用let，clearInterval停止间歇定时器。
addEventListener方法绑定事件监听，常用事件有click点击，mouseenter（建议）/over进入，mouseleave（建议）/out离开，focus聚焦，blur失焦，keyup/down键盘，input输入。
事件类型需要字符串，addEventListener第三个参数传递true为捕获执行。
多个同事件的函数都会执行，而on事件没有捕获且只执行最后赋值的函数。
事件函数的第一个参数为事件对象event，type属性为事件类型，clientX/Y属性为光标的窗口位置，offsetX/Y属性为光标的dom元素位置，key/keyCode属性为键盘值。
事件流分为捕获（从大到小）和冒泡（从小到大）阶段，触发事件会传递执行所有父子元素事件函数，事件对象stopPropagation方法阻止事件传递，preventDefault方法阻止默认行为。
removeEventListener方法解除非匿名函数事件，on事件赋空解除。
可以利用事件流实现事件委托，给父元素绑定事件，子元素事件冒泡触发父元素事件，事件对象target属性为子元素对象。
load事件为资源加载完成，DOMContentLoaded事件为文档加载完成，scroll事件为页面滚动，resize事件为窗口更改。
scrollTop/Left属性为滚动的垂直/水平位置，可赋值，值为数字不带单位，offsetTop/Left属性为相对已定位父元素的垂直/水平位置。
clientWidth/Height属性为可见宽高，offsetWidth/Height属性为边框宽高。
new Date()实例化日期对象，参数可以为字符串指定时间，getFullYear()方法获取4位年份，getMonth()方法获取月份（-1），getDate()获取与月有关的天，getDay()获取星期（0为星期天），getHours()获取时，getMinutes()获取分，getSeconds()获取秒。
toLocaleDateString/toLocaleTimeString方法获取格式化时间，getTime方法获取时间戳。
+new Date()/Date.now()方法获取时间戳。
DOM树的每一个内容为DOM节点，有元素节点、属性节点、文本节点。
parentNode属性获取父节点，childNodes获取子节点的伪数组，nextElementSibling/previousElementSibling获取上下兄弟节点。
document.createElement方法创建节点，cloneNode方法克隆节点，传入true同时克隆子节点，appendChild方法将节点追加到父元素末尾，insertBefore方法插入父元素里某元素前面，配合childNodes[0]可以插入到首位。
removeChild方法删除父元素下的节点，与隐藏不同，隐藏时节点还在。
声明函数时后面跟()可以立即执行函数，非箭头函数可以前面加运算符来让函数识别为整体。
touchstart事件为触摸开始，touchmove事件为触摸滑动，touchend事件为触摸结束。
要使用插件，先下载，然后在页面引入css和js。
Window对象包含document和navigator、location、history等。
setTimeout方法设置延时定时器，clearTimeout方法结束延时定时器。
浏览器有两大引擎，一个渲染引擎，一个js解释器。
Js为单线程，为了解决单线程问题出现了同步和异步，同步为顺序执行，在主线程执行，形成执行栈，异步为条件满足执行，分宏任务和微任务。
Js执行机制为先执行同步任务，微任务满足后加入微任务队列，宏任务交给宿主环境，满足后加入宏任务队列，同步执行完成后读取微任务、宏任务，并加入执行栈执行，如此循环称为事件循环。
Location对象保存拆分链接，href属性为访问链接，可赋值跳转页面，search属性为链接携带参数，hash属性为链接哈希值，是spa页面路由#基础，reload方法可以刷新页面，传true可以强制刷新。
navigator对象保存浏览器信息，userAgent属性为浏览器版本平台等信息。
History对象保存层级信息，back方法可以后退页面，forward方法可以前进页面，go方法可以前进后退页面。
localStorage对象可以把数据以键值对存储到本地，多窗口共享，setItem方法存储/修改数据，getItem方法读取数据，removeItem方法删除数据。
SessionStorage对象可以把数据以键值对暂时保存，单窗口共享，关闭浏览器结束，常用方法与localStorage相同。
本地存储只能存字符串，复杂数据可以用JSON.stringify方法转json字符串存储，读取后用parse方法转回来。
数组对象map方法可以遍历数组并返回新数组，回调函数有e、i两个参数，相对于forEach有返回值，join方法可以将数组转字符串，参数传入字符可以指定分割元素的字符。
test/exec方法可以判断字符串是否匹配正则表达式，replace方法替换匹配的字符串。
边界符^匹配行首字符，$匹配行尾字符，^$为精确匹配。
量词*重复次数不限，+重复至少一次，?重复最多一次，{n}重复指定次数，{n,}重复至少指定次数，{n,m}重复指定次数范围。
字符[]匹配字符集合，[^]匹配排除字符集合，.匹配除换行外的字符，|匹配其中一个正则，\d匹配数字，\D匹配排除数字，\w/\W匹配/排除数字字母下划线，\s/\S匹配/排除空字符。
修饰符i不区分大小写，g匹配所有结果。
```

# 二、Es6+

```
局部作用域分为函数作用域和块作用域，参数与函数内声明的变量可以在函数内使用，外部不能直接使用，函数执行结束，函数作用域变量清空。
js的{}内的代码为代码块，块内非var声明的变量产生块作用域，外部不能直接使用。
全局作用域的变量可以被其他作用域使用，但应该尽可能少声明全局变量，避免全局变量污染。
作用域链为底层查找机制，全局和局部可以有同一个变量，函数执行时优先查找当前作用域变量，然后逐级查找父级作用域至全局作用域。
Js的内存分配回收自动完成，变量不在使用时自动回收内存，一般全局变量不会自动回收，在关闭页面时回收。
内存因为某种原因无法回收，称为内存泄漏。
浏览器有两种回收算法，为引用计数法和标记清除法。
引用计数法在对象没有指向的引用时回收，但在堆内嵌套引用时无法回收。
标记清除法从全局对象开始往下查找，能查找到的标记，没有被标记的回收。
内层函数访问外层函数变量构成闭包，如果执行外层函数会返回内层函数，那外部通过返回的内层函数可以访问外层函数变量，且变量不会被回收，可能造成内存泄漏。
var声明的变量会变量提升，被提取到作用域代码最前面，但只提升声明不赋值，所以可以先使用再声明，非箭头函数也有提升。
非箭头函数的动态参数可以不设形参，通过arguments获得实参伪数组。
函数可以通过剩余参数...args作为形参，将实参数组赋值给args，可以同时设置普通参数，但需要设置在最后。
...数组为展开运算符，可以将数组元素提取出来。
箭头函数在形参只有一个的时候可以省略()，代码块只有一行时可以省略{}和return，可以直接返回被括号括起来的对象，this沿用父级作用域this，所以不建议在dom事件、原型中使用箭头函数。
数组解构：[a,b]=arr可以将数组元素同时赋值给不同变量，比元素多的变量不会赋值，可以设置默认值，变量少时也可以使用剩余参数，可以用空位忽略对应元素，可以解构多维数组。
对象解构：{a,b}=obj可以将对象属性方法同时赋值给与属性方法名相同的变量，变量可以通过:改名，可以和数组解构一起解构对象数组，解构对象里的对象需要使用对象名:{}解构。
在函数形参中也可以使用解构，箭头函数时形参需带括号。
数组forEach方法可以遍历数组元素、索引并传递给回调函数，没有返回值，适合在对象数组中使用。
构造函数可以批量创建类似对象，缺点是浪费内存，声明时建议以大写字母开头，使用new实例化，实例化的对象是不同的对象，互不影响，构造函数的属性方法为实例成员，常用的内置构造函数有Object、Array、String、Number，js的基本数据类型都有构造函数，称为包装类型。
Object常用静态方法，keys/values方法可以得到对象所有键/值的数组，assign方法可以拷贝对象，可以用于给对象添加属性。
数组reduce方法可以返回累计处理结果，给回调函数传入处理值和当前值两个实参，可以传初始处理值。
Array.from方法可以把伪数组转数组。
JavaScript是一种多范式编程语言，通过构造函数和原型实现面向对象。
构造函数的prototype属性为原型对象，this指向实例化对象，constructor属性为构造函数。
可以定义方法让对象实例共享，通过赋值实例化对象来继承构造函数，通过原型实现继承为原型继承。
__proto__属性指向上级原型对象，形成原型链，instanceof运算符判断是否在原型链上。
实例对象__proto__属性为对象原型，指向原型对象，不能赋值。
函数内部调用自己形成递归，容易造成内存栈溢出，建议有return。
for...in的实参在处理对象时是键，数组时是索引。
对象.属性可以写为对象[属性]，来处理变量当属性名的情况。
拷贝针对引用类型，浅拷贝只拷基础数据和引用地址，深拷贝的新对象不会影响旧对象，可以用递归函数、调用库、转json字符串实现。
throw new Error()可以抛出自定义错误信息，终止程序，try尝试执行，catch捕获异常，不终止程序，finally在出错时也会继续执行。
debugger定位代码位置。
以下方法指定this指向：call方法、apply方法（需要传数组）、bind方法（不会执行函数，返回拷贝函数）。
防抖是一段时间内不再次触发执行，节流是一段时间内只执行一次。
```

# 三、Ajax

```
Ajax是XMLHttpRequest对象，负责与服务器通信，常用基于Ajax、Promise的axios库。
Axios引入后获得axios函数，基本语法axios({url, method, data:{}, params:{}}).then(d=>{}).catch(e=>{})。
url是统一资源定位符，简称网址，由协议、域名、路径、参数等组成，参数格式为?key=value&。
http协议是超文本传输协议，请求方法一般有get、post、put、delete、patch等。
请求/响应报文包含请求/响应行、请求/响应头、空行、请求/响应体，响应状态码有1xx信息、2xx成功、3xx重定向、4xx客户端错误、5xx服务器错误。
文件上传：input[type=file]的事件对象的target.files属性为文件对象，new FormData实例化表单数据对象，append方法添加文件对象，上传表单数据对象。
new XMLHttpRequest()实例化ajax对象，open方法配置请求方法和url，loadend事件接收响应，send方法发起请求，可以传数据，setRequestHeader('Content-Type', 'application/json')设置请求头。
new Promise((resolve,reject)=>{})实例化对象，默认为pending状态，resolve方法改为fulfilled状态，触发并传参给.then方法回调，reject方法改为rejected状态，触发并传递给catch方法。
.then方法return Promise为链式调用，避免嵌套，all静态方法可以接收多个Promise，参数接收Promise对象数组，返回结果数组。
回调嵌回调多次为回调地狱，耦合高、可读性差、捕错难。
async、await是Promise的语法糖，async关键字声明的函数内允许使用await，await取代then接收Promise状态并返回参数，捕错用try...catch。
new URLSearchParams()接收对象实例化url参数对象，toString方法转参数字符串。
```

# 四、Ts

```
ts是js的超集，ts=type+js，ts是静态类型编程语言，编译时做类型检查。
安装编译器：npm i -g typescript，编译命令：tsc *.ts，执行命令：node *.js，安装简化编译运行器：npm i -g ts-node，简化编译运行命令：ts-node *.ts。
类型注解：var a:number=0中:*即为类型注解，为变量添加类型约束，只能赋值约束的类型，否则报错。
ts新增类型：联合类型、类型别名、接口、元组、字面量、枚举、void、any等。
数组：var a:number[]=[];var a:Array<string>=[]中:*[]或Array<*>即为数组类型，多类型数组可以写:(*|*)[]，与:*|*[]含义不同，|为联合类型，表示多类型的一种。
类型别名：type a=number|string中type*=*即为类型别名，后面可以使用别名作为类型注解。
函数：function a(b:number):void{};const a=(b:number):void=>{};const a:(b:number)=>void=(b)=>{}中function或=>或:(*:*)=>*即为函数类型，需为参数、返回值作类型注解，有返回值一般有return，没有返回值为void。
可选参数：const a=(b?:number):void=>{}中?:*即为可选参数，表示可以没有的参数，需放在其他参数后面。
对象：var a:{b:number;c():void;d?:()=>void}={}中:{*:*}即为对象类型，也可以带可选参数。
接口：interface a{b():void}中interface*{}即为接口类型，在同对象类型多次使用时可以声明接口来复用，后面可以使用接口作为类型注解，注意和类型别名区分，可以使用extends继承其他接口。
元组：var a:[number,string]=[]中:[*]即为元组类型，需知道元素的个数和类型。
类型推论：在未类型注解时，ts自动注解即为类型推论，常在声明变量并赋值或注解函数返回值时自动注解。
类型断言：a as b;<a>b中使用*as*或<*>*即为类型断言，需为父子类型或联合交叉类型，否则报错，使用console.dir方法查看原型链可以知道元素类型。
字面量：const a=0中类型为常量即为字面量类型，可以配合联合类型实现枚举的功能并更高效。
枚举：enum A{B=39}中使用enum*{}即为枚举类型，建议名称与值大写开头，使用.访问枚举成员，枚举值默认从0自增，可以声明时用=给成员自定义默认值，非数字枚举需自定义值，后面可以使用枚举作为类型注解。
any：var a;var a=(b)=>{}中参数或未赋值变量未做类型注解即为any类型，取消类型保护，可以对值任意操作，应尽量避免，仅临时使用。
ts中typeof关键字可以使用在类型注解中，将其他对象的类型作为类型注解，不能获取函数返回值。
class类：class a{b:number;c='0'}中以class*{}即为类类型，使用new关键字实例化类对象，可以设置默认值，constructor方法构造函数，返回值不能类型注解，extends关键字继承父类。
ts中可以使用implements关键字实现接口，public/protected/private关键字控制访问性，readonly关键字表示属性只读，只能在构造函数中赋值，需类型注解，可以使用在接口对象。
ts使用结构化类型系统（Structural Type System），名称不同但有相同结构的两个对象认为是兼容的，接口和类少兼多，也可以互相兼容，函数参数数量类型多兼少，返回值少兼多，回调函数参数会自动注解。
交叉类型：a&b中*&*即为交叉类型，功能类似继承，但对重名属性方法有不同的处理逻辑。
泛型：function a<T>(b:T):T{}中*<*>即为泛型，里面的值为类型变量，extends关键字做泛型约束，keyof关键字获取对象键的联合类型。
泛型工具：Partial<T>创建属性可选的类型，Readonly<T>创建属性只读的类型，Pick<T,K>创建T的K属性的类型，Record<K,T>创建K键T值的类型。
索引签名：{[a:string]:number}中[*:*]即为索引签名类型，js中对象键是字符串类型，数组是特殊对象，键为数字类型。
映射：type a{[key in keyof b]:number}中[*in*]即为映射类型，只能在类型别名中使用。
索引访问：a[b|keyof c]中*[*]即为访问索引类型，表示属性的类型。
类型声明文件.d.ts为js库提供类型信息，不含可执行代码不会编译成js，ts已为js标准api提供类型声明文件，大部分第三方库可以使用npm i @types/*命令下载类型声明文件，declare关键字为js文件中已有的变量声明类型。
命名导出：export var a=0;中export*即为命名导出，可导出多个，import关键字导入，需带{}并写明哪几个。
默认导出：export default a中export default*即为默认导出，不能导出声明，只能导出一个，import关键字导入，无需带{}，名称可自定义，可与命名导出混用。
```

# 五、Git

```
git init初始化本地仓库。
git config --global user.name "Your Name";git config --global user.email "your@email.com"全局配置。
git add . 将工作区保存至暂存区。
git commit -m "message" 提交更新并注释。
git remote add origin <url> 添加远程仓库。
git clone <url> 克隆远程仓库。
git pull origin <branch> 拉取并合并远程分支。
git push origin * 推送本地分支到远程，后续git push即可，-f可以强制同步历史。
git log 基础日志。
git reset 回退到指定版本。
git reset --hard 强制回退到指定版本。
README.md配置说明文件。
.gitignore配置忽略文件：*.*文件、*/文件夹。
```

# 六、Node

```
Node.js是跨平台js运行环境，可以搭建服务器端js程序，编写数据接口，实现前端工程化，基于v8引擎，node环境没有BOM、DOM、Ajax，使用node *.js命令执行js文件。
终端快捷：↑上一条命令，tab补全路径，esc清空命令，cls清空终端，ctrl+c停止服务，ctrl+shift+`在vsc新建终端。
CommonJS标准导出module.exports={}，导入require('*')。
fs读写文件模块：writeFile方法写入文件，参数1必选路径字符串，参数2必选写入内容，参数3可选格式，不能创建路径，会覆盖之前内容。
readFile方法读取文件，参数1必选路径字符串，参数2可选编码格式，参数3必选回调函数。
相对路径以终端为起点而非文件，建议使用绝对路径，__dirname变量获取目录绝对路径。
path路径处理模块：join方法拼接路径，basename方法获取路径的文件名，extname方法获取路径的扩展名。
端口号标记不同功能的服务程序，值0-65535，访问时默认80，localhost/127.0.0.1代表本机域名ip。
http服务器模块：createServer方法得到web服务对象，on方法监听request请求。
req请求对象：url属性请求的地址，method属性请求方式。
res响应对象：setHeader设置响应头，end方法设置响应体并结束响应，listen方法启动，设置端口，执行回调。
模块化提高代码复用性、可维护性，并能按需加载。
模块分内置模块（fs、path、http）、自定义模块（.js）、第三方模块，使用require时会执行模块代码，导入自定义模块可省略.js。
模块作用域是变量函数只能在模块内访问，module对象存储模块信息，exports对象导出模块成员，第三方模块称为包。
npm是软件包管理器：npm init -y初始化并获得package.json文件，npm i安装依赖，i *下载包，@*下载指定版本，-g安装到全局，-D安装到开发，npm uninstall *删除包，npm config set registry=https://registry.npmmirror.com指定源。
包分为项目包、全局包，项目包分开发包、核心包。
项目包在项目中使用，下载到node_modules中，并在package-lock.json文件存储信息，git需在.gitignore忽略node_modules，全局包所有项目使用。
package.json是包管理配置文件，dependencies键保存下载的包，devDependencies键为开发包。
包结构规范：以一个目录包含，顶级目录下带package.json文件，键有name名称、version版本、main入口，可以带description描述、author作者、keywords搜索关键字、license许可协议，可以包含README.md文件，说明安装方式、导入、功能、协议等。
版本规范为三位点分十进制，第一位大版本，第二位功能版本，第三位debug版本，前面增加，后面归零。
开发包：创建文件夹根目录，根目录创建package.json并配置，index.js当入口文件，README.md并写说明，src文件夹，把功能分开写到src文件夹js文件中并导出，在index.js导入导出。
注册npm账号，切官方源，npm login登录，npm publish发布，npm unpublish * --force删除72h内的包。
模块加载后缓存，多次require只执行一次，内置模块优先级最高，自定义模块要路径，查找顺序：文件名-.js-.json-.node，包查找package的main-index.js。

express：
express框架包可以快速搭建web服务器、api服务器，express()获取web服务器，listen方法启动、设置端口、执行回调。
get方法监听get请求，post方法监听post请求，send方法响应请求。
req.query方法获取url参数，req.params方法获取动态参数/:a。
安装nodemon包并使用nodemon *.js命令，可以修改代码后自动重启服务器。
router方法创建路由对象，use方法注册中间件，express.static中间件创建资源服务器，json中间件解析json请求体，urlencoded中间件解析urlencoded请求体。
中间件会对请求预处理，可以使用错误中间件捕获错误，需要注册在其他中间件后面。
第三方中间件body-parser包可以解析请求体，数据大的时候，客户端会触发多次data分批发送数据，完成触发end，内置querystring模块可以处理字符串，parse方法解析为对象。
编写接口一般为send({status:0,msg:'成功',data:*})。
第三方中间件cors包可以解决接口跨域问题，Access-Control-Allow-Origin响应头指定允许访问此资源的域，Headers响应头声明额外请求头信息，Methods响应头声明额外请求方式。
jsonp是通过script src请求并接收函数调用，仅支持get。
mysql包可以连接操作MySQL数据库，createPool({host:'',user:'',password:'',database:''})方法配置并获得mysql数据库对象，query方法执行sql语句并执行接收结果参数回调。
sql语句可以使用?占位符，后续第二个参数里的值赋值给?，通过设置字段表示删除状态，然后使用更新状态模拟删除（软删除）。
web开发模式分服务器端渲染（服务器动态生成html响应，前端性能好，利于seo）和前后端分离（服务器提供api接口，开发/用户体验好，减轻服务器压力）。
cookie可以突破无状态，是存储于浏览器的4kb字符串，由一个键值对和其他可选属性组成，请求时自动发送，域名独立，不具有安全性。
中间件express-session包可以使用session认证，session({secret:'*',resave:false,saveUninitialized:true})配置并要在use方法中注册，后续通过请求对象session属性访问对象，destroy方法清除session信息。
token是加密信息的字符串，通过authorization请求头发给服务器。
jwt分header、payload、signature，需要jsonwebtoken和express-jwt包，定义secret密钥，jsonwebtoken.sign方法生成jwt字符串，express-jwt({secret:*}).unless({path:[*]})配置中间件排除解析，请求对象user属性获取jwt解析信息，token不要加密密码。

webpack：
webpack包是静态打包工具，可以完成把html、css、js、资源等内容进行压缩、整合、转译等前端工程化工作。
npm i webpack webpack-cli --save-dev命令下载，需在package.json文件的script键加值"*":"webpack"，后续通过npm run *命令打包。
在根目录创建webpack.config.js文件可以配置打包出入口和清空目录。
webpack的插件下载后在webpack.config.js文件require引入并在plugins键注册使用，加载器在module键注册使用。
html-webpack-plugin包插件可以打包时生成html，css-loader包加载器可以解析css代码，style-loader包加载器可以把css插入dom。
mini-css-extract插件可以提取css代码，不能和style-loader一起使用，less-loader包加载器可以把less代码编译成css代码。
webpack.config.js文件mode键配置打包模式，resolve键alias键可以配置src路径为@，建议配置cdn加载。
```

# 七、MySql

```
数据库是存储管理数据的仓库，MySQL是一个开源免费流行的数据库，一般每个项目对应独立数据库，不同数据存于不同表。
开发一般安装server和workbench，server存储管理数据，workbench可视化管理。
mysql -u * -p连接MySQL 3306端口。
SHOW DATABASES;显示所有数据库。
CREATE DATABASE *创建数据库。
DROP DATABASE *删除数据库。
USE *切换数据库。
SELECT DATABASE()查看当前使用的数据库。
SHOW TABLES;查看所有表。
DESC *查看表结构。
CREATE TABLE * (* * *)创建表。
DROP TABLE *删除表。
ALTER TABLE * RENAME TO *修改表名。
ALTER TABLE * ADD * *添加列。
ALTER TABLE * DROP COLUMN *删除列。
INSERT INTO 表名 (列1, 列2) VALUES (值1, 值2);插入数据。
SELECT * FROM 表名; -- 查询所有列。
SELECT 列1, 列2 FROM 表名 WHERE 条件;查询数据。
UPDATE 表名 SET 列名=新值 WHERE 条件;更新数据。
DELETE FROM 表名 WHERE 条件;删除数据。
TRUNCATE TABLE 表名;清空表数据。
sql是结构化查询语言，是访问和处理数据库的编程语言，用sql编写的代码称为sql语句，在关系型数据库sql中使用。
-- 为注释，关键字对大小写不敏感。
order by *可以升序，desc降序，count(*)给出数量。
```

# 八、终端命令

```
# 文件
当前目录：ls，dir
切换目录：cd，cd;返回上级：cd ..,cd ..;到根目录：cd /，cd \
创建目录: mkdir，mkdir
删除文件: rm，del
删除目录: rm -rf，rmdir /s /q
复制文件: cp，copy
复制目录: cp -r，xcopy /e
移动文件: mv，move
查看文件: vim，vim
查找文件: find . -name，dir /s /b
文件权限: ls -l，icacls
vim命令：i进入编辑，esc退出编辑，:wq保存退出，:q!强制退出，:q退出。

# 网络
测试连通：ping，ping
本机IP：ipconfig，ipconfig
端口占用： netstat -tlnp，netstat -ano
网络请求：curl，curl

# 系统
清屏: clear，cls
打印：echo，echo
查看进程：top，tasklist
结束进程：kill，taskkill /F /PID
磁盘空间：df -h，wmic logicaldisk get size,freespace
内存空间：free -h，systeminfo
设置环境变量：export VAR=value，set VAR=value
查看环境变量：echo $VAR，echo %VAR%
```

# 九、Html-Vue

```
vue是用于构建用户界面的渐进式框架，创建vue实例为导入vue包，new Vue()实例，配置el、data项。
{{*}}为插值表达式，需要有数据，包含表达式而不是语句，不能在标签里使用，不能解析标签。
响应式是数据改变时dom自动更新。
指令是v-开头的标签属性：v-html为innerHTML，v-show为display，v-if为渲染条件，v-else/v-else-if需紧挨着v-if，v-on/@为注册事件。
函数放在methods里，访问data的变量要用this，v-bind/:为动态标签属性，v-for基于数据渲染元素。
key为唯一标识，key只能为字符串和数字，需唯一不变，尽量不使用index，v-model为表单数据双向绑定。
指令修饰符为某些关键字添加.*，实现不同的操作，如@keyup.enter按下回车事件，v-model.trim去空格，.number转数字，@事件.stop阻止冒泡，.prevent阻止默认行为。
:class属性可以为对象数组，对象键为类名，值为布尔值，:style属性可以为对象。
计算属性是基于已有属性求得的新属性，在computed中声明，*(){return}，使用同响应式属性一致，简写只能读取，*:{get(){},set(*){}}可以修改。
watch:{*(n,o){}}监听器，在数据变化后执行函数，*:{*:*,handler(n,o){}}可以额外配置deep和immediate。
```

# 十、Cli-Vue2

vue cli 是官方提供的集成 webpack 的脚手架工具

一、安装

```
# cmd
npm i @vue/cli -g
```

二、查看版本

```
# cmd
vue --version
```

三、创建项目

```
# cmd
vue create \*
```

四、启动项目

```
# cmd
npm run serve
```

package.json.scripts 查看修改启动命令

五、打包

```
# cmd
npm run build
```

默认绝对路径，可配置 vue.config.js 改为相对路径

```
// vue.config.js
module.exports = defineConfig({
  publicPath:'./'
})
```

六、vscode 设置

trigger on tab 可以将输入的字母加数字内容按 tab 变成标签。

## 项目结构

```
VUE
├── dist # 打包完可以上线的项目目录#
├── node_modules # 第三方依赖包存储目录（自动生成）
├── public # 静态资源目录（无需编译处理）
│ ├── favicon.ico # 浏览器标签页图标
│ └── index.html # 主页面模板文件 ③
├── src # 核心源代码目录
│ ├── api # 接口目录#
│ ├── assets # 静态资源（图片/字体等）
│ ├── components # 通用组件库
│ ├── mixins # 混入目录#
│ ├── router # 路由目录#
│ ├── store # vuex状态目录#
│ ├── utils # 封装的工具函数
│ │ ├── EventBus.js # 事件总线#
│ │ ├── request.js # 请求封装#
│ │ └── storage.js # vuex持久化工具#
│ ├── views # 页面组件目录#
│ ├── App.vue # 根组件文件 ②
│ └── main.js # 入口文件 ①
├── .gitignore # Git版本控制忽略文件
├── babel.config.js # Babel转码配置
├── jsconfig.json # JavaScript项目配置
├── package.json # 项目配置文件（名称/版本/依赖等）
├── README.md # 项目说明文档（本文件）
├── vue.config.js # Vue CLI扩展配置
└── yarn.lock # Yarn依赖版本锁定文件（未使用yarn）
```

一、1.main.js（入口文件）

初始化 Vue 实例，引入核心包和根组件，渲染 index.html

```
// main.js
import Vue from 'vue' // 导入vue核心包
import App from './App.vue' // 导入app组件
Vue.config.productionTip = false // 关闭环境提示
new Vue({ // 实例化Vue对象，配置项render，把App组件渲染到index.html的#app元素上
  // .$mount('#app')和el:'#app'功能相同
  // el: '#app',
  render: h => h(App) // 基于app组件，创建DOM节点并返回
}).$mount('#app')
```

二、2.App.vue（根组件）

包含页面模板、样式和逻辑

三、3.index.html（主页面）

包含挂载容器：`<div id="app">`，引入打包后的 JS/CSS 文件

```
<!-- html -->
<body>

<!-- 提示不支持js -->
<noscript>
    <strong>We're sorry but <%= htmlWebpackPlugin.options.title %> doesn't work properly without JavaScript enabled. Please enable it to continue.</strong>
</noscript>

<!-- 提供id为app的vue挂载容器 -->
<div id="app"></div>

<!-- built files will be auto injected -->
</body>
```

## 运行流程

```
npm run serve
│
v
main.js <—— app.vue
│
v
index.html
```

## 组件化开发

将页面拆成一个个组件，便于维护，复用，提升开发效率

一、分类

组件分为普通组件和根组件
组件由 template 结构，script 行为，style 样式组成

二、普通组件使用

1、局部注册

在 component 文件夹创建组件
使用时用 import 导入 component: {\*}注册后当标签使用

2、全局注册

在 main.js 中 import 导入 vue.component('_',_)注册

3、规范

组件名使用多单词大驼峰命名法
组件的 data 是一个函数，为了保证组件实例的 data 独一份。

4、局部样式

使用 scoped 关键字让样式只作用当前组件 `<style scoped>`
作用是为组件所有元素添加 data-v-hash 属性，css 选择器添加对应的属性选择器

三、组件的通信

通过 props，$emit，provide，inject，eventbus，vuex 方法通信

5、prop

prop 是组件的自定义属性，props 可以对数据做校验，有类型校验，非空校验，默认值，自定义校验，

```
// 类型校验
{ *: 类型 }，

// 其他校验
{
  *: {
    type:类型,
    required:空值,
    default:默认,
    validatop: {
      return自定义
    }
  }
}
```

prop 和 data 属性都可以为组件提供数据，prop 数据不能自己改
父组件的数据更新会通过 prop 影响子组件，称为单向数据流

6、父传子

子组件标签的属性会被子组件 props 数组，对象接收

7、子传父$emit

子组件方法传递的事件和参数会被子组件标签对应的事件监听接收

8、event bus 通信

创建 utils/EventBus.js，导入并实例化 vue 作为事件总线，事件总线组件$emit方法传递的事件和参数会被自己所有$on 方法监听的对应事件接收

9、provide/inject 跨层通信

provide 方法 return 的变量会被下层组件 inject 数组接收，变量为引用类型时是响应式的

## v-model

v-model 是一个语法糖

一、底层实现

```
<!-- html -->
<input v-model="data"/> => <input :value="data" @input="data = $event.target.value"/>
```

v-model 为不同表单绑定不同的属性和事件，$event 可以获取事件形参

二、在封装的组件里使用

由于子组件不能直接修改父组件的数据，使用要拆解 v-model

```
<!-- html -->
<!-- 子： -->
<input :value="value" @input="$emit('input', $event.target.value)" />

<!-- 父： -->
<son :value="data" @input="data = $event" /> => <son v-model="data" />
```

三、sync 修饰符实现

```
<!-- html -->
<!-- 子： -->
<input :value="data" @input="$emit('update:data',$event.target.value)" />

<!-- 父： -->
<son :data="value" @update:data = "value = $event"/> => <son :data.sync="value" />
```

## ref

```
// js
this.$refs.* // 用于获取当前组件ref属性为*的dom元素和组件实例，可以调用组件方法
```

## $nextTick,$set

vue 是异步更新 dom 的，$nextTick方法可以确保dom已经更新。
部分情况下直接赋值会破坏变量响应性，$set 可以保证赋值后变量的响应性

## 自定义指令

自定义指令可以封装 dom 操作
组件加载时执行 inserted，值变化时执行 updata
el 为绑定的元素，bindin 可以获取值

一、全局注册

```
// js
Vue.directive(
  '*',
  {
    inserted(el,binding) { el.*() },
    updata(el,binding) { el.* = binding.value }
  }
)
```

二、局部注册

```
// js
directives: {
  '*',
  {
    inserted(el,binding) { el.*() },
    updata(el,binding) { el.* = binding.value }
  }
}
```

## 插槽

可以自定义组件的某些结构
需在组件自定义部分使用 slot 元素，使用时在组件元素内传递结构。
slot 元素内的内容为默认内容

一、具名插槽

需要多个自定义部分时，可以给 slot 元素添加 name 属性
使用时在组件元素内添加<template v-slot="name"/#name>元素定义对应的 slot，默认插槽名为 default

二、作用域插槽

slot 元素添加的属性值，可以被#name="\*"接收

## 路由

确定路径和组件关系
扩展：路由器为设备和 ip 的映射

一、单页应用

spa-single page application
所有功能在一个页面上实现，按需更新
性能高，开发快，初始加载慢，seo 不友好
适合系统、内部网站、移动端等

二、VueRouter

响应式路径组件,改变路径切换组件

1、下载

```
# cmd
npm i vue-router@3*
```

2、引入

```
// js
import VueRouter form 'vue-router'
```

3、注册

```
// js
Vue.use(VueRouter)
```

4、实例化

```
// js
const router = new VueRouter()
```

5、注入

```
// main.js
new Vue({
  render: h => h(app),
  router
}).$mount('#app')
```

6、配置目录

src 目录下创建 views 目录，将需要路由的组件配置到 views 目录

7、配置规则

```
// router.js
import...

VueRouter({
  routes:[
    {path: '*', component: *}
  ]
})
```

8、配置出口

```
<!-- html -->
<router-view />
```

9、规范

页面组件配置在 views 目录下，复用组件配置在 components 目录下，本质无区别

10、封装

src 目录下创建 router/router.js
导入 vue
导出 router
导入注入 main.js

11、router-link

```
<!-- html -->
<router-link to="*" />
```

提供 class 类名 router-link/-exact-active
相当于$router.push()

自定义类名

```
// js
VueRouter({
  linkActiveClass: '*',
  linkExactActiveClass: '*'
})
```

12、传参

跳转组件传参

查询参数

```
// js
$route.query.* // 获取url参数
```

适合多参数

动态路由

```
// js
$route.params.* // 获取配置 path:'url/:*?...' 规则后 url/* 传递的参数
```

13、重定向

```
// router.js
{ path: '/*', redirect:'/*' }
```

14、自定义 404

```
// router.js
{ path: '*', component: *} // 配置在末尾
```

15、路由模式

```
VueRouter({
  mode:"history/hash"
})
```

history 模式取消#，需后端配合

16、js 跳转

```
// js
this.$router.push('/*')
this.$router.push({ path: '*', query: { *: * } })
```

命名跳转

```
// router.js
{ path: '*', name: '*' }
// js
this.$router.push({ name: '*', params: { *: * } })
```

适合 path 字段较长时

17、二级路由

```
// router.js
{ path:'/*', children: [] }
```

18、返回

```
// js
this.$router.back()
```

19、路由守卫

```
// router.js
const nologinlist = ['*']
router.beforeEach((to, from, next) => {
  if (!nologinlist.includes(to.path) && !store.state.user.user.token) {
    next('/login')
  }
  next()
})
```

20、路由懒加载

```
// router.js
{ path: '*', component: () => import('*') },
```

三、keep-alive

缓存组件，防止销毁，本身不会被渲染
缓存后 created，mounted，destroyed 不再触发
新增 activated 和 deactivated 钩子

21、include

匹配的组件缓存

22、exclude

匹配的组件不缓存

23、max

缓存上限

## 编码规范

一、eslint

错误高亮，自动修复错误，格式化代码
需要项目以根目录打开

```
# cmd
npm install eslint@8 --save-dev
npx eslint --init # 可选，生成配置文件
npx eslint . # 检查
npx eslint . --fix # 自动修复
```

```
// .eslintignore
dist/
node_modules/
```

```
// package.json
"scripts": {
  "eslint": "eslint ."
  "eslint:fix": "eslint . --fix"
},
```

```
// .eslintrc.js
module.exports = {
  root: true, // 设为根目录
  env: {
    node: true, // node 环境
  },
  parserOptions: {
    ecmaVersion: 'latest', // 最新 ES+ 规范
  },
  extends: [ // 规则集，需安装合适版本
    'eslint:recommended', // eslint 推荐规范
    'plugin:vue/essential', // vue 推荐规范
    'plugin:prettier/recommended',  // prettier 推荐规范
  ],
  rules: { // 配置规则
    'no-unused-vars': 'warn', // 未使用变量仅警告
    'no-empty': 'warn', // 空代码块仅警告
  },
}

```

二、prettier

统一编码风格，格式化代码

```
# cmd
prettier --write . # 格式化代码，需全局 prettier 包
```

```
// .prettierrc
{
  "semi": false, // 不加分号
  "singleQuote": true, // 使用单引号
  "singleAttributePerLine": true, // 每行一个属性
  "arrowParens": "avoid" // 单参数省略括号
}
```

## vuex

状态管理工具

一、安装

npm install vuex@3

二、创建

src 目录下创建 store/index.js

三、配置

```
// store.js
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
const store = new Vuex.Store()
export default store
```

四、state

```
// store.js
Vuex.Store({
  state: {
    *: *
  }
})

//js
$store.state.* // 获取*的数据
```

1、mapState

映射 state

```
// js
import { mapState } from 'vuex'

computed: {
  ...mapState(['*'])
}
```

五、mutations

vuex 为单向数据流，不能直接修改，mutations 用于修改

```
// store.js
Vuex.Store({
  mutations: {
    *(state, *) {
      *
    }
  }
})

// js
$store.commit('*', *) // 调用
```

只能传递一个载荷

2、mapMutations

映射 mutations

```
// js
import { mapMutations } from 'vuex'

methods: {
  ...mapMutations(['*'])
}
```

六、actions

mutations 不能处理异步，actions 用于处理异步

```
// store.js
Vuex.Store({
    actions: {
    *(context, *) {
      context.commit('*', *)
    }
  }
})

// js
$store.dispatch('*', *) // 调用
```

3、mapActions

映射 actions

```
// js
import { mapActions } from 'vuex'

methods: {
  ...mapActions(['*'])
}
```

七、getters

基于 state 的计算数据

```
// store.js
Vuex.Store({
  getters: {
    *(state) {
      return * // 必须有返回值
    }
  }
})
```

4、mapGetters

映射 getters

```
// js
import { mapGetters } from 'vuex'

computed: {
  ...mapGetters(['*'])
}
```

八、modules

src 目录下创建 store/modules/\*.js

```
// modules/*.js
const state = {}
const mutations = {}
const actions = {
  *(context, *) {
      context.commit('*', *) // 调用自己的'*'
      context.commit('*', *, { root: true }) // 调用全局的'*'
    }
}
const getters = {}

export default {
  // namespaced: true, // 开启命名空间
  state,
  mutations,
  actions,
  getters
}

// store.js
Vuex.Store({
  modules: {
    *
  }
})

$store.state.*.* // 访问
```

5、module 命名空间

默认挂载在全局
通过 namespaced:true 开启命名空间，挂载于 module

```
$store.state.*.* // 访问
...map*('*',['*']) // 映射
$store.commit/dispatch('*/*', *) // 调用
```

九、vuex 持久化

src/utils 目录下创建 storage.js

```
// @/utils/storage.js
export const getstorage = (key) => {
  const data = localStorage.getItem(key)
  return data ? JSON.parse(data) : data
}
export const setstorage = (key,obj) => {
  localStorage.setItem(key, JSON.stringify(obj))
}
export const rmstorage = (key) => {
  localStorage.removeItem(key)
}

// store.js
import { getstorage,setstorage } from "@/utils/storage"
const key = *
const state = {
    user:getstorage(key)
}
const mutations = {
  setuser(state, data) {
    state.user = data
    setstorage(key, data)
  }
}
```

## json-server 库

api 接口服务工具

一、安装

```
# cmd
npm i json-server -g
```

二、配置

将数据存入 db/index.json

三、运行

```
# cmd
json-server index.json
```

## 请求封装

将所有请求函数从页面中抽离并封装为模块

一、安装 axios

```
# cmd
npm i axios

// 调用
axios(
  {
    url，
    method，
    data{}，
    params{}
  }
).then(
  d=>{}
).catch(
  e=>{}
)
```

二、配置实例

src/utils 目录下创建 request.js

```
import axios from 'axios'

const instance = axios.create({ // 创建实例
  baseURL: 'https://localhost/api/', // 请求地址
  timeout: 1000, // 请求超时时间
  headers: {} // 请求头
})

// 添加请求拦截器
instance.interceptors.request.use(
  function (config) {
    // 在发送请求之前做些什么
    return config
  },
  function (error) {
    // 对请求错误做些什么
    return Promise.reject(error)
  },
)

// 添加响应拦截器
instance.interceptors.response.use(
  function (response) {
    // 对响应数据做点什么
    return res
  },
  function (error) {
    // 对响应错误做点什么
    return Promise.reject(error)
  },
)

export default instance

// 简单封装
export const get = (url, params, config) => instance.get(url, { params, ...config })
export const post = (url, data, config) => instance.post(url, data, config)
export const put = (url, data, config) => instance.put(url, data, config)
export const del = (url, params, data, config) => instance.delete(url, { params, data, ...config})
```

可以按需求配置 error 和 loading 封装

三、配置 api 模块

src 目录下创建 api/\*.js

```
// api/*.js
import { get, post, put, del } from '@/utils/request.js'
import request from '@/utils/request.js'

export const getapi = data => get('/url',data)
export const postapi = data => request.post('/url',data)
```

## Ui

一、vant-ui 库

移动端 ui 组件库
文档：https://vant-ui.github.io/vant/v2/#/zh-CN/

二、移动适配

100vw 为屏幕宽

三、postcss 库

自动将 px 转为 vw

1、安装

```
# cmd
npm i postcss-px-to-viewport -D --legacy-peer-deps
```

2、配置

根目录创建 postcss.config.js

```
// postcss.config.js
module.exports={
  plugins: {
    'postcss-px-to-viewport': {
      viewportWidth:375
    }
  }
}
```

## mixins

将 vue 组件实例的 data methods 等配置项混入到组件
配置同名时优先组件内部配置，生命周期都会执行
src 目录下创建 mixins/\*.js

```
// mixins.js
export default {
  data() {
    return {}
  },
  created() {},
  methods: {},
}

// js
// 按需引入
import mixins from './mixins/*';
export default {
  mixins:[mixins],
}

// main.js
// 全局引入
import mixins from './mixins/*';
Vue.mixin(mixins)
```

# 十一、Vite-Vue3

更易维护
更快速度
更小体积
更优响应

## 构建 Vue 项目 create-Vue

cli 基于 webpack
create 基于 vite

一、初始化

```
# cmd
npm init vue@latest
```

二、安装依赖

```
# cmd
npm i
```

三、运行

```
# cmd
npm run dev
```

四、vue-official

vscode 的语法插件

## 目录变化

一、vite.config.js

基于 vite 的配置文件

二、main.js

```
// main.js
new Vue() => createApp()
createRouter() createStore()
```

封装实例保障独立性

三、App.vue

先 `<script setup/>`，再 `<template/>`,后 `<style/>`
允许多个多根元素

## 组合式 api

一、Setup

早于 beforecreate 钩子
this 为 undefined
需要 return

```
<!-- html -->
<!-- 为Setup的语法糖，省略return -->
<script setup></script>
```

二、reactive

需导入
接受对象并返回响应式对象

三、ref

需导入
接受数据并返回响应式对象
通过 value 属性获取，<template/>里不需要
推荐统一使用 ref

四、computed

需导入
作用与 vue2 一致

```
// js
const * = computed(() => {
  return *
})
```

五、watch

需导入
作用与 vue2 一致

```
// js
watch(*, (n, o) => *, { immediate, deep })
```

1、监听多数据

```
watch([*, *], (n, o) => *)
```

2、监听具体属性

```
watch(() => *.*, (n, o) => *)
```

六、生命周期

需导入

```
// js
beforeCreate/created => setup
beforeMount/mounted => onBeforeMount/onMounted
beforeUpdate/updated => onBeforeUpdate/onUpdated
beforeDestroy/destroyed => onBeforeUnmount/onUnmounted
```

七、props

通过 defineProps 编译器宏挂载，解析时转换

```
// js
const props = defineProps(['*'])
props.* // 获取

<!-- html -->
{{ * }}
```

八、emit

通过 defineEmits 编译器宏挂载，解析时转换

```
// js
const emit = defineEmits(['*'])
emit('*', *)
```

九、模板引用

需导入 ref
先创建 ref 对象，然后在元素 ref 里绑定

```
// js
const * = ref()

<!-- html -->
<* ref="*" />
```

十、defineExpose

setup 内的属性和方法默认不暴露

通过 defineExpose 指定暴露的属性和方法

```
// js
defineExpose({*})
```

十一、provide&inject

跨层通信,可以传递方法
provide 方法传递的参数会被 inject 方法接收

```
// js
provide('*', *) // 组组件

const * = inject('*') // 子组件
```

十二、defineOptions

vue3.3 以上，定义 options api 选项

```
// js
defineOptions({
  name: '',
})
```

十三、v-model

vue3.3 以上
原使用 props&emit 实现双向绑定

```
<* :modelValue="*" @update:modelValue="* = $event"> => <* v-model="*"/>
```

3、defineModel

前期版本需导入和配置 vite.config.js
通过 defineModel 实现双向绑定，可直接“修改”

```
// js
const * = defineModel()
```

## pinia

vue3 的状态管理工具，vuex => pinia
更简单的 api，组合式 api

一、安装

```
# cmd
npm i pinia
```

二、配置

main.js 创建 pinia 实例并应用

```
// main.js
import { createApp } from 'vue'
import App from './App.vue'
import { createPinia } from 'pinia'
const pinia = createPinia()
createApp(App).use(pinia).mount('#app')
```

三、使用

src 目录下创建 store/\*.js

```
// store.js
import { defineStore } from 'pinia
```

1、选项式

```
// store.js
import { defineStore } from "pinia";
export const use*Store = defineStore('*',{
  state: () => {
    return {*}
  },
  actions: {
    *() {
      this.* = *
    },
  },
  getters: {
    *: (state) => {
      return state.*
    }
  },
})

// js
import { use*Store } from '@/store/*'
*().*
```

2、组合式

```
// store.js
import { defineStore } from "pinia";
import { computed, ref } from "vue";
export const use*Store = defineStore('*', () => {
  const * = ref(*) // state
  const * = () => *.value = * // action
  const * = computed(() => *.value = *) // getter
  return{*}
})

// 使用同上
```

四、storeToRefs

需导入
Store 属性不能解构，否则丢失响应式，方法可以解构
可使用 storeToRefs 解构

```
// js
const {*} = storeToRefs(*())
```

五、pinia-plugin-persistedstate

pinia 持久化插件
与 vuex-persistedstate 相似的 api

3、安装

```
# cmd
npm i pinia-plugin-persistedstate
```

4、注册

src/main.js 下

```
// main.js
import { createApp } from 'vue'
import App from './App.vue'
import { createPinia } from 'pinia'
import persist from 'pinia-plugin-persistedstate'

const pinia = createPinia()
createApp(App).use(pinia.use(persist)).mount('#app')
```

5、使用

```
// store.js
export const use*Store = defineStore('*',{
  ...,
  persist: true
})

export const use*Store = defineStore('*', () => {}, { persist: true })
```

6、配置

```
// store.js
persist: {
  key: '*', // 指定存储的 key
  storage: sessionStorage, // 指定存储方式，默认 localStorage
  paths: ['*'] // 指定持久化的属性
}
```

## router

```
# cmd
npm install vue-router@4
```

```
// router.js
import { createRouter, createWebHistory, createWebHashHistory } from 'vue-router'

const routes = [
  { path: '/', component: () => import('./*') }
]

export default createRouter({ // 创建路由实例
  history: createWebHistory(), // 使用 history 模式，参数为路径前缀，可为环境变量
  routes,
})
```

```
// main.js
import router from './router'

createApp(App).use(router).mount('#app')
```

```
<!-- html -->
<router-view />
```

```
// js
useRouter() // 获取 router 对象
useRoute() // 获取 route 参数
```

一、beforeEach

不再需要 next

```
// router.js
router.beforeEach((to, from) => {
  if (*) return '/*' // true/undefined放行，false返回，url 跳转
})
```

## 配置husky

用于git commit提交时执行命令

```
# cmd
pnpm dlx husky-init && pnpm i
```

```
# .husky/pre-commit
# export PATH="/c/Program Files/nodejs:$PATH"
echo *
pnpm *
npx *
```

一、配置环境

使用时，需保证所有环境支持node

二、配置lint-staged

用于只校验暂存区

```
# cmd
pnpm i lint-staged -D
```

```
// package.json
"scripts": {
  "lintstaged": "lint-staged"
},
"lint-staged": {
  "*.{vue,js,ts}": [
    "eslint --fix"
  ]
}
```

```
# cmd
pnpm lint-staged
```

```
# .husky/pre-commit
npx lint-staged
```

## 环境变量

import.meta.env 对象暴露的内建变量
import.meta.env.BASE_URL 为 vite.config.js 中的 bash 项

# 十二、Uniapp

基于vue的跨端框架
一套代码，多端开发

## 创建项目

一、hbuilder 创建

选择默认模板和 vue3
小程序工具需开启服务端口
可选择窗口分离
可选择编译模式
手机调试需 id

二、命令行创建

```
# cmd
npx degit dcloudio/uni-preset-vue#vite-ts _
cd _
pnpm i # 安装依赖
pnpm run dev:mp-weixin # 编译小程序
```

小程序工具导入 dist 目录

1、vscode 适配

// 插件
uni-create-view // 创建页面
uni-helper // uni 提示
uniapp 小程序扩展

// 配置

```
// .vscode\settings.json
"files.associations": {
    "\*.json": "jsonc" // 允许注释
}
```

```
# cmd
npx prettier --write . --list-different # 格式化全部代码
```

2、ts 适配

```
# cmd
pnpm i -D @types/wechat-miniprogram @uni-helper/uni-app-types
pnpm i -D @uni-helper/uni-ui-types
```

```
// tsconfig.json
"types": [
    "@dcloudio/types",
    "@types/wechat-miniprogram",
    "@uni-helper/uni-app-types",
    "@uni-helper/uni-ui-types"
]
```

## 目录结构

```
uniapp
    ├pages 页面文件目录
    ├static 静态资源目录
    ├unpackage 编译资源目录
    ├App.vue vue 根文件
    ├index.html 挂载文件
    ├main.js 入口文件
    ├manifest.json 打包配置文件
    ├pages.json 页面配置文件
    ├uni.promisify.adaptor.js
    └uni.scss 常用变量样式
```

## pages.json 配置

```
// pages.json
{
    "pages": [ // 路由及页面配置，第一个路由为入口
        {
            "path": "页面路径",
            "style": {
                "navigationStyle": "导航栏显隐",
                "navigationBarTextStyle": "状态栏颜色",
                "navigationBarTitleText": "标题内容"
            }
        }
    ],
    "tabBar": { // 底栏配置，路径需在 pages 注册，至少需要俩个
        "selectedColor": "选中标题颜色",
            {
                "pagePath": "底栏路径",
                "text": "底栏标题"
                "iconPath": "图标"
                "selectedIconPath": "选中图标"
            }
    },
    "subPackages": [ // 子包配置
    {
        "root": "子包根目录",
        "pages": [ // 子包页面配置
            {
                "path": "子包页面路径",
                "style": {
                    ...
                }
            }
        ]
    },
    "preloadRule": { // 子包预加载配置
        "触发开始加载页面": {
            network: "预加载网络",
            packages: ["预加载子包根目录"]
        }
    }
  ],
    "globalStyle": { // 默认配置
        "navigationBarTextStyle": "标题颜色",
        "navigationBarTitleText": "标题内容",
        "navigationBarBackgroundColor": "标题背景",
        "backgroundColor": "背景颜色"
    },
    "uniIdRouter": {} // uniid 路由
}
```

## 配置组件库

```
// cmd
pnpm i @dcloudio/uni-ui
```

```
// pages.json
"easycom": {
    "autoscan": true,
    "custom": {
        "^uni-(.\*)": "@dcloudio/uni-ui/lib/uni-$1/uni-$1.vue" // 自动引入组件规则
    }
},
```

## pinia 持久化

```
// stores
persist: {
    storage: {
        getItem(key) {
            return uni.getStorageSync(key)
        },
        setItem(key, value) {
            uni.setStorageSync(key, value)
        },
    },
},
```

## 差异开发

```
// js
// #ifdef MP-WEIXIN || WEB || APP
// #endif

<!-- template -->
<!-- #ifdef 平台 -->
<!-- #endif -->
```

小程序不支持\*选择器
WEB 默认 scoped

## 分包

将资源分为多个包，减少首屏加载时间，预下载分包可提升进入分包页面的速度
配置分包参考上方 pages.json 配置 说明的 subPackages、preloadRule

## 打包项目

```
# cmd
npx @dcloudio/uvm *.*.* # 生成 uvm 依赖配置文件为指定版本，慎用
pnpm build:mp-weixin # 微信小程序
pnpm build:h5 # 浏览器
```

```
// manifest.json
"h5": {
    "router": {
        "base": "./" // 配置打包路径
    }
},
```

微信开发者工具上传 => 微信公众平台审核发布选择版本
APP 端 使用 HBuilderX 打包

## uniCloud

通过 js 开发服务端，提供云数据库等功能
登陆 uniCloud => 认证身份 => 建立服务空间 => 云数据库创建表
HBuilderX 根目录创建 uniCloud => 关联服务空间 => database 下载表结构 DB Schema

## uni 小技能

一、小程序大图查看

```
uni.previewImage({
    urls: [] // 所有大图
    current: url // 当前大图
})
```

二、获取安全区域

```
// js
const { safeAreaInsets } = uni.getSystemInfoSync()
```

三、获取骨架屏

开发工具导航栏=>页面信息=>生成骨架屏
web 和 app 需要引入样式

四、页面传参

onLoad 方法可以接受 url 参数，pages.json 里注册的页面才有 onLoad 方法
pages.json 里注册的页面的 defineProps 方法也可以接受 url 参数

五、获取手机号

```
// js
uni.login()
```

<button
open-type="getPhoneNumber"
@getphonenumber="onGetPhoneNumber" />

六、获取图片

```
// js
uni.chooseMedia()
```

七、动态标题

```
// js
uni.setNavigationBarTitle({
    title: "标题"
})
```

八、滚动容器

```
<!-- html -->
<scroll-view
    scroll-y // 允许纵向滚动
    scroll-x // 允许横向滚动
    refresher-enabled // 开启下拉刷新
    :refresher-triggered="" // 下拉刷新状态
    @scrolltolower="" // 滚动到底部时
    @refresherrefresh="" // 下拉刷新时 />
```

九、侧滑菜单

```
<!-- html -->
<uni-swipe-action />
<uni-swipe-action-item />
<template #right /> // 侧滑菜单内容
```

十、获取页面栈

```
// js
getCurrentPages()
```

十一、微信小程序滚动动画

```
// js
this.animate(
    'css选择器',
    [{}, // 初始css样式
     {}], // 结束css样式
    动画时长,
    {
      scrollSource: '滚动容器css选择器',
      timeRange: 时长倍率,
      startScrollOffset: 开始滚动位置,
      endScrollOffset: 结束滚动位置,
    }
  )
```

十二、倒计时组件

```
<!-- html -->
<uni-countdown
    :second="秒数"
    :show-day="显示天"
    :show-colon="显示冒号"
    @timeup="完成时"
/>
```

十三、复制

```
// js
uni.setClipboardData({ data: "内容" })
```
