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

    var UserAvatar = React.createClass({...});
    var UserProfile = React.createClass({...});
    
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
    
