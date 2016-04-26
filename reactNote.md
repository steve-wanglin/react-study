#React 学习笔记#

##一、 React JSX 语法##

	<html>
		<head>
    	<script src="../build/react.js"></script>
    	<script src="../build/react-dom.js"></script>
    	<script src="../build/browser.min.js"></script>
		</head>
   		<body>
    	<div id="example"></div>
    	<script type="text/babel">
		** Our code goes here! **
    	</script>
    	</body>
	</html>

<h4>上面的代码有两个注意的地方：</h4>
 1.首先一个`<script>`会有一个type＝“text/labbel" 这是因为
  React独有的JSX语法，跟Javascript不兼容。凡是使用到JSX的地方，都需要加上**type＝”text/label**

2.上面的代码分别引用了三个库：react.js react-dom.js 和browser.js,他们必须首先加载，react是核心库，react-dom是提供于DOM提供相关操作的库，browser是将jsx语法专为Javascript语法，这一步最耗时间，实际上线的时候，应该将它放到服务器完成

    babel src --out-dir build

二、ReactDOM.render()

 React.render是React的基本语法，用于将模版语言转换为html语言，并插入指定的DOM节点

    ReactDOM.render(
      <h1>Hello, world!</h1>,
      document.getElementById('example')
      );