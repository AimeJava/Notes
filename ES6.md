# ES6 #

定义变量
**let/const/var**

	var //函数级作用域，在ES6中尽量不要用 
	const //是块级作用域，定义的变量不能够重新赋值
	let	//是块级作用域，

	for (var i = 0; i < 10; i++){
		setTimeout(function() {
			console.log(i);
		},0)
	}
	console.log("aaa");

结果是先打印aaa 后打印10个10 ；

    for (let i = 0; i < 10; i++){
   		function (){
   			setTimeout(function() {
   				console.log(i);
   		 	},0)
    	}
    }
    console.log("aaa");
打印0-9

定义字符串

	const aaa = 'hello world'
	const bbb = "hello world"
	const ccc = `hello world`

箭头函数
**没有自己的this指针**
