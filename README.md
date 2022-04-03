# less-tool

Use: 
        
    1 in your vue project
        1.1 yarn add less-tool
        1.2 npm i style-resources-loader -D
            1.2.1 npm i vue-cli-plugin-style-resources-loader -D
        1.3 in you vue.config.js ,add the following code:
            pluginOptions: {
            'style-resources-loader': {
              preProcessor: 'less',
              patterns: [ './node_modules/less-tool/*.less' ]
            }
            },  
        1.4 in your vite project, add the following code in vite.config.js
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
    2 then you can use the variables or mixin methods defined in the .less file globally


Push:

        git commit -a -s -m ' '
        git push origin main
        npm publish
