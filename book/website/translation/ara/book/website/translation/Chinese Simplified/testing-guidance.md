<a name="General_guidance_and_good_practice_for_testing"></a>

# 测试的一般指导意见和良好做法

有几种 {ref}`不同的类型`<rr-testing-types-of-testing> (b) 每个国家都有特定最佳做法的测试结果。 然而,这里将概述一些适用于所有这些方面的一般性指导。

(r-test-writes)=
## 写测试-任何测试!

开始写入测试的过程可能会非常庞大,特别是如果你有一个大的代码基础。 此外,如上所述,有许多类型的测试,所有测试的实施似乎都是不可能登山的山脉。 这就是为什么本章中最重要的指导内容如下： **写一些测试**。 在代码中测试一件很长的小件事,这件事比测试一件长于数千行的代码中没有什么要好。 您可能无法做所有事情,但是做 *个很有价值。* 是很有价值的。

在您可以的地方进行改进 并尽最大努力将测试包括在您写的新代码中,即使不可能为已写入的所有代码写入测试。

## 运行测试

本章中第二项最重要的建议：进行测试。 如果你很少运行它,拥有一个美丽、完美的测试套件是没有用的。 在测试运行之间留下长期空白,使得更难追踪测试失败时出现的问题,因为这样做是因为： 很多代码将被更改。 而且,如果自进行试验以来已经过去了几个星期或几个月,而试验失败, 很难或不可能知道在平均时间内获得的结果仍然有效, 它们可能已经受到了bug的影响,必须被抛弃。

