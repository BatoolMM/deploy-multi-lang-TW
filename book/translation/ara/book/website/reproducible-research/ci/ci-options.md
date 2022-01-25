(r-ci-Options) =
# ما هو الدمج المستمر؟

الدمج المستمر هو ممارسة إدماج التغييرات التي يجريها الأفراد في مشروع في صلب المشروع، الإصدار المشترك بشكل متكرر (عادة عدة مرات في اليوم). تستخدم برمجيات CI أيضا عادة لتحديد أي تضارب أو خلل يتم إدخاله من خلال التغييرات، وبذلك يتم العثور عليها وإصلاحها في وقت مبكر، مما يقلل إلى أدنى حد من الجهد اللازم للقيام بذلك. كما أن إجراء الاختبارات بانتظام ينقذ البشر من الحاجة إلى القيام بذلك يدويا. من خلال جعل المستخدمين على علم بالأخطاء في أقرب وقت ممكن الباحثين (إذا كان المشروع مشروع بحث) لا يهدر الكثير من الوقت للقيام بعمل قد يحتاج إلى إبعاده، وهو ما قد يكون عليه الحال إذا كانت الاختبارات تجري بشكل نادر ويتم إنتاج النتائج باستخدام رمز خاطئ.

ويتطلب هذا الفصل فهما قويا لمراقبة النسخ. والمفاهيم الرئيسية التي يجب أن تتذكروها هي:

- كيف يمكن استخدامه لتمكين الناس الذين يتعاونون في مشروع واحد من الجمع بين عملهم عن طريق الدمج
- باء - ما هي الصراعات المدمجة والصعوبات التي يمكن أن تطرحها
- ما هو GitHub وكيفية استخدامه

باختصار، إذا كانت مجموعة من الباحثين تتعاون في مشروع ما، فمن الممارسات الجيدة أن يستخدموا التحكم في الإصدار لتتبع تغيراتهم مع مرور الوقت. ويجمع بين عملهم بانتظام. وإذا لم يجمع هؤلاء بين عملهم (المتكامل) بصورة منتظمة، فمن المرجح أن يكون من الصعب جدا عندما يأتون إلى ذلك لأن الناس المختلفين قد أدخلوا تغييرات متناقضة.

التكامل المستمر ممارسة لتطوير البرمجيات حيث يقوم أعضاء فريق ما بدمج عملهم بصورة متواترة. بدلاً من القيام بعمل بمعزل عن التغييرات الكبيرة ودمجها في تغييرات كبيرة على فترات غير متواترة. وعادة ما يندمج كل شخص يوميا على الأقل في جزر كوك. يتم التحقق من كل تكامل من خلال بناء آلي (يتضمن عادة الاختبارات) للكشف عن أخطاء التكامل في أسرع وقت ممكن.

والفكرة هي التقليل إلى أدنى حد من تكلفة التكامل بجعله موضع نظر مبكر. ويمكن للباحثين أن يكتشفوا تناقضات على الحدود بين الشفرة الجديدة والشفرة الموجودة في وقت مبكر، بينما لا يزال من السهل نسبياً التوفيق بينها. وبمجرد حل الصراع، يمكن أن يستمر العمل بثقة بأن المدونة الجديدة تفي بمتطلبات الخلاف القائم حاليا. والهدف هو بناء برمجيات أكثر صحة عن طريق تطوير واختبار زيادات أصغر. ويجد العديد من الأفرقة أن هذا النهج يؤدي إلى الحد بدرجة كبيرة من مشاكل الإدماج ويسمح للفريق بأن يتطور بسرعة أكبر.

وغالبا ما لا يوفر إدماج الشفرة في حد ذاته أي ضمانات بشأن نوعية الشفرة الجديدة أو الوظيفة الجديدة. وهذا يقودنا إلى الجانب الثاني من مبادرة كوت ديفوار. عندما يدمج المطور التعليمات البرمجية في المستودع الرئيسي، تقوم العمليات الآلية بإنشاء نسخة عمل من المشروع. بعد ذلك، يتم تشغيل حزم الاختبار ضد المبنى الجديد للتحقق مما إذا كان قد تم إدخال أي أخطاء. إذا فشلت مرحلة البناء أو الاختبار، يتم تنبيه الفريق بحيث يمكنه العمل على حل المشكلة. من الأسهل إصلاح خطأ في شيء كتبته قبل بضع دقائق من شيء كتبته أمس (أو الأسبوع الماضي) أو الشهر الماضي).

من خلال ضمان بناء التعليمات البرمجية الخاصة بك واختبارها بانتظام، تساعد CI الباحثين على إثبات أن التعليمات البرمجية الخاصة بهم تقوم بما يدعي أنها تقوم به، وأنه يفعل ذلك بشكل صحيح. وعادة ما تسمح خوادم التكامل المستمرة أيضا بتشغيل وظائف البناء والاختبار في أوقات محددة. بحيث يمكن عمل [وظيفة كرون](https://en.wikipedia.org/wiki/Cron)، البناء الليلي والاختبار، بالإضافة إلى وظيفة البناء والاختبار التي تجري بناء على الطلب.


## ما هي الخيارات لمقدمي خدمات CI؟

وهناك العديد من مقدمي خدمات مبادرة CI، مثل إجراءات GitHub وTravis CI. ولكل من هذه الخدمات مزاياها ومساوئها الخاصة. في هذا القسم نقدم نظرة عامة موجزة مع روابط للأمثلة لمساعدتك على اختيار الأنسب لك.

 - [إجراءات GitHub](https://help.github.com/en/actions)، للحصول على بعض الأمثلة ، انظر [لغة وأدلة الإطار](https://help.github.com/en/actions/language-and-framework-guides) و [هذا البرنامج التعليمي](https://github.com/NLESC-JCER/ci_for_science#-github-actions).
 - [دائرة CI](https://circleci.com/)، لبعض الأمثلة ، انظر [هنا](https://circleci.com/docs/2.0/project-walkthrough/) و [هنا](https://circleci.com/docs/2.0/hello-world/).
 - [GitLab CI](https://docs.gitlab.com/ee/ci/)، لبعض الأمثلة [أمثلة GitLab CI](https://docs.gitlab.com/ee/ci/examples/README.html) و [هذا البرنامج التعليمي](https://github.com/NLESC-JCER/ci_for_science#-gitlab-ci).
 - [أنابيب آزور](https://azure.microsoft.com/en-us/services/devops/pipelines/)، لبعض الأمثلة ، انظر [صفحة دعم النظام الإيكولوجي](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/?view=azure-devops) و [هذا البرنامج التعليمي](https://github.com/trallard/ci-research).
 - [Jenkins](https://www.jenkins.io/)، لبعض الأمثلة انظر [هذا البرنامج التعليمي](https://www.jenkins.io/doc/tutorials/)
 - [Travis CI](https://travis-ci.com/)، لبعض الأمثلة [دروس ترافيس](https://docs.travis-ci.com/user/tutorial/).

يمكن العثور على قائمة أكثر شمولاً من مقدمي خدمات CI [هنا](https://www.software.ac.uk/resources/guides/hosted-continuous-integration).