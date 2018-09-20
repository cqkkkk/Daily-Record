## 2018.09.03
#### 1.canvas画布功能的rotate旋转，实际上是旋转整个画布的坐标系，而不是旋转画布中的某一个物体，因此只要出现在rotate设置值之后的均会受到rotate的影响，在其之前的就不会受到影响。且rotate设置之间会进行叠加，也就是第二次设置rotate值不会先清空第一次设置的rotate值，而是会在第一次设置的值的基础上继续旋转相应的角度。所以，在使用canvas时，若需要多次设置rotate值，需要小心使用，以防出错。
#### 2.canvas画布可以通过toDataURL使得画出来的图像转为一张png图像，且通过获取该图像的url，就可以在img标签中将这个值赋给src属性来使用。
#### 3.Vue实例中模板的img标签有一个不同点，src属性前面要加上冒号，不然会出错。
#### 4.若想要页面中的文字在长按之后不会选择，应该在css属性当中添加user-select：none，并且因为要满足不同浏览器的要求，所以要加上不同的前缀来适配不同的浏览器。

## 2018.09.06
#### 1.meeting组件bug，down之后若不再按钮上up，则不会触发到up事件，按钮的状态还是按下的状态。给整一个contentView添加一个mouseup事件，触发之后将按钮的状态调整为正常的。另外，还需要添加按钮的value值，用来判断只有当在指定按钮上down，这个按钮的up事件才能触发。
#### 2.学习swnb的github上面相关的canvas动画写法，并将相关的项目添加到了canvas-learning的文档中，发现其多采用面向对象编程的写法来写整个组件。需要好好学习关于js面向对象编程，看书看到相关的章节，开始慢慢理解构造函数，原型等，还需要加强练习来帮助巩固。
#### 3.接触到一个常见的dom方法queryselecter，于是查阅相关资料对常见的HTML DOM元素以及对应的属性和方法过了一遍，包括一些见过但没用过的，比如：addEventListener，removeEventListener，innerHTML等等，详见活页笔记本。
#### 4.了解javascript 中的 cookie ，其主要用于存储web页面中的用户信息，主要作用就是记录客户端的用户信息。

## 2018.09.07
#### 1.canvas虚线画法，设置虚线的实线长度和空白长度，以及最开始偏移长度。之后画出来的就是虚线。

```shell
ctx.setLineDash([20, 20]);  // [实线长度, 间隙长度]
ctx.lineDashOffset = -0;
```

#### 2.创建了translate.vue和crossroad.vue组件，均是采用简单的requestAnimationFrame动画请求来画的。之后要尝试接触一些复杂一点的动画，并加以练习。
#### 3.对JavaScript的面向对象编程进一步学习，对构造函数，原型和实例三者之间有了一定的了解，还需多加练习，才能真正掌握。重点理解：使用构造函数可以用于创建一个新的实例，构造函数中的prototype属性指向原型对象，原型对象中有一个constructor属性指向构造函数，并且新建的实例也是指向原型对象的。在构造函数中定义的属性和方法会在每一个实例中新建一个，而在原型中的属性与方法则为全部实例共享，节省内存空间。
#### 4.还需补充知识点：git分支管理，ajax异步请求，es6等。

## 2018.09.10
#### 1.在Vue-learning项目中引入vue-awesome库（SVG图标组件库），并且利用相关图标制作简单的一个评分系统。使用该库，直接对icon的name属性命名相应的图标名字即可使用。
#### 2.学习了SVG可伸缩矢量图形的一些基础画法，可以在html中画出一些简单的图形。当然，个人人为最好的做法还是直接使用现有的图标库中的图标，或者时能够直接使用一些在线的svg编辑器，画好之后直接保存引用。
#### 3.最重要的是今天的commit过程中对数据控制组件状态这一个抽象的概念有了一定的了解，这样编写出来的代码更加简洁，且更加有意义。同时也对组件的可复用性以及组件传递的prop参数，prop参数认证有了更深一步的了解和运用。详见[svgtest.vue](https://github.com/cqkkkk/Vue-learning/blob/master/vue-learning/src/components/SvgTest.vue)

