<h4>webpack相关</h4>

- [webpack](http://webpack.github.io/)
- [深入浅出的webpack](http://webpack.wuhaolin.cn/)
- [webpack性能优化1](https://zhuanlan.zhihu.com/p/27710902)
- [webpack性能优化2](https://zhuanlan.zhihu.com/p/26710831?refer=ElemeFE)
- [Webpack 和 React 小书](https://fakefish.github.io/react-webpack-cookbook)
webpack	https://github.com/webpack/webpack
Webpack，101入门体验	http://html-js.com/article/3009
webpack入门教程	http://html-js.com/article/3113
基于webpack搭建前端工程解决方案探索	http://segmentfault.com/a/1190000003499526

### webpack中loader和plugin：
对于loader，它就是一个转换器，将A文件进行编译形成B文件，这里操作的是文件，比如将A.scss或A.less转变为B.css，单纯的文件转换过程；  

对于plugin，它就是一个扩展器，它丰富了wepack本身，针对是loader结束后，webpack打包的整个过程，它并不直接操作文件，而是基于事件机制工作，会监听webpack打包过程中的某些节点，例如
run：开始编译  
make：从entry开始递归分析依赖并对依赖进行build  
build-moodule：使用loader加载文件并build模块  
normal-module-loader：对loader加载的文件用acorn编译，生成抽象语法树AST  
program：开始对AST进行遍历，当遇到require时触发call require事件  
seal：所有依赖build完成，开始对chunk进行优化（抽取公共模块、加hash等）  
optimize-chunk-assets：压缩代码  
emit：把各个chunk输出到结果文件  