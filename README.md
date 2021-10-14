# Dokku Dockerfile buildpack

该插件通过实现自定义的 Dokku Builder，在原始的 Dockerfile Builder 的基础上添加前置和后置操作，在开始构建之前读取项目根目录下的 `.service.yml`
文件，选用相应的 Dockerfile 模板并编译，生成 Dockerfile 后将其发送到原始的 Dockerfile builder 中完成后续构建。并提供了在构建前后构建后执行命令的功能。

## 安装 Installation

```bash
dokku plugin:install https://github.com/syfxlin/dokku-dockerfile-buildpack.git dockerfile-buildpack
```

## 用法 Usage

该插件会查看项目根目录下是否存在 `.service.yml` 文件，若存在该文件则使用本插件来完成构建操作。

```yaml
# .service.yml，见 templates/<buildpack>/_service.example.yml
buildpack: nginx
```

## 维护者 Maintainer

XK-Java 由 [Otstar Lin](https://ixk.me/)
和下列 [贡献者](https://github.com/syfxlin/dokku-dockerfile-buildpack/graphs/contributors)
的帮助下撰写和维护。

> Otstar Lin - [Personal Website](https://ixk.me/) · [Blog](https://blog.ixk.me/) · [Github](https://github.com/syfxlin)

## 许可证 License

![License](https://img.shields.io/github/license/syfxlin/dokku-dockerfile-buildpack.svg?style=flat-square)

根据 Apache License 2.0 许可证开源。
