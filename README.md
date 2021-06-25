# kubeimg
## 安装
```shell
mv kubeimg /usr/local/bin/
chmod +x /usr/local/bin/kubeimg
```
## 搞了个工具方便查询应用镜像版本，使用命令：
### 默认查所有namespace
```
kubeimg image
```
### 查指定namespace
```
kubeimg image -n <namespace>
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
