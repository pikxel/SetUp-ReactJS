# SetUp-ReactJS
Fast setup of Hello World in React:


1.Make the root folder for your app.
2.$ npm init
3.$ npm install --save react
4.$ npm install --save react-dom
5.$ npm install --save babel-core babel-loader babel-preset-es2015 babel-preset-react
6.$ mkdir public (you have to be inside of your root folder)
7.$ cd public
8.$ touch Main.htm
9. Edit Main.html :

<!DOCTYPE html>
<head>
  <meta charset="UTF-8">
</head>
<body>
  <div id="app"></div>
  <script src="bundle.js"></script>
</body>
</html>

10.Navigate back to your root directory
11.$ touch webpack.config.js
12.npm install webpack@2.1.0-beta.22 --save-dev
13.Setup webpack.config.js: 

module.exports = {
  entry: "./app/components/Main.js",
  output: {
    filename: "public/bundle.js"
  },
  module: {
    loaders: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        loader: 'babel',
        query: {
          presets: ['react', 'es2015']
        }
      }
    ]
  }
}

14.$ mkdir app
15 $ cd app
16 $ mkdir components
17 $ cd components
18 $ touch Main.js
19 Edit Main.js 

var React = require('react');
  var ReactDOM = require('react-dom');

  var Main = React.createClass({
    render: function(){
      return(
        <div>
          Hello World
        </div>
      )
    }
  });

  ReactDOM.render(<Main />, document.getElementByID('app'))
  
  
  20.$ wewbpack -w 
  21. Enjoy coding
