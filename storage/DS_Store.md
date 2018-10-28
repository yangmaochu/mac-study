# 控制DS_Store文件的生成

mac会在每个文件夹下生成一个`.DS_Store`文件用于保存文件夹的自定义属性，如文件的图标位置或背景色，相当于Windows的desktop.ini。

##  禁止`.DS_store`生成

```
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool TRUE
```

## 恢复`.DS_store`生成

```
defaults delete com.apple.desktopservices DSDontWriteNetworkStores
```