<h1 align="center">Rong6-Navigation</h1>

## 这是什么？

这是一个在[WebStack-Hugo](https://github.com/shenweiyan/WebStack-Hugo)的基础上修改的导航网站。   
本质上，此仓库是为我的“[荣6的网站导航](https://nav.rong6.cn)”服务的。    

由于此项目修改历史过于长远，我也不太记得修改了啥了ヽ(ー_ー)ノ 大致为
- 修改一些细节
- 删除无用功能
- 添加SEO优化
- 添加跳转页（需手动添加，详情见[这](redirect-config)）

## 使用
### 安装
克隆代码：
``` bash
git clone https://github.com/rong6/Rong6-Navigation.git
```

前往[Hugo仓库Releases](https://github.com/gohugoio/hugo/releases)下载自己对应版本的Hugo二进制文件，将`hugo.exe`或`hugo`文件移植克隆仓库根目录下。    

以Windows为例，在克隆仓库根目录下打开CMD，输入
```
# 检查Hugo是否正常
hugo.exe --version
# 启动开发服务器
hugo.exe server
```
启动后打开http://127.0.0.1:1313即可预览效果。

### 配置
#### 配置文件
以下是该主题重要的一些配置文件。
- `config.toml`为站点配置文件，修改可更改站点基础配置。
- `data/friendlinks.yml`为友情链接配置文件，修改后友链将会显示在站点最下面的“友情链接”分类内。
- `data/headers.yml`为导航栏配置文件，修改后顶部导航栏将会变更。
- **`data/webstack.yml`** 为导航链接配置文件，非常重要，配置见[这](#webstack-config)。

<a name="webstack-config"></a>
#### `data/webstack.yml`配置
这是`data/webstack.yml`文件的示例配置，`taxonomy`为分类名，`icon`为图标，`description`为网站介绍，`logo`为网站图标，`title`为网站标题，`url`为网站地址：
```
- taxonomy: 科研办公
  icon: fas fa-flask fa-lg
  list:
    - term: 生物信息
      links:
        - title: NCBI
          logo: ncbi.jpg
          url: https://www.ncbi.nlm.nih.gov/
          description: National Center for Biotechnology Information.
        - title: Bioconda
          logo: bioconda.jpg
          url: https://anaconda.org/bioconda/
          description: "Bioconda :: Anaconda.org."
    - term: 云服务器
      links:
        - title: 阿里云
          logo: 阿里云.jpg
          url: https://www.aliyun.com/
          description: 上云就上阿里云。
        - title: 腾讯云
          logo: 腾讯云.jpg
          url: https://cloud.tencent.com/
          description: 产业智变，云启未来。
```

<a name="redirect-config"></a>
#### 跳转页
本人技术不太行，没法做到全局的第三方链接都自动经过跳转页，你需要将`url`的值改为`./redirect/?url=<URL_BASE64>`，例如跳转到`www.baidu.com`则是`./redirect/?url=aHR0cHM6Ly93d3cuYmFpZHUuY29t`。

#### 图标
全站都使用Font Awesome的图标库，可在[Font Awesome官网](https://fontawesome.com/v5/search?o=r&m=free)挑选图标。   
对于获取第三方站点图标可使用`https://api.iowen.cn/favicon/<domain>.png`，例如`https://api.iowen.cn/favicon/www.baidu.com.png`。   

更多的一些配置可查看[原仓库](https://github.com/shenweiyan/WebStack-Hugo)。

## 提交网站
由于网站太多了不好整合，难免有遗漏之地方，你可以向我提交你想分享的网站，可使用**Pull Requests**或[金数据](https://jsj.top/f/jpXJhz?x_field_1=github)提交，nav.rong6.cn每隔一段时间都会自动拉取最新页面。