# web<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>
  <script>


    //console.log(/[a-zA-Z]+/.test("hello"));




//    console.log(/./.test("除了回车换行以为的任意字符"));//true
//    console.log(/.*/.test("0个到多个"));//true
//    console.log(/.+/.test("1个到多个"));//true
//    console.log(/.?/.test("哈哈"));//true
//    console.log(/[0-9]/.test("9527"));//true
//    console.log(/[a-z]/.test("what"));//true
//    console.log(/[A-Z]/.test("Are"));//true
//    console.log(/[a-zA-Z]/.test("干啥子"));//false
//    console.log(/[0-9a-zA-Z]/.test("9ebg"));//true
//    console.log(/b|(ara)/.test("abra"));//true
//    console.log(/[a-z]{2,3}/.test("arfsf"));//




    console.log(/\d/.test("998"));

    console.log(/\d*/.test("998"));

    console.log(/\d+/.test("998"));

    console.log(/\d{0,}/.test("998"));

    console.log(/\d{2,3}/.test("998"));

    console.log(/\D/.test("eat"));

    console.log(/\s/.test("  "));
    console.log(/\S/.test("嘎嘎 "));
    console.log(/\w/.test("_"));
    console.log(/\W/.test("_"));

  </script>
</head>
<body>


</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<style type="text/css">
  #dv{
    width: 300px;
    height:200px;
    position: absolute;
    left:300px;
    top:100px;
  }
  .strengthLv0 {
    height: 6px;
    width: 120px;
    border: 1px solid #ccc;
    padding: 2px;
  }

  .strengthLv1 {
    background: red;
    height: 6px;
    width: 40px;
    border: 1px solid #ccc;
    padding: 2px;
  }

  .strengthLv2 {
    background: orange;
    height: 6px;
    width: 80px;
    border: 1px solid #ccc;
    padding: 2px;
  }

  .strengthLv3 {
    background: green;
    height: 6px;
    width: 120px;
    border: 1px solid #ccc;
    padding: 2px;
  }
</style>
<body>
<div id="dv">
  <label for="pwd">密码</label>
  <input type="text" id="pwd" maxlength="16"><!--课外话题-->
  <div>
    <em>密码强度：</em>
    <em id="strength"></em>
    <div id="strengthLevel" class="strengthLv0"></div>
  </div>
</div>
<script src="common.js"></script>
<script>

  //获取文本框注册键盘抬起事件
  my$("pwd").onkeyup=function () {
    //每次键盘抬起都要获取文本框中的内容,验证文本框中有什么东西,得到一个级别,然后下面的div显示对应的颜色
    //如果密码的长度是小于6的,没有必要判断
//    if(this.value.length>=6){
//     var lvl= getLvl(this.value);
//      my$("strengthLevel").className="strengthLv"+lvl;
//    }else{
//      my$("strengthLevel").className="strengthLv0";
//    }
    my$("strengthLevel").className="strengthLv"+(this.value.length>=6?getLvl(this.value) :0);
  };

  //给我密码,我返回对应的级别
  function getLvl(pwd) {
    var lvl=0;//默认是0级
    //密码中是否有数字,或者是字母,或者是特殊符号
    if(/[0-9]/.test(pwd)){
      lvl++;
    }
    //判断密码中有没有字母
    if(/[a-zA-Z]/.test(pwd)){
      lvl++;
    }
    //判断密码中有没有特殊符号
    if(/[^0-9a-zA-Z_]/.test(pwd)){
      lvl++;
    }
    return lvl;//最小的值是1,最大值是3
  }




</script>
<script>

  /*
  *
  * 密码: 数字,字母,特殊符号
  *
  * 密码: 只有数字- 或者是只有字母,或者是只有特殊符号---1级---弱
  * 两两组合: 数字和字母, 数字和特殊符号, 字母和特殊符号   -----2级----中
  * 三者都有: 数字和字母和特殊符号------3级-----强
  *
  * */