## 2018.09.12
#### 1.学习了解github上多人开发同一个项目的过程，首先fork的话就是指当看到别人的开源项目觉得很好，就复制成为自己的项目，并且做的修改可以提交给原项目的主人，好比说自己复制项目之后做的一些优化，实现的一些其他功能等等。但是缺点就是这并不是多人开发的选择，提交之后还要交给原项目主人进行审核，且原项目若进行更新，只能再从新fork一遍而不能直接通过git pull来实时进行更新，开发起来比较麻烦。实际上这也不是github设置给多人开发用的。
#### 2.多人使用github进行开发时，在项目的setting里面可以设置参与到项目的协作者，输入用户名之后把invitation发给相应的人，点击链接就可以加到项目中。这样的开发，两人都可以commit，且都可以通过pull拉取项目更新数据，实际上一个项目，而fork则是复制，变成了两个项目。
#### 3.创建classweb项目，主要采用的前端框架是react，且配合之前在兰吉尔用过的前端ui工具antd共同开发这个项目。开发这个项目一方面能够加深对react框架的学习，一方面能学会数据库的一些运用，学会用网页与数据库进行交互，另外也可以把班级（暨南大学珠海校区2015级物联网工程）这个页面做出来，留作大学的一个珍贵的回忆。

## 2018.09.13
#### 1.加入生物实验的项目中，查看学习项目的一些声明文件，对一个项目怎么搭建起来有一定的了解，一个项目一般会对代码格式进行统一，一般采用eslint。通过安装eslint插件并在指定位置上写一个。eslinttrc.js的规则文件来使用。
#### 2.一个项目中还需要对状态管理方案或组件通讯机制采用统一的方案，swnb为本项目写了两个工具，center和datastore。center主要用于解决对象的通讯问题，而datastore则用来解决数据管理问题。（还没真正搞明白，待进一步学习理解）
#### 3.move.js该文件中export了一个类moveable，专门用于拖动，这样之后若有组件需要有实现拖动的功能就可以import这个方法来实现，而无需在每一个组件中都写一个move的方法。要学习这种复用的思路。
#### 4.fakerequest.js 该方法用于暂时的数据请求，文件中存着相关的数据以及获取各数据的方法，通过调用这些方法就可以获取到相对应的数据。
#### 5.要学会灵活运用vue提供的一些api，尤其是v-for。下面例子中srcList是一个函数并且最终会返回一个数组给v-for来循环使用。imgScr同样也是一个函数，拿到src之后才能调用该函数，并返回一个真正的图片路径。

```shell
<div>
	<img v-for="(src,index) in srcList('base')"
	     @click="choosePage(src)" :src="imgSrc(src)" :key="index"/>
</div>
```
#### 6.computed是vue中的计算属性，只用在调用相关数据时，才会运行相关的代码。而生命周期函数created则不一样，created是在页面加载之前就会执行相对应的代码。要区分两者，合理运用。
#### 7.学习使用vue-router，vue.js官方的路由管理器，它和 Vue.js 的核心深度集成，让构建单页面应用变得易如反掌。这里不做详细介绍，待之后有时间将这个路由管理器运用到[vue-learning](https://github.com/cqkkkk/Vue-learning)项目中去。(待更新)

