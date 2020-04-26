[toc]

## does not exist in the Haste module map
 问题描述
>安装完新的插件后，提示之前的安装的插件出现问题。提示‘Module react-native-screens does not exist in the Haste module’

解决方法

1. 安装提示不存在的插件
```
    // react-native-* 为提示不存在的插件的名称
    npm install react-native-* -save 
```

2. 关闭命令行终端窗口，再打开命令行行
```
    yarn start --restart-cache 或者 npm start --reset-cache
```

3. 重新在手机上摇一摇进入开发者界面，点击reload


