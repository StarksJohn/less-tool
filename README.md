# less-tool

Use: 
        
    1 in your vue project
        1.1 yarn add less-tool or npm i less-tool
        1.2 npm i style-resources-loader -D
            1.2.1 npm i vue-cli-plugin-style-resources-loader -D
            1.2.2 npm i less-loader -D
            1.2.3 npm i less -D
        1.3 in you vue.config.js ,add the following code :
            module.exports = {
                 pluginOptions: {
                'style-resources-loader': {
                  preProcessor: 'less',
                  patterns: [ './node_modules/less-tool/*.less' ]
                }
                }, 
            }
        1.4 del sass-loader and node-sass in your packages.json

    2 in your vite project, add the following code in vite.config.js
              css: {
                modules: {
                  localsConvention: 'dashesOnly'
                },
                preprocessorOptions: {
                  less: {
                    // Support inline JavaScript
                    javascriptEnabled: true,
                    // https://blog.csdn.net/yun_master/article/details/120050054 Global references Less file
                    additionalData: `@import "${path.resolve(__dirname, './node_modules/less-tool/mixin.module.less')}";`
                    }
                  }
                }
    3 then you can use the variables or mixin methods defined in the .less file globally


Push:
        
        1 update the version in package.json , eg : https://www.cnblogs.com/isYunjiang/p/16483363.html 
            1.0.0 -> 1.0.1  npm version patch
            1.0.1 -> 1.1.0  npm version minor
            1.1.0 -> 2.0.0  npm version major
        2 git commit -a -s -m 'add' && npm version patch && git push origin main && npm login && npm publish
        3 Finally, in your main project, yarn add less-tool or npm i less-tool
