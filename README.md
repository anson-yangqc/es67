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
