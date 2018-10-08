# vuetest
全局引入less、sass

npm install less less-loader --save 
或者
npm install sass-loader node-sass --save-dev

接着再安装
npm install sass-resources-loader --save-dev

在build/utils.js中进行配置
```
function resolveResource(name) {
    return path.resolve(__dirname, '../src/assets/less/' + name);
}
```

```
less: generateLoaders('less').concat(
      {
       loader: 'sass-resources-loader',
        options: {
          resources: [resolveResource('var.less'),resolveResource('mixin.less')]
        }
      }
   ),
```
    
就可以使用了 
   