最好是尽可能实现测试自动化。 如果每次试验都需要单独进行,那么这种艰苦的过程很可能被忽视。 可以通过使用测试框架来做到这一点([稍后讨论](#use-a-testing-framework))。 [Jenkins](https://jenkins.io) 是这方面的另一个好工具。 最好设置您的测试能够定期运行,可能是每晚运行。

考虑在您的项目上设置连续集成(在连续集成章节中讨论)。 每次更改代码时,这将自动运行测试, 根据您使用的连续集成软件,如果测试失败,将通知您。

## 请考虑运行测试需要多长时间

بعض الاختبارات، مثل {ref}`محرر الاختبار` فقط اختبار قطعة صغيرة من التعليمات البرمجية وبالتالي عادة ما تكون سريعة جدا. غير أن أنواعاً أخرى من الاختبارات، مثل {ref}`نظام اختبار rr-test-system` التي تختبر الكود بأكمله من النهاية إلى النهاية، قد يستغرق تشغيله وقتاً طويلاً اعتماداً على التعليمات البرمجية. 因此,在每次几分工作之后运行整个测试套装都可能是阻碍性的。 在这种情况下,最好是经常进行体重较轻的检验,如单体检验,而长时间的检验则是每天隔夜只进行一次。 您每种测试的数量相对于运行需要多长时间,也是很好的。 您应该有很多单元测试(或其他类型的测试速度较快),但要运行很长时间的测试要少得多。

## 记录测试和如何运行

必须提供文件,说明如何进行试验。 两者都是为了您自己,以防您将来回到一个项目。 和任何其他希望在你的工作基础上更上一层楼或转载你的工作的人。 这份文件还应包括下列主题：

- 任何资源,例如需要的测试数据集文件
- 运行测试所需的任何配置/设置调整
- 需要安装什么软件 (例如 [测试框架](#use-a-testing-framework))

理想的情况是,您将提供脚本来设置和配置任何需要的资源。

## 测试现实案件

使您测试的案例尽可能切合实际。 例如,如果： 您有运行测试的虚拟数据,请确保数据尽可能与实际数据相似。 如果您的实际数据带有很多空值,那么您的测试数据集应该是空的。

## 使用测试框架

有一些工具可以使写作和运行测试更加容易,这些工具被称为测试框架。 找一个你喜欢的人,学习它提供的功能并加以利用。 共同测试框架(及其所用语文)包括：

- 语言毒性
  - CTest, 测试运行器, 基础脚本, 等等。 优秀的旧代码硬化
- ++C
  - 捕获量
  - كعكة <unk>
  - 升起：测试
  - 谷歌测试
- ج
  - 所有 C++ 框架
  - 检查
  - CUnit
```{note}
虽然现代C+++和C仍然大多兼容,但它们并不完全,可以互换使用测试框架。
```
- Python
  - الاختبار (<unk> )
  - unittst来自标准的 Python 库
- R 单位测试
  - 测试
  - tinytest
  - svUnit (使用 SciViewGUI)
- Fortran 单元测试：
  - 英尺单位
  - pfunt (与 MPI 一起工作)

## 力求有一个很好的代码范围

代码覆盖面是测试“覆盖”你的代码的一个尺度。 更确切地说,这是衡量在进行测试时你的代码运行多少次。 例如： 如果你有 `如果语句` 语句,但只测试如果语句评为“False”,那么如果方块将不会运行任何代码。 因此,你的代码覆盖率将是 < 100%。 代码覆盖面不包含注释等文档,所以添加更多文档不会影响您的百分比。

正如所讨论的那样,任何试验都比没有试验有改进。 然而,我们至少希望你的代码覆盖面尽可能高,这是很好的。

大多数编程语言都有可以输入的工具,或者可以导入的工具,或者作为测试框架的一部分,自动衡量代码覆盖面。 测量代码覆盖面也有很好的 [bot](https://codecov.io/)。

**弹着：覆盖面好的幻想。** 在某些情况下,相同的代码可以而且可能应该以多种方式测试。 例如,可以快速增加对输出应用“健康检查”测试的代码的覆盖率(另见 {ref})<rr-testing-challenges-difficult-quatify>但这并不排除这样的风险：由于错误的原因,代码正在产生基本正确的答案。 一般而言,最好的测试是将前后一致的代码中的较小而不是较大的组别隔开。 然后挑出单独的逻辑步骤。 尝试以思考在执行整个过程中可能出现的特定代码块的可能情况为指导。 并检验这些个别案件。 这常常会导致同一代码经过多次测试——这是个好事!

## 酌情使用双倍测试/模拟器

如果试验失败,应构造尽可能容易地追踪失败的来源。 如果你想要测试的代码不可避免地依赖于其他东西,这将成为问题。 例如,如果测试一个与 web 交互的代码失败, 这可能是因为代码有一个 bug *或* ,因为互联网连接有问题。 同样,如果使用对象的代码测试失败,可能是因为正在测试代码中存在错误, 或对象的问题(应通过自己单独的试验进行测试)。 如果可能,应从测试中删除这些依赖项。 这可以通过在真正依赖的地方使用测试替代(测试双倍)来实现。 测试双倍可分类如下：

- 虚拟对象已经传递,但从未使用,意味着它的方法从未被调用。 这种对象可以用来填充方法的参数列表。
- 假冒对象有工作实现,但通常是简化的。 例如,他们使用内存数据库,而不是真正的数据库。
- 一件事是部分实现一个接口或类,目的是在测试过程中使用此件事的实例。 Stubs 通常不会对任何计划进行测试以外的东西作出反应。 Stubs也可以录制电话信息。
- 模拟对象是用于定义某个方法调用输出的接口或类的虚拟实现。 模拟对象被配置为在测试期间执行特定行为。 它们通常记录与系统的互动情况,测试可以证实这一点。

测试双倍可传递到其他测试对象。

您可以手动创建模拟对象 (通过代码) 或使用模拟框架模拟这些类。 模拟框架允许您在运行时创建模拟对象并定义其行为。 模拟对象的典型例子是数据提供者。 在生产过程中使用了连接到实际数据源的实现方法。 但为了测试模拟对象模拟数据源并确保试验条件永远相同。