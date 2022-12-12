# 快速生成增删改查使用说明
1. 使用EasyCodeMybatisCodeHelper插件


#  swagger使用说明
1.在Controller层添加功能说明，例如：@Api(tags = "博客中心")

2.在接口方法处添加接口说明，例如: @ApiOperation(value = "分页所有")

# 分页插件说明

例如：
```java
@Api(tags = "博客中心")
@RestController
@RequestMapping("/api/article")
public class SysArticleController {
  @ApiOperation(value = "分页所有")
  @GetMapping("/list/page/{pageNum}/{pageSize}")
  public PageInfo<SysArticle> list(@PathVariable("pageNum") int pageNum, @PathVariable("pageSize") int pageSize) {
    PageInfo<SysArticle> sysArticlePageInfo = sysArticleService.selectPageArticle(pageNum, pageSize);
    return sysArticlePageInfo;
  }
}
```