# vue对象配置参数
* 1.el 要绑定dom元素作为 vue的控制区间
* 2.data 就绑定该区间内的数据
* 3.methods 绑定该区间内的方法，但是这些方法会随着视图的变化而不断的执行
* 4.computed 绑定该区间内的方法，使用方式不需要调用该方法，写方法名就可以，并且如果说和他关联的数据没有发生改变，那么视图的变化不会触发该方法的执行
# 事件对象：
        @click="show($event)";
# 事件冒泡：
        阻止冒泡：①event.cancelBubble=true; 
                   ②@click.stop="";    //推荐
# 默认行为(默认事件)：                                         
        contextmenu() -> 右键触发 contextmenu 事件
        阻止：①event.preventDefault();
	     ②@contextmenu.prevent=""  //推荐           
# 键盘事件：
	@keydown  $event  event.keyCode;
	@keyup  $event  event.keyCode;
	常用键： 
	      回车：①event.keyCode==13；②@keyup.13=""；③@keyup.enter=""
# 属性：
	v-bind:src="url"  
	简写  :src="url"    :width="width"   :height="height"   :title="title"   //推荐     
# class和style:
	  :class=""   v-bind:class=""
	  :style=""   v-bind:style=""

	  :class="[red]"   red是数据              style{.red{color:red}}   data:{red:'red'}
	  :class="[red,b]" 

	  :class="{red:true,blue:true}"     red,blue是类名     style{.red{color:red}} 

	  ：class="json"     data:{json:{red:true,blue:true}}
	  ```````````````````````````````````````````````````````
	  :style:
	  :style="[red]"                  data:{red:{color:'red'},b:{bcakground:'blue'}}
	  :style="[red,b]"
	  注意：符合样式采用驼峰命名法
 # 模版：
	{{msg}}   数据更新模版变化
	{{*msg}}   数据只绑定一次    （1.0版）    <span v-once>这个将不会改变: {{ msg }}</span> （2.0版）
	{{{msg}}}  html转义输出    （1.0版）		<span v-html="msg"></span>  （2.0版）         
