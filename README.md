# git-flow-test
## GitFlow正常步骤
### 前置步骤
1. 创建git仓库(git-flow-test)
2. 把git仓库拉取到本地或者把本地代码拉取到git仓库(可省略)
    - 拉起到本地
    ```bash
      echo "# git-flow-test" >> README.md
      git init
      git add README.md
      git commit -m "first commit"
      git remote add origin git@github.com:MrXuan3168/git-flow-test.git
      git push -u origin master
    ```
     - 把本地代码推送到该仓库
     ```bash
      git remote add origin git@github.com:MrXuan3168/git-flow-test.git
      git push -u origin master
     ```
### 后续步骤
3. 版本管理人员(老大)根据master主干新建一个develop分支进行新功能(登录注册)的实现
4. 新功能开发人员(小禤、小红)基于develop分支新建一个Feature分支进行个人任务的开发
    - 小禤Feature分支起名为"feature_login"(实现登录功能)
    - 小红Feature分支起名为"feature_register"(实现注册功能)
5. 大家在Feature分支上完成了功能以后，就可以提交代码了，然后在Git页面上发起一个"Pull request(合并请求申请)".
    > 这里不能合并到master上，只能合并到develop上
6. 老大收到合并请求以后，验证没问题，就把代码合并到develop分支上面
7. 测试或者开发人员对develop的代码进行测试
8. 等小红的代码也成功了经过合并到develop分支并且测试人员测试通过以后，则基于该develop分支创建一个预发布版本"release-1.0.0"。
9. 测试人员对release-1.0.0版本进行测试，测试没问题则请求合并到master主干上。
10. 老大收到合并请求以后，验证没问题，就把代码合并到master主干上面
11. 基于master主干创建一个里程碑版本(tag) "1.0.0-Release"
12. 删除已经完成使命的分支"feature_login"、"feature_register"、"release-1.0.0"

## 当里程碑版本出现bug时的处理步骤
1. 当用户发现"1.0.0-Release"版本发现bug的时候，需要新建一个issue，把bug描述清楚。
2. 开发人员或者老大基于tag新建一个分支，名字为"hotfix_0001(该issue序号)"
3. 开发人员修复bug以后，提交代码到hotfix分支上面，然后新建一个合并请求(这里直接合并到master主干上)。
4. 测试人员测试没问题以后，基于master主干新建一个tag标签"release-1.0.1"
5. 删除已经完成使命的分支"hotfix_0001"


