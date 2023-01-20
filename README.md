# Python Project Skeleton

# 基本操作

- 本地搭建
  - 本地构建: 执行 build.sh
  - 本地安装 (develop 形态, 方便调试和测试): 执行 dev_install.sh
  - 本地测试: 执行 test.sh, 之前需要先本地安装
  - CI: 已经配好
- 生成项目
  - 在本项目代码根目录中执行 ./populate.sh dst, 其中 dst 是你的目标路径
  - 上述操作将把代码框架复制到 dst 路径下

注意:

- 本地运行时若有依赖包, 请自行安装

# 目录结构

- 代码都在 src/da 目录下, 并导致经此 skeleton 构造的包都在 da namespace 下, 例如本例构造的包名为 da.sample. 可以在 src/da 下新建多个目录, 都会包括在同一个 python 包中
- 请不要直接在 src 目录下新建与 da 平行的目录. 所有代码都应在 src/da 下创建新的目录, 且尽量不要把代码直接放在 src/da 目录下
- 测试都在 tests 目录中
- CI 相关文件在 docker 目录下和 .gitlab-ci.yml 文件中, 一般情况下无需修改

# 发布

CI 会自动发布, 无需配置, 但默认发布的版本都是 0.0.0. 只有当前 commit 对应一个 tag, 且 tag 名为 release-x.y.z 时才会发布为版本 x.y.z. 正常情况下无需修改 CI 配置 (.gitlab-ci.yml)

# 依赖

修改下述 requirements 文件将自动更改 CI 镜像, 但不会在本地环境中安装依赖:
- requirements.txt: 正常运行时需要的依赖
- requirements-dev.dev: 开发期间的依赖
- requirements-docs.txt: 为了生成文档而需要的依赖
- requirements-test.txt: 为了运行测试而需要的依赖

# 说明
基于 cookiecutter 快速生成项目
cookiecutter 项目地址: https://github.com/cookiecutter/cookiecutter

- 生成文档的脚手架
