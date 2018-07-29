###复习
	1.基本使用
		怎么去拿画笔？
			---> var ctx = canvas.getContext("2d");
		在canvas节点身上的api
			getContext
			width
			height
		在渲染上下文ctx身上的api
			其他所有的api都挂靠在了ctx身上
		
		canvas的宽高！！！ 不能使用css属性来设置，因为会缩放图像
	2.矩形绘制
		canvas原生支持的图像绘制只有矩形一种
		ctx.fillRect() / ctx.strokeRect() / clearRect()
	3.路径绘制
		除了矩形外，其他图像的绘制都得依靠路径
		ctx.beginPath() --->  清除路径容器
		ctx.save()			--->  将当前的状态（变换 基本的样式）压栈
		ctx.restore()		--->  将栈顶状态弹出栈，弹到渲染容器中
		ctx.moveTo()    --->  将画笔移到到指定位置
		ctx.lineTo()       --->  确定路径
		ctx.rect()			---> 确定矩形的路径
		ctx.closePath()  ---> 闭合路径
		ctx.fill()				---> 填充路径(自动闭合)
		ctx.stroke()		---> 连接路径
	4.曲线绘制
		ctx.arc() ---> 注意canvas中的坐标
		
		--->  控制点  起始点  结束点
		ctx.arcTo():  可能不会经过起始点  结束点，因为其半径是自己控制
		ctx.quadraticCurveTo()   : 肯定会经过起始点  结束点 一个控制点
		ctx.bezierCurveTo: 肯定会经过起始点  结束点 二个控制点
	5.变换
		ctx.translate(): 控制canvas原点的位置
		ctx.rotate() : 控制canvas中的图像进行旋转（绕着原点）
		ctx.scale() ： 控制canvas中的图像进行缩放（按照原点）
								放大: 将画布中的css像素的个数变少 每个css像素所占的面积变大
								缩小: 将画布中的css像素的个数变多 每个css像素所占的面积变小
		
		！！！canvas中的变换是累加的
		！！！canvas中的渲染是进行过优化的，不用考虑浏览器渲染与js引擎执行快慢的问题
	6.图片的使用
		在canvas中使用图片一定要等图片加载完毕
		ctx.drawImage()
		
	7.两个实例
		时钟
		飞鸟