# 使用NTFS格式的移动硬盘

## 第一步：查看待挂载硬盘分区的名称

1. 在终端下输入以下命令：
```
diskutil list
```
2. 在以下命令返回结果中找到所需使用分区对应的`NAME`字段信息
```
/dev/disk2 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     FDisk_partition_scheme                        *16.0 GB    disk2
   1:               Windows_NTFS ymc                     16.0 GB    disk2s1
```
3. 确认所需挂载的分区名为`ymc`

## 第二步：修改系统配置，实现移动硬盘插入后自动挂载

1. 编辑系统配置文件
```
sudo vim /etc/fstab
```
2. 在配置文件中增加以下信息
```
LABEL=ymc none ntfs rw,auto,nobrowse
```
3. 保存文件并重新拔插移动硬盘

## 第三步：在桌面上增加访问移动硬盘的快捷方式

在终端下输入以下命令：
```
sudo ln -s /Volumes ~/Desktop/我手工挂载的硬盘
```