
(r-code-reuse-detail)=
# توصيات مفصلة لإعادة استخدام البرمجة

تأكد من أنك (أو شخص آخر) تستطيع إعادة استخدام التعليمات البرمجية الخاصة بك للقيام بنفس الشيء الذي فعلته بالضبط. يحتوي هذا القسم على قائمة فحص بسيطة للتوصيات لجعل برنامجك أكثر قابلية للاستخدام. ويتضمن هذا الفرع شرحا أكثر تعمقا لكل توصية من هذه التوصيات، مع مؤشرات للأجزاء الأخرى ذات الصلة من هذا الدليل.

## التوصيات المتكررة

في هذه المرحلة، قد لا تحتاج حتى إلى أن تكون قادراً على فتح التعليمات البرمجية وقراءتها، أنت فقط تريد التأكد من أنك تستطيع إعادة تشغيل جميع الخطوات المطلوبة والحصول على نفس النتائج التي لديك.

### 1. تأكد من أنك تستطيع العثور عليه (في الفضاء)

يجب تخزين التعليمات البرمجية الخاصة بك علنا ومشاركتها مع المتعاونين. ولديها معرف ثابت فريد حتى يتمكن الجميع من العثور عليه والوصول إليه.

**انظر أيضًا**: {ref}`rr-vcs`

### 2. تأكد من أنك تستطيع العثور عليها (في الوقت)

من الناحية المثالية يتم توثيق التطور الزمني للشفرة مع التحكم في الإصدار. هذا يسمح لك باسترداد نسخة محددة من الماضي.

**انظر أيضًا**: {ref}`rr-vcs`

### 3. تأكد من أنك تستطيع تنفيذ نفس سلسلة العمليات

وغالبا ما يكون الإنسان الذي أنشأ البيئة هو أيضا الشخص الذي كتب الكود والشخص الذي يعرف بالضبط الترتيب اللازم للخطوات اللازمة للتمكن من إعادة تشغيل الكود واستنساخ النتائج. ومن المؤكد أن هذا يمكن توثيقه بعناية لكي يقوم به إنسان آخر مرة أخرى.

