#React Cheatsheet

## 入门

使用[React.js jsfiddle](http://jsfiddle.net/reactjs/69z2wepo/)开始Hack。(或者使用非官方的[jsbin](http://jsbin.com/yafixat/edit?js,output))

    var Component = React.createClass({
      render: function() {
        return <div>Hello {this.props.name}</div>;
      }
    }); 
    
    ReactDOM.render(<Component name="John" />, document.body);
    
