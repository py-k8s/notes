# go 项目基础使用

1. 创建项目
```
mkdir ops-go
cd ops-go
go mod init github.com/py-k8s/ops-go
```
2. 下载依赖包
``` 
go get k8s.io/client-go@latest
```

3. 导入自己的依赖包
```
import (
	"fmt"
	// 这里的包名前缀要和 go mod init github.com/py-k8s/ops-go 中的项目名称一致
	"github.com/py-k8s/ops-go/libs"
)
```

4. 下载所有依赖包
```
go get
```

5. 一个目录下只能有一个 GO 文件允许有 func main() 入口，不然会报错
```
main redeclared in this block compiler DuplicateDecl
```

6. golang 在 windows 系统编译 linux 可执行文件
```
// 在 cmd 或者 powershell 执行以下命令
set GOARCH=amd64
go env -w GOARCH=amd64
set GOOS=linux
go env -w GOOS=linux

// 切换回 windows
go env -w GOARCH=amd64
go env -w GOOS=windows
```