**انظر أيضًا**: [درس CodeRefinery في البحث القابل للتكرار](https://coderefinery.github.io/reproducible-research/)

### 4. تأكد من أن بيئتكم وتسلسل عملياتكم قويين ولا حاجة إلى أي إنسان لتكرار ما تم إنجازه

لا تريد أن تعتمد على البشر. إنهم يميلون إلى ارتكاب أخطاء حتى وإن لم تكن لديهم نوايا سيئة. لذلك تريد أن تكون بيئتك سكريبت وأن يعاد إنشاؤها عند الحاجة، وتريد أن يتم تشغيل تسلسل العمليات الخاص بك بواسطة برنامج نصي لخط الأنابيب الذي يلغي معا كل تسلسل الخطوات. ومن الآثار الجانبية اللطيفة لخطي تسلسل العمليات أن ذلك يمكن أن يكون في كثير من الأحيان بمثابة توثيق للخطوات المتخذة.

**انظر أيضًا**: {ref}`rr-renv-options`

### 5. رخصة الرمز الخاص بك

تأكد من إرفاق ترخيص بالكود الخاص بك وتحديد كيف تريد الاستشهاد به عندما يقوم الناس بإعادة استخدامه. فكر في استخدام رخصة مسموح بها تسمح بإعادة الاستخدام. كما يجب عليك اختيار ترخيص متوافق مع تراخيص المكتبات أو الحزم التي يعتمد عليها برنامجك.

**انظر أيضًا**: {ref}`rr-licensing-software`، {ref}`rr-licensing-software-permissive`، {ref}`rr-licensing-compatibility`

### 6. تأكد من أنه قابل للكابل

تأكد من تحديد كيف تريد الاستشهاد بها عندما يقوم الناس بإعادة استخدامها.

**انظر أيضا**: {ref}`cm-citable-cite-software`

### 7. تضمين البيانات الضرورية

إذا كان البرنامج يعتمد على أي نوع من البيانات، يجب أن تكون البيانات متاحة

**انظر أيضًا**: {ref}`rr-rdm-data`

## توصيات قابلة لإعادة التشغيل

تأكد من أنك (أو غيرها) تستطيع إعادة استخدامه للقيام بالشيء الذي فعلته، ولكن مع بيانات مختلفة/معلمات مختلفة

### 1. إزالة البتات المشفرة وجعل الوحدة النمطية مرنة
لا تريد الحصول على تفاصيل محددة لبيانات أو معلمات التحليل الخاصة بك مشفرة في الكود. إذا كان شيء ما يمكن أن يصبح دالة قابلة لإعادة الاستخدام، فاصله عن المعلمات المشفرة وتحويله إلى شيء (إعادة استخدامه) بمفرده. اجعل الوحدات النقية: مع إعطاء نفس المدخلات، دالة نقية دائما ترجع نفس القيمة. بدلاً من تحديد مسارات الملفات داخل البرامج النصية ، فكر في تمريرها كحجج سطر الأوامر لنصوص أكثر قابلية للتنقل وعامة و قابلة لإعادة الاستخدام.

**راجع أيضًا**: [درس تطوير كود مصنع الكود الموحد](https://cicero.xyz/v3/remark/0.14.0/github.com/coderefinery/modular-code-development/master/talk.md/#1)

### 2. اختبر أن الوحدات التي قمت بإنشائها يمكن أن تأخذ أنواعا مختلفة من بيانات الإدخال أو المعلمات
قد لا تعرف بعد كيف سيتم إعادة استخدام التعليمات البرمجية الخاصة بك في المستقبل، ولكن يمكنك منع كيفية عدم استخدامه إذا كنت تستطيع اختبار أي المعلمات مسموح بها.

**انظر أيضًا**: [درس مصفاة CodeRefinery في الاختبار الآلي](https://coderefinery.github.io/testing/motivation/)

### 3. تحويل الوحدات إلى حزمة/صندوق أدوات
فصل المزيد من التفاصيل الخاصة بمشروعك مع الأجزاء التي يمكن إعادة استخدامها في مشاريعك الأخرى أو من قبل أشخاص آخرين.

**انظر أيضًا**: {ref}`rr-renv-pack`، [برنامج التغليف](https://scicomp.aalto.fi/scicomp/packaging-software/)، [تغليف البرمجيات في بايثون](https://aaltoscicomp.github.io/python-for-scicomp/packaging/)

## التوصيات المحمولة
وتشير إمكانية النقل إلى القدرة على نقل البرمجيات إلى بيئة جديدة. ويمكن أن يشير ذلك إلى آلة مطابقة (ولكن ليس ذاتها)، ولكن يمكن أن يشير أيضا إلى هندسة جديدة للمعدات، ونظام تشغيلي وما إلى ذلك. وكلاهما مهم لإعادة استخدام البرمجيات.

### 1. تأكد من أنه يمكنك إعادة إنشاء البيئة حيث كانت تعيش
فالبيئة هي لقطة هشة في الوقت المناسب تصاحب المدونة بصمت. ويمكن أن يشمل الإنسان الذي قام بتشغيل البرمجيات، والخطوات التي قام بها الإنسان لإعداد البيانات، الأجهزة وأجهزة التشغيل والمكتبات والحزم الخارجية/صناديق الأدوات/التبعيات. وكل ذلك يمكن توثيقه بعناية لكي يعيد إنسان آخر القيام بنفس الخطوات بالضبط.

**انظر أيضًا**: {ref}`rr-renv`

## التوصيات الموسعة والقابلة للتعديل
تأكد من أن الآخرين يمكنهم البناء على التعليمات البرمجية الخاصة بك لتوسيع نطاقها وتحسينها.

### 2. تأكد من أن الكود الخاص بك مقروء من قبل البشر
غالباً ما يدفع المزيد لكتابة التعليمات البرمجية للبشر الآخرين حتى يتمكنوا من قراءتها (بما في ذلك نفسك المستقبلي). لا يكون النيل المشفر الذي يحتوي على أسماء متغيرة غامضة أسرع أو أكثر كفاءة من تقسيم الخطوط الملاحية الواحدة إلى خطوات متعددة مع أسماء متغيرات مقروءة تكون منطقية. وعلاوة على ذلك، فإن استخدام اتفاقيات الترميز سيساعد القراء الآخرين.

**راجع أيضًا**: {ref}`rr-code-style-and-formatting`، {ref}`rrr-code-quality-advantage`

### 3. تأكد من وجود التعليقات
كتابة التعليقات قبل كتابة الرمز الفعلي. تخيل أنه يمكن لشخص ما قراءة التعليقات وتخطي جميع أجزاء التعليمات البرمجية بين التعليقات والحصول على صورة كاملة لما يحدث كما لو أنهم قرأوا الكود بأكمله.