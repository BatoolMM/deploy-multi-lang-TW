# 代码测试清单

这份清单载有许多项目。 正如上面提到的 {ref}`<rr-testing-write-tests>`所述，做一些项目要比没有项目要好得多。 如果这份任务清单似乎不可逾越，请不要气馁。

<a name="Writing_tests"></a>

## 写入测试

- 写几次烟雾测试。
- 为您的所有代码单位写入单元测试。
- 写入集成测试以检查各单元之间的集成。
- 写下几个系统测试。 通过程序优先安排共同和重要的路径。
- 写回归测试。 回归测试可以在任何级别上进行。
- 如果适合您的项目写入验收测试。
- 将运行时间测试添加到您的项目。

<a name="Good_practice_checks"></a>

## 良好做法检查

- [ ] 记录测试以及如何运行这些测试。
  - [ ] 写下脚本来设置和配置运行测试所需的任何资源。
- [ ] 选择并使用测试框架。
- [ ] 定期运行测试。
  - [ ] 自动运行测试过程。 考虑利用连续一体化（见连续一体化一章）来实现这一目标。
- [ ] 检查测试的代码覆盖面并尝试改进它。
- [ ] 与伙伴一起参与代码审查。