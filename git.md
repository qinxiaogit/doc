1. git push origin <tagname> 推送一个本地标签
2. git push origin --tags 可以推送全部未推送过的本地标签
3. git tag -d <tagname> 删除一个本地标签
4. git push origin :refs/tags/<tagname> 可以删除一个远程标签
5. 常用git忽略文件https://github.com/github/gitignore

axios:vue2.0 ajax
vue:
v-bind缩写：
	<!--完整语法-->
	<a v-bind:href=""></a>
	<!--缩写语法-->
	<a :href=""></a>
	<!--完整语法-->
v-on 缩写
	<a v-on:click=""></a>
	<!--缩写语法-->
	<a @click=""></a>
计算属性
	demo:
	<div id="example">
		<div>Original message:"{{message}}"</div>
		<p>Computed reversed message:{{reverSedMessage}}</p>
	</div>
	var vm = new Vue({
		el:{
			message:'hello',
		},
		computed:{
			reverSedMessage:function(){
			return this.message.split('').reverse().jion();
		}
		watch:{//监听数据变化
			message:function(newMessage){

		},
		methods:function(){
			//方法
		}
	}
	}
	);
	数组更新检测：
	#变异方法：vue包含一组观察数组的变异方法，它们会触发视图更新
		push(),pop(),shift(),unshift(),splice(),sort(),reverse();
	#重塑数组：
		
	内联处理器方法:
		有时候需要在内联语句处理器中访问原生DOM事件。可以用特殊变量$event把他传入方法
		<button v-on:click="warn('Form cannot be submitted yet.', $event)">Submit</button>
		//
		methods:function(message,event){

		}
	事件修饰符：
		v-on提供了事件修饰符，通过由点(.)表示的指令后缀来调用修饰符
		.stop
		.prevent
		.capture
		.self
		.once
		<!-- 阻止单击事件冒泡 -->
		<a v-on:click.stop="doThis"></a>
		<!-- 提交事件不再重载页面 -->
		<form v-on:submit.prevent="onSubmit"></form>
		<!-- 修饰符可以串联  -->
		<a v-on:click.stop.prevent="doThat"></a>
		<!-- 只有修饰符 -->
		<form v-on:submit.prevent></form>
		<!-- 添加事件侦听器时使用事件捕获模式 -->
		<div v-on:click.capture="doThis">...</div>
		<!-- 只当事件在该元素本身（而不是子元素）触发时触发回调 -->
		<div v-on:click.self="doThat">...</div>
按键修饰符
	<!-- 只有在 keyCode 是 13 时调用 vm.submit() -->
	<input v-on:keyup.13="submit">
	<!-- 同上 -->
	<input v-on:keyup.enter="submit">
	<!-- 缩写语法 -->
	<input @keyup.enter="submit">

	.enter
	.tab
	.delete (捕获 “删除” 和 “退格” 键)
	.esc
	.space
	.up
	.down
	.left
	.right
可以通过全局config.keyCodes 对象自定义按键修饰符别名
//可以使用 v-on:keyup.f1 
Vue.config.keyCodes.f1 = 112 ;
2.0版本新增 修饰符开启鼠标或键盘事件监听,使在按键按下时发生响应
	.ctrl
	.alt 
	.shift
	.meta
demo:
	<!--ALT+C -->
	<input @keyup.alt.67 = "clear">
	<!--Ctrl+click-->
	<div @click.ctrl="doSomething">Do something</div>
组件component：
组件注册：
	Vue.component(tagName,options);
组件组侧之后，便可以在父实例的模块中以自定义元素<my-component></my-component>的形式使用。要确保初始化根实例之前注册了组件：

<div id="example">
	<my-component></my-component>
</div>
//注册
Vue.component('my-component',{
	template:'<div>A custom component!</div>'
})
//创建根实例
new Vue({
	el:'#example'
});
渲染为：
	<div id="example">
		<div> A custom component</div>
	</div>
局部注册：
var Child = {
	template:'<div>A custom component!</div>'
};
new Vue({
	//...
	components:{
		'my-component':Child
}	
})