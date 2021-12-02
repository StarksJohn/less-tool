# less-tool

Use: 
        
    1 in your vue project
        1.1 yarn add less-tool
        1.2 npm i style-resources-loader -D
        1.3 in you vue.config.js ,add the following code:
            pluginOptions: {
            'style-resources-loader': {
              preProcessor: 'less',
              patterns: [ './node_modules/less-tool/*.less' ]
            }
            },  
    2 then you can use the variables or mixin methods defined in the .less file globally
