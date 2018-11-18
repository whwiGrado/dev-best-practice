# Dev Best Practice

## node 安装与版本管理
> 工具：[nvm](https://github.com/creationix/nvm)

## npm 源管理
> 工具：[nrm](https://github.com/Pana/nrm)

## yarn 常用命令
- yarn init：初始化包
- yarn install || yarn：安装 package.json 文件里定义的所有依赖包
- yarn add：为当前正在开发的包新增一个依赖包

    ```bash
  yarn add <package...>
    这将安装您的dependencies中的一个或多个包。

  yarn add <package...> [--dev/-D]
    用 --dev 或 -D 会在 devDependencies 里安装一个或多个包。

  yarn add <package...> [--peer/-P]
    用 --peer 或者 -P 会在 peerDependencies 里安装一个或多个包。

  yarn add <package...> [--optional/-O]
    用 --optional 或者 -O 会在 optionalDependencies 里安装一个或多个包。

  yarn add <package...> [--exact/-E]
    用 --exact 或者 -E 会安装包的精确版本。 默认是安装包的主要版本里的最新版本。 比如说， yarn add foo@1.2.3 会接受 1.9.1 版，但是 yarn add foo@1.2.3 --exact 只会接受 1.2.3 版。

  yarn add <package...> [--tilde/-T]
    用 --tilde 或者 -T 来安装包的次要版本里的最新版。 默认是安装包的主要版本里的最新版本。 比如说，yarn add foo@1.2.3 --tilde 会接受 1.2.9，但不接受 1.3.0。
    ```

- yarn remove：从当前包里移除一个未使用的包
- yarn publish：发布一个包到包管理器
- yarn <script> 将会执行用户自定义脚本，相当于 yarn run <script>
- yarn global <add/bin/list/remove/upgrade> [--prefix] 安装到全局目录
- yarn workspace <workspace_name> <command> 这会在所选工作区中运行对应的 yarn 命令

	```bash
  yarn workspace awesome-package add react react-dom --dev
  会将 react 和 react-dom 作为 devDependencies 加到 packages/awesome-package/package.json 中

  yarn workspace awesome-package remove react react-dom --save
  将会从 packages/awesome-package/package.json 中移除 react react-dom
	```
- yarn config list 查看当前配置，如 registry 等
- yarn info 查看某个包的信息
  
  ```bash
  yarn info <package> [<field>] 例如：
  
  yarn info <package> time
  查看某个包的所有版本的 release time
  
  yarn info <package> versions
  查看某个包的所有版本
  
  yarn info <package> license
  查看某个包的 license
  
  yarn info <package> dependencies
  查看某个包的依赖
  ```
- yarn link
  ```bash
  例如：在 core-web 中创建一个软连接到 libs/ui-components，操作如下：
  cd {repo_path}/libs/ui-components
  yarn link
  cd {repo_path}/packages/core-web
  yarn link ui-components
  ```

## [语义化版本号](https://github.com/whwiGrado/dev-best-practice/blob/master/Semantic-Versioning2.0.0.md)



