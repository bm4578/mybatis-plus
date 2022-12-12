
PS：因为SpringBoot项目每次都需要搭建测试环境，又因为每个依赖经常更新，导致有时候会因为版本冲突而造成的bug，而半天摸不着头脑。对此我将整合了常用的开发环境与所需版本，只需要导入项目就可以直接写增删改查，避免每次因选择版本而浪费时间。
本项目整合了SpringBoot+mybatis-plus+pagehelper(分页插件)+knife4j(原版swagger)+druid+mysql
，其目的是为了更快的写增删改查。

功能如下：
1. 快速进入测试页面
![](https://raw.githubusercontent.com/bm4578/images/master/202212121740189.png)
2. swagger页面
![](https://raw.githubusercontent.com/bm4578/images/master/202212121743222.png)
### 快速生成增删改查使用说明
1. 在idea中使用EasyCodeMybatisCodeHelper插件
###  swagger使用说明
1.在Controller层添加功能说明，例如：@Api(tags = "博客中心")
2.在接口方法处添加接口说明，例如: @ApiOperation(value = "分页所有")
### 分页插件说明

例如：
```java
@Api(tags = "博客中心")
@RestController
@RequestMapping("/api/article")
public class SysArticleController {
  @ApiOperation(value = "分页所有")
  @GetMapping("/list/page/{pageNum}/{pageSize}")
  public PageInfo<SysArticle> list(@PathVariable("pageNum") int pageNum, @PathVariable("pageSize") int pageSize) {
      return sysArticleService.selectPageArticle(pageNum, pageSize);
  }
}
```