## 2018.09.15(山竹即将登陆广东)
#### 1.状态管理，如果需要做一个组件或者是一个网页会按照一定的步骤进行操作的话，做法可以参考以下demo：
```shell
	 // html部分
	 <header>
            <p>{{state.title}}</p>
         </header>
	 
	 // JavaScript部分
	 // 创建一个stateList数组，数组中每个元素是一个对象，保存着每一个步骤
	 const stateList = [
	    {
		title: '打开冰箱'
	    },
	    {
		title: '把大象塞进冰箱'
	    },
	    {
		title: '关上冰箱'
	    }   
	];
	
	let stateCount = 0; //索引
	let state = stateList[stateCount], //当前步骤
	
	// 每当完成一个步骤时要调用nextstate函数，转换为下一个状态
	function nextstate(){
		state = stateList[++stateCount];
	}
```
#### 2.ref属性 ref是用来给元素和子组件注册引用信息。引用信息将注册在父组件的$refs对象上。如果在普通的DOM元素上使用，引用指向的就是DOM元素。举例：
```shell
	<input type="text" ref="input1"/>
    	<button @click="add">添加</button>
	
	add:function(){
        	this.$refs.input1.value ="22"; //this.$refs.input1  减少获取dom节点的消耗
        }
```
#### 当 ref 和 v-for 一起使用的时候，你得到的引用将会是一个包含了对应数据源的这些子组件的数组。
#### 3.之前尝试实现的动画都是但步骤的，也就是一直沿着一个方向前进，或沿着一个方向平移等等。那么，当我们需要实现较复杂的动画时，例如在一个步骤中，一个物体先右移，下移，再左移，上移回到原点这样来画一个矩形的形态。如果仍然采用之前的requestAnimationFrame动画请求来做的话，会相当的复杂。查阅资料之后发现另一个有趣的实现方法，即采用css3中的animation来做。使用animation属性制作动画可以更加灵活的设置动画帧，keyframe中的百分数是动画完成总时间的比例。
```shell
	.tset{
		animation: name duration timing-function delay iteration-count direction fill-mode;
	}
```
##### name:keyframe的名称，也就是定义了关键帧的动画的名称,这个名称用来区别不同的动画。
##### duration:完成动画所需要的时间（2s 或者 2000ms）
##### timing-function:完成动画的速度曲线 linear:匀速 ease:从慢到快再到慢 ease-in：慢慢加快 ease-out：慢慢变慢 ease-in-out：先变快再变慢
##### delay：动画开始之前的延迟
##### iteration-count：动画播放次数
##### direction：是否轮流反向播放动画（normal:正常顺序播放，alternate下一次反向播放）如果把动画设置为只播放一次，则该属性没有效果。
#### 上面这些参数并不是在每次使用动画时都要全部写上，可以写上部分需要的参数即可。例如接下来的demo：
```shell
	//javascript
	//在需要动画实现的时候才将这个css样式加到指定的dom元素上
	document.queryselector('div').classList.add('clean');
	
	// css
	.clean{
		animation: clean_coverslip 2s linear;
	}
	@keyframes clean_coverslip
	{
	    	1% {left:810px;}
	    	30% {left:500px;}
	    	50% {left:600px;}
	    	70% {left:500px;}
	    	100%{left:810px;}
	}
```
#### 4.entries ES6中同时为数组和对象object提供了entries（）方法，二者虽然同名，但是应用于不同的地方，其达到的效果是不一样的，内部逻辑是不一样的。要注意区分！！！！！
##### 数组中使用
```shell
	for (let [index, elem] of ['a', 'b'].entries()) {
	  console.log(index, elem);
	}
	// 0 "a"
	// 1 "b"
	
	//如果不使用for...of循环，可以手动调用遍历器对象的next方法，进行遍历。
	let letter = ['a', 'b', 'c'];
	let entries = letter.entries();
	console.log(entries.next().value); // [0, 'a']
	console.log(entries.next().value); // [1, 'b']
	console.log(entries.next().value); // [2, 'c']
```
##### 对象中的使用（Object.entries方法返回一个数组，成员是参数对象自身的（不含继承的）所有可遍历（enumerable）属性的键值对数组。）
```shell
	const obj = { foo: 'bar', baz: 42 };
	Object.entries(obj)
	// [ ["foo", "bar"], ["baz", 42] ]
```

## 2018.09.17（山竹已溜）
#### 1.在项目中完成一个效果就是要先改变一张图片的背景，然后隔一个时间段之后再变回来。很自然就想到使用setTimeOut这个函数，在过去一定的时间段之后执行相应的函数，但是如果直接按照正常的函数书写格式来写一个函数，那么会拿不到vue模板中的data值，而将正常函数书写形式改为箭头函数就可以解决这个问题。
```shell
	setTimeout(function(){
		var test = this.value; //拿不到数据 
	},1000)
	
	function test(){
		var test = this.value;
	}
	setTimeout(test,1000); //还是拿不到相应数据
	
	setTimeout(() => {
		var test = this.value; //可以拿到数据
	})
```
#### 2.箭头函数与普通函数之间的区别（待进一步学习）
#### 3.linkTimeout  当有多个步骤的情况之下，可以采用多个setTimeout来写，也可以写一个类linkTimeout将这些全部步骤串联起来。（详见onion中的用法以及utils文件夹下的定义类文件）

## 2018.09.20
#### 1.使用vue模板来开发前端项目的一个好处就是它是组件化开发，这点跟react框架是一样的。你可以随时将你写好的组件export，然后在另一个组件中进行import并应用，开发起来相当方便。举例如下：
```shell
	//开发了一个名为onion的组件，同时还开发了另一个afteronion组件，想要将这两个组件给整合到一个组件中，二者是先后顺序
	//给onion组件命名并且将其export
	export default {
		name: 'onion',
		data(){
			...
		}
	}
	
	//创建一个整合的组件假设名字为test,使用v-if来控制两个组件哪个组件显示
	<template>
		<onion v-if="stage === 0" @jump="onJump"></onion>
		<afteronion v-else></afteronion>
	</template>
	
	<script>
		import onion from '...';
		import afteronion from '...';

		export default {
			data() {},
			components: {
				onion,
				afteronion
			},
			methods: {
				onJump() {
					   this.stage = 1;
				}
			}
		}
	</script>
	
	//同时在onion组件中还有一个button用来监听一个点击事件，并且执行相应的函数
	<button v-on:click = "jump"></button>
	jump() {
		this.$emit('jump');
	}

```
#### 2.父组件可以使用 props 把数据传给子组件。子组件可以使用 $emit 触发父组件的自定义事件。关于这两个的用法可以参考[这里](https://blog.csdn.net/sllailcp/article/details/78595077)


