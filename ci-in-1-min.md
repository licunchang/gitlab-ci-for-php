# Continuous Integration in 1 Minute(1 分钟初探 PHP 项目在 gitlab 中的持续集成)

## 0 功能

* 语法检查
* 代码规范检查(PSR-2)

## 1 下载 CI 配置文件

在 PHP 项目的根目录下下载 CI 配置文件 `.gitlab-ci.yml`，你可以通过下面的命令快速下载。

```
curl -L https://github.com/licunchang/gitlab-ci-for-php/raw/master/.gitlab-ci.yml -o .gitlab-ci.yml
```

## 2 提交 .gitlab-ci.yml 文件

将 `.gitlab-ci.yml` 文件提交并 push 到 gitlab。

```
git add .gitlab-ci.yml
git commit -m "add .gitlab-ci.yml file"
git push
```

## 3 登录 gitlab 查看集成报告

登录 gitlab，选择刚刚提交了 .gitlab-ci.yml 文件的 project，点击左侧菜单栏 `CI/CD` -> `Pipelines`，就能看到这次集成的状态了。



Have Fun！