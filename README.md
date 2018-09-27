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
导出 export default two; 导入 import fn from 'a.js'; 使用 a.two();
导出 export one; export two ; 导入 import {two} from 'a.js' 
错误 export 3; export {one:20}
正确 export var one = 3  ; var one=20;export {one}
```
