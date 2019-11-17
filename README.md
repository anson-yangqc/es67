# es67
```
	<script type="text/javascript">
	//情况1
	async function one(){
		const result = await test();
		console.log('s',result); //3秒后打印 s ok
	}
	function test(argument) {
		return new Promise((resolve,reject)=>{
			setTimeout(()=>{
				resolve('ok');
			},3000)
		})
	}
	one();

	//情况2
	function second(){
		return new Promise((resolve,reject)=>{
			resolve('ok');
		})
	}
	second().then(data=>{
		console.log('data',data); //data ok
	})
	</script>
```

```
<script type="text/javascript">
	async function one(argument) {

		// var one1 = two();
		// var two1 = three();
		// await one1;
		// await two1;

		await two();
		await three();
		console.log(0);
	}
	function two(argument) {
		return new Promise(function(reslove,reject){
			setTimeout(function(){
				console.log('2');
				reslove(2);
			},7000)
		})
	}

	function three(argument) {
		return new Promise(function(reslove,reject){
			setTimeout(function(){
				console.log('3');
				reslove(3);
			},2000)
		})
	}
	one();
</script>
```

```
导出 export default two; 导入 import fn from 'a.js'; 使用 a.two();
导出 export one; export two ; 导入 import {two} from 'a.js' 
错误 export 3; export {one:20}
正确 export var one = 3  ; var one=20;export {one}
```