//  //获取文本框注册键盘抬起事件
//  my$("pwd").onkeyup=function () {
//    //每次键盘抬起都要获取文本框中的内容,验证文本框中有什么东西,得到一个级别,然后下面的div显示对应的颜色
//    //如果密码的长度是小于6的,没有必要判断
//    if(this.value.length>=6){
//      var lvl=getLvl(this.value);
//      if(lvl==1){
//        //弱
//        my$("strengthLevel").className="strengthLv1";
//      }else if(lvl==2){
//        my$("strengthLevel").className="strengthLv2";
//      }else if(lvl==3){
//        my$("strengthLevel").className="strengthLv3";
//      }else{
//        my$("strengthLevel").className="strengthLv0";
//      }
//    }else{
//      my$("strengthLevel").className="strengthLv0";
//    }
//
//
//  };
//
//  //给我密码,我返回对应的级别
//  function getLvl(pwd) {
//    var lvl=0;//默认是0级
//    //密码中是否有数字,或者是字母,或者是特殊符号
//    if(/[0-9]/.test(pwd)){
//      lvl++;
//    }
//    //判断密码中有没有字母
//    if(/[a-zA-Z]/.test(pwd)){
//      lvl++;
//    }
//    //判断密码中有没有特殊符号
//    if(/[^0-9a-zA-Z_]/.test(pwd)){
//      lvl++;
//    }
//    return lvl;//1  3
//  }
//



</script>





</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>

</head>
<body>
请您输入邮箱地址:<input type="text" value="" id="email"/> *<br/>
<script>
  //如果输入的是邮箱,那么背景颜色为绿色,否则为红色

  //获取文本框,注册失去焦点的事件
  document.getElementById("email").onblur = function () {
    //判断这个文本框中输入的是不是邮箱
    var reg = /^[0-9a-zA-Z_.-]+[@][0-9a-zA-Z_.-]+([.][a-zA-Z]+){1,2}$/;
    if (reg.test(this.value)) {
      this.style.backgroundColor = "green";
    } else {
      this.style.backgroundColor = "red";
    }
  };
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>

</head>
<body>
请输入您的名字:<input type="text" value="" id="userName" />*<br/>
<script>
  //是中文名字,则绿色,否则红色
  document.getElementById("userName").onblur=function () {
    var reg=/^[\u4e00-\u9fa5]{2,6}$/;
    if(reg.test(this.value)){
      this.style.backgroundColor="green";
    }else{
      this.style.backgroundColor="pink";
    }
  };


  //[\u4e00-\u9fa5]    [一-龥]
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style type="text/css">
    body {
      background: #ccc;
    }

    label {
      width: 40px;
      display: inline-block;
    }

    span {
      color: red;
    }

    .container {
      margin: 100px auto;
      width: 400px;
      padding: 50px;
      line-height: 40px;
      border: 1px solid #999;
      background: #efefef;
    }

    span {
      margin-left: 30px;
      font-size: 12px;
    }

    .wrong {
      color: red
    }

    .right {
      color: green;
    }

    .defau {
      width: 200px;
      height: 20px;
    }

    .de1 {
      background-position: 0 -20px;
    }
  </style>

</head>

<body>
<div class="container" id="dv">
  <label for="qq">Q Q</label><input type="text" id="qq"><span></span><br/>
  <label>手机</label><input type="text" id="phone"><span></span><br/>
  <label>邮箱</label><input type="text" id="e-mail"><span></span><br/>
  <label>座机</label><input type="text" id="telephone"><span></span><br/>
  <label>姓名</label><input type="text" id="fullName"><span></span><br/>
</div>
<script src="common.js"></script>
<script>

  //qq的
  checkInput(my$("qq"),/^\d{5,11}$/);
  //手机
  checkInput(my$("phone"),/^\d{11}$/);
  //邮箱
  checkInput(my$("e-mail"),/^[0-9a-zA-Z_.-]+[@][0-9a-zA-Z_.-]+([.][a-zA-Z]+){1,2}$/);
  //座机号码
  checkInput(my$("telephone"),/^\d{3,4}[-]\d{7,8}$/);
  //中文名字
  checkInput(my$("fullName"),/^[\u4e00-\u9fa5]{2,6}$/);
  //给我文本框,给我这个文本框相应的正则表达式,我把结果显示出来
  //通过正则表达式验证当前的文本框是否匹配并显示结果
  function checkInput(input,reg) {
    //文本框注册失去焦点的事件
    input.onblur=function () {
      if(reg.test(this.value)){
        this.nextElementSibling.innerText="正确了";
        this.nextElementSibling.style.color="green";
      }else{
        this.nextElementSibling.innerText="让你得瑟,错了吧";
        this.nextElementSibling.style.color="red";
      }
    };
  }

