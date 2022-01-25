(rr-ci-practices)=
# 最佳做法和建议

## 小的、迭代性的更改

在实行持续一体化时，最重要的做法之一是鼓励项目成员作出小的改动并作出小的改动。 小的变化最大限度地减少了整合后的问题裁剪的可能性和影响，从而最大限度地减少了整合的时间和努力成本。

## 基于Trunk的开发

在以trunk为基础的开发过程中，将在仓库的主要分支机构进行工作，或经常每隔一段时间将其合并到共享仓库中。 允许使用寿命短的功能分支，只要它们代表小的变化并尽快进行合并。

以三元论为基础的发展的目的是避免违反上文讨论的小规模反复变革概念的大规模承诺。 对等点早期就可以使用代码，以便当冲突的范围很小时能够解决冲突。

## 保持建筑和测试阶段

由于必须经常进行构建和测试步骤，因此必须精简这些程序，以尽量减少花在这些步骤上的时间。 建筑时间的增加应被视为一个主要问题，因为每个建筑物都会被踢出，这使影响更加复杂。

在可能的情况下，并行运行试验套件的不同部分可以帮助更快地通过管道移动构建。 还应注意确保每一类测试的比例是合理的。 单元测试通常非常快，维修间接费用也很少。 与此相反，自动化系统或验收测试往往很复杂，容易发生故障。 为此，在很大程度上依靠单位测试往往是一个好主意。 进行相当数量的集成测试，然后回到以后更复杂测试的数量。

## 计算费用

某些软件需要大量的计算资源才能构建和/或运行。 例子包括天气和气候模型。 这可能使持续整合的使用不切实际，因为测试要么需要太长时间，要么使用太多的资源。 因此，需要找到一种折衷办法，在测试不完整的风险与可用的开发过程之间取得平衡。

一种办法是采用不同程度的测试，根据变化情况需要不同的子组。 在每一种情况下都可以使用一个共同的广泛分组，并且可以援引其他分组来更详细地测试某些领域。 这为测试过程引入了判断因素，但可以成功应用。

## 依赖关系跟踪

应定期检查依赖关系更新。 它可以节省很多时间，避免因为代码依赖于过时的功能。 像 [David](https://david-dm.org/) 这样的服务可以用于依赖管理。

## 整个输油管线的一致性情况

项目应在管道开始时建立一次，由此产生的软件应储存起来，供以后的程序使用，不再重建。 在每个阶段使用完全相同的手工艺品， 您可以肯定您不会因为不同的构建工具而引入不一致之处。