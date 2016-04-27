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

##二、ReactDOM.render()##

 React.render是React的基本语法，用于将模版语言转换为html语言，并插入指定的DOM节点

    ReactDOM.render(
      <h1>Hello, world!</h1>,
      document.getElementById('example')
      );

## 三、this.props.children     


     var NameTag=React.createClass({
     render:function(){
     return(<ol>{
     React.Children.map(this.props.children,function(child){

     return <li>{child}</li>
     })

     }
     </ol>
     );
     }
     });

需要注意的是，children的值有三种可能：undefined,object,array,如果没有字节点,则为**undefined**,有一个子节点，则为**object**,大于1的时候为**array**

React 提供一个工具方法 React.Children 来处理 this.props.children 。我们可以用 React.Children.map 来遍历子节点，而不用担心 this.props.children 的数据类型是 undefined 还是 object。更多的 React.Children 的方法，[请参考官方文档](https://facebook.github.io/react/docs/top-level-api.html#react.children)。


## 四、PropTypes
组件的属性可以接受任意值，字符串、对象、函数等等斗可以。有时，我们需要一种机制，验证别人使用组件时，提供的参数是否符合要求。
组件类的PropTypes属性，就是用来验证组件实例的属性是否符合要求。
    
    var MyTitle = React.createClass({
    propTypes: {
    title: React.PropTypes.string.isRequired,
    },
    render: function() {
     return <h1> {this.props.title} </h1>;
    } 
    });
    
上面的Mytitle组件有一个title属性。PropTypes 告诉 React，这个 title 属性是必须的，而且它的值必须是字符串。现在，我们设置 title 属性的值是一个数值。  
    
   