</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>
  <script>
    //正则表达式中:g 表示的是全局模式匹配
    //正则表达式中:i 表示的是忽略大小写

    
       var str="中国移动:10086,中国联通:10010,中国电信:10000";
       //把里面所有的数字全部显示出来
       var array=str.match(/\d{5}/g);
       console.log(array);


    //
    //    var str = "123123@xx.com,fangfang@valuedopinions.cn 286669312@qq.com 2、emailenglish@emailenglish.englishtown.com 286669312@qq.com...";
    //    var array = str.match(/\w+@\w+\.\w+(\.\w+)?/g);
    //    console.log(array);


    //提取这里的日
    //    var str="2017-11-12";
    //    var array=str.match(/(\d{4})[-](\d{2})[-](\d{2})/g);
    //    //console.log(array);
    //    //正则表达式对象.$3
    //    console.log(RegExp.$3);


    //    var email="shuaiyangtaishuaile@itcast.com.cn";
    //    email.match(/([0-9a-zA-Z_.-]+)[@]([0-9a-zA-Z_-]+)(([.][a-zA-Z]+){1,2})/);
    //    console.log(RegExp.$1);//用户名
    //    console.log(RegExp.$2);//126
    //    console.log(RegExp.$3);//域名


    //    var str="小苏好帅哦,真的是太帅了,帅,就是真帅";
    //    str=str.replace(/帅/g,"猥琐");
    //    console.log(str);

    //    var str="  哦买噶的    ,太幸福了  ";
    //    str=str.trim();
    //    console.log("==="+str+"===");


    //    var str = "  哦买噶的    ,太幸福了  ";
    //    str = str.replace(/\s+/g, "");
    //    console.log("===" + str + "===");


    //所有的h都替换成S
    //    var str="HhpphH";//SSppSS
    //    str=str.replace(/[h]/gi,"S");
    //    console.log(str);


    //    var reg = new RegExp(/[h]/gi);
    //    var str = "HhpphH";//SSppSS
    //    str = str.replace(reg, "S");
    //    console.log(str);

//
//    var str = "中国移动:10086,中国联通:10010,中国电信:10000";
//    //把里面所有的数字全部显示出来
//    //var array = str.match(/\d{5}/g);
//    //正则表达式对象.exec方法传入字符串
//    var reg=/\d{5}/g;
//    //var array=reg.exec(str);
////    console.log(array);
////    console.log(reg.exec(str));
////    console.log(reg.exec(str));
////    console.log(reg.exec(str));
//
//    var result=reg.exec(str);
//    while(result!=null){
//      console.log(result);
//      result=reg.exec(str);
//    }



//    var str = "中国移动:10086,中国联通:10010,中国电信:10000";
//    var reg=/\d{5}/g;
//    //通过正则表达式匹配这个字符串
//    var array=reg.exec(str);
//    console.log(array);
//    console.log(reg.exec(str));
//    console.log(reg.exec(str));
//    console.log(reg.exec(str));//null
//


    var str = "中国移动:10086,中国联通:10010,中国电信:10000";
    var reg=/\d{5}/g;
    //通过正则表达式匹配这个字符串
    var array=reg.exec(str);
    while (array!=null){
      //输出匹配的内容
      console.log(array[0]);
      array=reg.exec(str);
    }










  </script>
</head>
<body>


</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>
  <script>
    //深拷贝:拷贝还是复制,深:把一个对象中所有的属性或者方法,一个一个的找到.并且在另一个对象中开辟相应的空间,一个一个的存储到另一个对象中

    var obj1={
      age:10,
      sex:"男",
      car:["奔驰","宝马","特斯拉","奥拓"],
      dog:{
        name:"大黄",
        age:5,
        color:"黑白色"
      }
    };

    var obj2={};//空对象
    //通过函数实现,把对象a中的所有的数据深拷贝到对象b中
    function extend(a,b) {
      for(var key in a){
        //先获取a对象中每个属性的值
        var item=a[key];
        //判断这个属性的值是不是数组
        if(item instanceof Array){
          //如果是数组,那么在b对象中添加一个新的属性,并且这个属性值也是数组
          b[key]=[];
          //调用这个方法，把a对象中这个数组的属性值一个一个的复制到b对象的这个数组属性中
          extend(item,b[key]);
        }else if(item instanceof Object){//判断这个值是不是对象类型的
     //如果是对象类型的,那么在b对象中添加一个属性,是一个空对象
          b[key]={};
          //再次调用这个函数,把a对象中的属性对象的值一个一个的复制到b对象的这个属性对象中
          extend(item,b[key]);
        }else{
          //如果值是普通的数据,直接复制到b对象的这个属性中
          b[key]=item;
        }
      }
    }

    extend(obj1,obj2);
    console.dir(obj1);
    console.dir(obj2);



  </script>
</head>
<body>


