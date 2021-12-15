(rr-testing-unitist)=
# 单元测试

单元测试负责以单独和目标明确的方式测试单项代码要素。 个别功能和班级的功能自行测试。 其目的是验证软件的每个单位是否按设计行事。 一个单位是任何软件中最小的可蒸发部分。 在程序性方案拟订中，一个单位可以是一个单独的方案、职能或程序。 在面向对象的编程中，最小单位通常是一种方法。 它通常有一个或几个投入，通常只有一个产出。 任何外部依赖应该替换为 stub或模拟实现来使测试完全侧重于有关代码。

单元测试对于测试单个代码组件是否正确至关重要，以便在将其置于更复杂的环境之前能否做到内部一致和准确。 测试的有限范围和从属性的移除使得更容易寻找任何缺陷的原因。 现在也是检验各种投入和代码分支的最佳时机，这些分支可能很难在以后被撞击。 例如，系统测试常常耗费时间运行，通过一个超过几个条件语句的代码对每个可能的路径进行系统测试可能不切实际。 部队测试规模较小，速度较快，因此更切合实际地涵盖所有可能的案件。

在进行任何烟雾试验之后，单位试验往往是进行任何更改时进行的第一次试验。

## 单位测试的惠益

如果研究人员改变一部代码或如何运行，他们如何能够确保这样做没有破坏任何东西？ 他们可以进行几次测试，但没有单独测试每一部小代码，他们如何确定？ 单元测试为研究人员提供了确定性，使他们能够在修改和维持其守则时有信心。

这是一个小的例子。 说一个研究人员有一个小的功能，可以做一个简单的事(这里仅有一个简短的线)。 在这个示例中，这将会将一个数字提升到第5功率：

```
def take_fifth_power(x):
  results = x * x * x * x * x
  返回结果
```

此函数的单元测试看起来像这样：
```
def test_take_fifth_power():
  stake take_fifth_power(1.5) == 7.59375
```

所以它检查输出正确的结果是给定的输入。 如果不是测试将失败。 研究人员继续开展工作。 在其中间，他们决定提升这个功能，乘以这个数字的五倍是一种有点巡洋溢。 他们将 `结果= x * x * x * x * x * x * x` 行更改为 `结果= x * 5`。 下次他们进行单位测试时，这次测试将失败，因为他们刚刚犯了错误。 也许他们需要咖啡，也许他们的手指被滑动，也许他们的椰子用神经舞击中他们的耳朵，分散了他们的注意力。 但当他们正在提升这个函数时，他们应该写下 `结果 = x ** 5` *不是* `结果 = x * 5`。 失败的测试会揭示错误，它可以迅速纠正。 如果没有发现这样的错误，可能导致研究人员工作出现严重错误。

因此，单元测试导致更可靠的代码，但也有其他好处。 首先，它使漏洞更容易被发现，从而使发展速度更快。 测试大型代码块的较大规模测试(虽然仍然有用)，其缺点是如果它们失败，很难确定bug的来源。 因为单位测试是根据其定义测试的少量代码， 它们帮助开发者找到错误的原因比更高层次的测试或代码更快，根本没有测试。 单元测试还使修复bug更快和更容易，因为它们能够较早地发现bug，而其影响仅限于小型单位。 如果不及早通过单元测试检测到 bug ，则可能需要很长时间才能发现它们。 影响基于错误代码的后续工作。 这意味着更多的代码面临风险，而修复错误更加耗时。

单元测试的另一个主要好处是，它有力地激励研究人员编写模块化代码，因为模块化代码更容易编写单元测试。 模块化代码是将代码分解成可管理的块，每个块都能完成简单的任务。 要做到这一点，典型的办法是将守则分成各种职能和一组职能。 与之相反，一个只是产生结果的一系列漫长连续行的脚本是非模块。

模块化代码也更容易重新使用。 例如， 如果研究人员有个人功能做一些有用的东西，在未来的项目中，他们需要再次做这件事。 复制或导入函数是微不足道的。 相反， 如果做这个有用的东西的代码与大量的其他代码绑在一起长脚本中，那么将它分离出来再使用就更难了。

## 单元测试提示

- 许多测试框架都有专门用于编写和运行单位测试的工具。
- 将发展环境与试验环境隔离开来。
- 写独立的测试案例。 例如，如果一个单位A利用另一单位B提供的结果， 你应该用 [测试双倍](#Use_test_doubles_stubs_mocking_where_appropriate)测试单元A ，而不是实际调用单元B。 如果您不这样做，您的测试失败可能是由于A *或* B的错误造成的。 使错误更难追踪。
- 目标是通过一个单元覆盖所有路径。 特别注意循环条件。
- 除了撰写案例以核实行为之外，还编写案例以确保守则的执行。 例如，如果一个函数应该添加两个数字，运行需要几分钟，这可能会有问题。
- 如果您在代码中发现缺陷，请写一个测试以暴露它。 为什么？ 首先，如果你不适当地修复缺陷，你以后将能够抓住缺陷。 第二，您的测试套件现在更加全面。 第三，您很可能太迟无法在您已经修复缺陷后写入测试。 说代码有一个简单的功能，可以将人们归类为成年人或儿童：

```
def adult_or_child(年龄)：

  # 如果年龄大于或等于18岁，则将他们分类为成年人
  如果年龄 >= 18：
    person_status = '成年人'

  # 如果一个人不是成年人分类他们为孩子
  其他：
    person_status = 'Child'

  return person_status
```

并且说这个代码有一个像这样的单元测试：

```
def test_adult_or_child()：

  # 测试一个成年人被正确分类为成人
  adult_or_child(22) == '成年'

  # 测试一个儿童被正确分类为儿童
  saving adult_or_child(5) == 'Child'

  return
```

没有测试的代码有问题：如果提供了负年龄，它将很高兴地将此人归类为儿童，尽管不可能有负年龄。 代码应该在这个情况下出现错误。

一旦解决了错误：
```
def adult_or_child(年龄)：

# 检查年龄有效
如果年龄 < 0：
  提升值错误， '不可能有一个负年龄'

# 如果年龄大于或等于18岁，则将他们归类为成年人
如果年龄 >= 18：
  person_status = '成年人'

# 如果此人不是成年人，则将他们归类为儿童
其他：
  person_status = 'Child'

return person_status
```

继续并写一个测试以确保代码中的未来更改不会导致它再次发生：
```
def test_adult_or_child()：

#测试一个成年人被正确归类为成年人
adult_or_child(22) == '成年人'

# 测试一个儿童被正确归类为儿童
断定成年人或儿童(5) == '儿童'

# 测试提供无效年龄导致错误
aises(值错误)：
    adult_or_child(-10)
```