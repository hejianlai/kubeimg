# kubeimg
## 安装
```shell
curl https://github.com/hejianlai/kubeimg/releases/download/v1.0/kubeimg
mv kubeimg /usr/local/bin/
chmod +x /usr/local/bin/kubeimg
```
## 使用命令
### 默认查所有namespace
```
kubeimg image
```
### 查指定namespace
```
kubeimg image -n <namespace>
```
### 作为kubectl扩展插件使用

kubectl 提供一个命令 kubectl plugin list，用于搜索路径查找有效的插件可执行文件。 执行此命令将遍历路径中的所有文件。任何以 kubectl- 开头的可执行文件都将在这个命令的输出中以它们在路径中出现的顺序显示。 任何以 kubectl- 开头的文件如果不可执行，都将包含一个警告。 对于任何相同的有效插件文件，都将包含一个警告。

```shell
cp /usr/local/bin/kubeimg /usr/local/bin/kubectl-img
kubectl plugin list
kubectl img image
```
## 开发步骤
使用cobra库：https://github.com/spf13/cobra
```shell
mkdir kubeimg
cd kubeimg
cobra init --pkg-name github.com/hejianlai/kubeimg
go mod init github.com/hejianlai/kubeimg
cobra add image
```