</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>遍历DOM树</title>
</head>

<body>
<h1>遍历 DOM 树</h1>
<p style="color: green;">Tip: 可以在遍历的回调函数中任意定制需求</p>
<div>
  <ul>
    <li>123</li>
    <li>456</li>
    <li>789</li>
  </ul>
  <div>
    <div>
      <span>haha</span>
    </div>
  </div>
</div>
<div id="demo_node">
  <ul>
    <li>123</li>
  </ul>
  <p>hello</p>
  <h2>world</h2>
  <div>
    <p>dsa</p>
    <h3>
      <span>dsads</span>
    </h3>
  </div>
</div>
<script>

  //获取页面中的根节点--根标签
  var root=document.documentElement;//html
  //函数遍历DOM树
  //根据根节点,调用fn的函数,显示的是根节点的名字
  function forDOM(root1) {
    //调用f1,显示的是节点的名字
   // f1(root1);
    //获取根节点中所有的子节点
    var children=root1.children;
    //调用遍历所有子节点的函数
    forChildren(children);
  }
  //给我所有的子节点,我把这个子节点中的所有的子节点显示出来
  function forChildren(children) {
    //遍历所有的子节点
    for(var i=0;i<children.length;i++){
      //每个子节点
      var child=children[i];
      //显示每个子节点的名字
      f1(child);
      //判断child下面有没有子节点,如果还有子节点,那么就继续的遍历
      child.children&&forDOM(child);
    }
  }
  //函数调用,传入根节点
  forDOM(root);
  function f1(node) {
    console.log("节点的名字:"+node.nodeName);
  }

  //节点:nodeName,nodeType,nodeValue




//  第一个函数:给我根节点,我会找到所有的子节点:forDOM(根节点)
//  获取这个根节点的子节点
//  var children=根节点的.children
//  调用第二个函数
//
//  第二个函数:给我所有的子节点,我把每个子节点的名字显示出来(children)
//  for(var i=0;i<children.length;i++){
//    每个子节点
//    var child=children[i];
//    f1(child);给我节点,我显示该节点的名字
//    child是子节点,但是如果child里面还有子节点,此时child就是爹了
//    child.children&&第一个函数(child)
//
//  }








</script>
</body>

</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>
  <script>

    /*
    *
    * 正则表达式:也叫规则表达式,按照一定的规则组成的一个表达式,这个表达式的作用主要是匹配字符串的,
    * "我的电话:10086,他的电话:10010,你的电话:10000" 正则表达式,把这个字符串中的所有的数字找到
    *
    * 正则表达式的作用:匹配字符串的
    *
    * 在大多数编程语言中都可以使用
    *
    * 正则表达式的组成:是由元字符或者是限定符组成的一个式子
    *
    *
    * 元字符:
    *
    * .  表示的是:除了\n以外的任意的一个字符   "fdsfs238"
    *
    * [] 表示的是:范围,  [0-9] 表示的是0到9之间的任意的一个数字,  "789" [0-9]
    * [1-7] 表示的是1到7之间的任意的一个数字
    * [a-z] 表示的是:所有的小写的字母中的任意的一个
    * [A-Z] 表示的是:所有的大写的字母中的任意的一个
    * [a-zA-Z] 表示的是:所有的字母的任意的一个
    * [0-9a-zA-Z] 表示的是: 所有的数字或者是字母中的一个
    * [] 另一个函数: 把正则表达式中元字符的意义干掉    [.] 就是一个.
    * | 或者     [0-9]|[a-z] 表示的是要么是一个数字,要么是一个小写的字母
    * () 分组 提升优先级   [0-9]|([a-z])|[A-Z]
    * ([0-9])([1-5])([a-z]) 三组, 从最左边开始计算
    * (()(()))
    *
    *
    * 都是元字符,但是也可以叫限定符,下面的这些
    *    *   表示的是:前面的表达式出现了0次到多次
    *    [a-z][0-9]* 小写字母中的任意一个 后面是要么是没有数字的,要么是多个数字的
    *    "fdsfs3223323"  [a-z][0-9]*
    *
    *    +  表示的是:前面的表达式出现了1次到多次
    *    [a-z][9]+  小写字母一个后面最少一个9,或者多个9
    *    "fesfewww9fefds"
    *
    *    ?  表示的是:前面的表达式出现了0次到1次,最少是0次,最多1次 ,另一个含义:阻止贪婪模式
    *    [4][a-z]? "1231234ij"
    *  限定符:限定前面的表达式出现的次数
    *  {} 更加的明确前面的表达式出现的次数
    *  {0,} 表示的是前面的表达式出现了0次到多次,和 *一样的
    *  {1,} 表示的是前面的表达式出现了1次到多次,和 +一样的
    *  {0,1} 表示的是前面的表达式出现了0次到1次,和 ?一样的
    *  {5,10} 表示的是前面的表达式出现了5次到10次
    *  {4} 前面的表达式出现了4次
    *  {,10} 错误的========不能这么写
    *  ^ 表示的是以什么开始,或者是取非(取反) ^[0-9] 以数字开头
    *  ^[a-z] 以小写字母开始
    *  [^0-9] 取反,非数字
    *  [^a-z] 非小写字母
    *  [^0-9a-zA-Z_]
    *  $ 表示的是以什么结束   [0-9][a-z]$  必须以小写字母结束
    *  ^[0-9][a-z] 相当于是严格模式   "3f2432e"  "4f"
    *   \d 数字中的任意一个,
    *   \D 非数字中的一个
    *   \s 空白符中的一个
    *   \S 非空白符
    *   \w 非特殊符号
    *   \W 特殊符号
    *   \b 单词的边界
    *   "what are you no sha lei"
    *
    *
    *
    *
    *
    *
    *    . 除了\n以外的任意一个单个字符
    *    []  范围
    *    () 分组,提升优先级
    *    | 或者
    *    * 0-多次
    *    + 1-多次
    *    ? 0-1次
    *    {0,} 和*一样
    *    {1,} 和+
    *    {0,1} 和?
    *
    *    \d 数字中的一个
    *    \D 非数字
    *    \s 空白符
    *    \S 非空白符
    *     \W  特殊符号
    *     \w 非特殊符号 _
    *     ^ 取反,以什么开始
    *     $ 以什么结束
         *
         *     \b 单词边界
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    * */
  </script>
