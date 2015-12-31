#React Cheatsheet

## 入门

使用[React.js jsfiddle](http://jsfiddle.net/reactjs/69z2wepo/)开始Hack。(或者使用非官方的[jsbin](http://jsbin.com/yafixat/edit?js,output))

    var Component = React.createClass({
      render: function() {
        return <div>Hello {this.props.name}</div>;
      }
    }); 
    
    ReactDOM.render(<Component name="John" />, document.body);
    
##嵌套

使用嵌套组件分离关注点。查看[多组件](http://facebook.github.io/react/docs/multiple-components.html)

    var UserAvatar = React.createClass({ ... });
    var UserProfile = React.createClass({ ... });
    
    var Info = React.createClass({
      render() {
        return (
          <div>
            <UserAvatar src={this.props.avatar} />
            <UserProfile username={this.props.username} />
          </div>
        );
      }
    });
    
##状态和属性

使用[props](https://facebook.github.io/react/docs/tutorial.html#using-props)(this.props)访问父类传递过来的参数。使用[state](https://facebook.github.io/react/docs/tutorial.html#reactive-state)(this.state)管理动态数据。

    <MyComponent fullscreen={true} />
    
    //属性
    this.props.fullscreen //=> true
    
    //状态
    this.setState({username: 'rstacruz'});
    this.replaceState({ ... });
    this.state.username   //=> 'rstacruz'
    
    render: function() {
      return (
        <div className={this.props.fullscreen ? 'full' : ''}>
          Welcome, {this.state.username}
        </div>
      );
    }
    
###设置默认值

提前渲染this.state.comments和this.props.name。

    React.createClass({
      getInitialState: function () {
        return { comments: []};
      }
      
      getDefaultProps: function () {
        return { name: "Hello"};
      }
    });
    
##组件API

这些是组件实例可以访问的方法。查看[组件API](http://facebook.github.io/react/docs/component-api.html)。

    ReactDOM.findDOMNode(c) // 0.14+
    React.findDOMNode(c)    // 0.13
    c.getDOMNode()          // 0.12 以下
    
    c.forceUpdate()
    c.isMounted()
    
    c.state
    c.props
    
    c.setState({ ... })
    c.replaceState({ ... })
    
    c.setProps({ ... })     //废弃
    c.replaceProps({ ... }) //废弃
    
    c.refs
    
###组件规范

你可以重写方法和属性。查看[组件规范](http://facebook.github.io/react/docs/component-specs.html)

    render()
    
    getInitialState()
    
    getDefaultProps()
    
    mixins: [ ... ]         混入... [更多](http://ricostacruz.com/cheatsheets/react.html#mixins)
    
    propTypes: { ... }      校验... [更多](http://ricostacruz.com/cheatsheets/react.html#property-validation)
    
    statics: { ... }        静态方法
    
    displayName: "..."      JSX自动填充
    
