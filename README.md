# Personal STM32 Projects Workspace

个人的STM32项目工作区

支持CubeIDE，CubeMX + Keil

## 环境

CubeIDE : last

CubeMX  : last

Vscode  : last

MDK-ARM : last

PACK : last

Java    : 1.8



> `能更新我就更新`

## 使用说明 

### 克隆仓库: 

> git clone --recursive https://github.com/9cats/STM32Embed.git

### 更新仓库:

###### 更新工作区

> git pull

###### 更新子模块

> git submodule update

### 使用简介

#### CubeIDE

##### 创建工作区

CubeIDE新建工作区`(New Workspace)`于本文件夹中

##### 编译运行

用CubeIDE先打开.ioc文件生成代码(项目中没有`Drivers/CMSIS` 和 `Drivers/STMXX_HAL_Driver`)然后直接运行

#### CubeMX + MDK-ARM

直接打开.ioc文件，在`Project Manager`中选择`ToolChain/IDE(编译用到的软件，默认为CubeIDE)`为`MDK-ARM`，然后正常使用
### 更新冲突

克隆项目后若自行添加CubeIDE项目，则不能正常更新仓库

> 因为该项目中的`.metadata文件夹`里包含CubeIDE相关配置，一但自行添加就会有冲突，这里建议每次更新时保留本地的`.metadata文件夹`