</head>
<body>



</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>
  <script>


    /*
    *
    *
    * 写正则表达式,根据字符串来写正则表达式进行匹配
    *
    * 经验: 1.找规律 2.不要追求完美
    *
    *
    * 身份证的正则表达式
    *
    * 15位或者18位
    * ([1-9][0-9]{14})|([1-9][0-9]{16}[0-9xX])
    *
    *
    * ([1-9][0-9]{14})([0-9]{2}[0-9xX])?
    *
    *
    * 练习:
    * 1.座机号码的正则表达式
    * 010-19876754
    * 0431-87123490
    *
    * [0-9]{3,4}[-][0-9]{8}
    * \d{3,4}[-]\d{8}
    *
    * \d{3,4}[-][0-9]{8}
    *
    *
    * 2.qq号码的正则表达式
    *
    * [1-9][0-9]{4,10}
    * \d{5,11}
    *
    * 3.手机号码的正则表达式
    *
    * 130 131 132 133 134 135 136 137 138 139
    * 143 147
    * 150 151 152 153 154 155 156 157 158 159
    * 170 171 173 176 177
    * 180 181 182 183 184 185 186 187 188 189
    * ([1][358][0-9][0-9]{8})|([1][4][37][0-9]{8})|([1][7][01367][0-9]{8})
    * \d{11}
    *
    *
    * 邮箱的正则表达式,必须要记住的
    *
    * sd2113_3.-fd@itcast.com.cn
    *
    *
    *
    * [0-9a-zA-Z_.-]+[@][0-9a-zA-Z_.-]+([.][a-zA-Z]+){1,2}
    *
    *
    *
    *
    *
    *
    *
    *
    *
    *
    * */
  </script>
</head>
<body>


</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>title</title>
  <script>

   //创建正则表达式对象

    //两种:
    /*
    *
    * 1.通过构造函数创建对象
    *
    *
    * 2.字面量的方式创建对象
    *
    *
    * 正则表达式的作用:匹配字符串的
    *
    * */
//   //对象创建完毕---
//    var reg=new RegExp(/\d{5}/);
//   //字符串
//    var str="我的电话是10086";
//   //调用方法验证字符串是否匹配
//    var flag=reg.test(str);
//    console.log(flag);



//   //对象创建完毕---
//   var reg=new RegExp(/\d{5}/);
//   //调用方法验证字符串是否匹配
//   var flag=reg.test("我的电话是10086");
//   console.log(flag);


    //字面量的方式创建正则表达式对象
    var reg=/\d{1,5}/;
    var flag=reg.test("小苏的幸运数字:888");
    console.log(flag);



  </script>
</head>
<body>


</body>
</html>
