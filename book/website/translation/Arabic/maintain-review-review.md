(استعراض - صيانة) =
# استعراض المساهمات

## عملية الاستعراض
وفي أي مشروع أو ديوان، يجب استعراض مجموعة من التغييرات قبل دمجها في المستودع الرئيسي. إذا كان العديد من الناس يملكون المشروع بصورة مشتركة، عملية المراجعة التي تتم بواسطة [مهمة مراجعة الرموز](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/managing-code-review-assignment-for-your-team) التي يتم فيها تعيين بعض أعضاء الفريق لهذه المهمة. غالباً ما يقترح المستعرضون تلقائياً على طلبات سحب GitHub استناداً إلى نشاط مماثل يقوم به أعضاء آخرون على نفس الملفات أو مختلف في المشروع. غير أن مديري المشاريع كثيرا ما يطلبون من المشرفين الآخرين استعراض طلب سحب معين على أساس توافرهم أو استعدادهم أو خبرتهم.

يمكن للمشرفين المعينين أو الراغبين في مراجعة طلب السحب عن طريق التحقق من [التغييرات محليا](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/checking-out-pull-requests-locally) أو على مستودع الإنترنت واقتراح التغييرات المطلوبة. وعند اكتمال عملية الاستعراض، يمكن الموافقة على الاستعراضات دون أي تغيير، أو [مع التغييرات المطلوبة](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/approving-a-pull-request-with-required-reviews) أو [تم رفضها](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/dismissing-a-pull-request-review) وفقا لجودة المساهمة.

## المبادئ التوجيهية لعملية الاستعراض والصيانة
وفيما يتعلق بالتعاون في مشروع GitHub، من المهم اتباع مبدأ توجيهي محدد يتضمن أفضل الممارسات للإبقاء على مشروع معين. ويمكن تنفيذ عملية الصيانة بسلاسة بمساعدة الجهات التالية:

1. *توثيق العملية*: التوثيق الشامل حول كيفية بدء المساهمين بالمشروع وكيف يمكنهم تقديم مساهمات ذات مغزى هو الخطوة الأولى التي يجب اتخاذها مع الحفاظ على مشروع مفتوح المصدر. هذه التفاصيل يجب أن تلقي الضوء على كل شيء عن المشروع، لماذا تم إنشاؤه في المقام الأول. من يحافظ على المشروع، ما تبدو عليه الثقافة المجتمعية، ومن يستطيع تقديم الإرشاد للمساهمين الجدد.

وتشكل هذه الوثائق الثلاث بداية طيبة نحو وضع هذه الوثائق:
- يجب أن يحتوي المشروع على {ref}`README. (د) الملف<pd-project-repo-readme>` الذي يوفر التفاصيل والروابط الهامة إلى الموارد التي يجب أن يعرف المرء أنه يصبح عضوا في المشروع.
- يجب توفير مدونة قواعد سلوك (أنظر _طريق اللحم_ [مدونة قواعد السلوك](https://github.com/alan-turing-institute/the-turing-way/blob/main/CODE_OF_CONDUCT.md)في كل مشروع لتهيئة بيئة ترحيب وآمنة لأعضاء المجتمع أثناء تعاونهم.
- مبدأ توجيهي جيد الكتابة للإسهام (أنظر _طريق تورينج_ [ملف المساهمة](https://github.com/alan-turing-institute/the-turing-way/blob/main/CONTRIBUTING.md)) مهم للغاية عندما يتم التعاون عن بعد في أي مشروع لضمان التواصل الواضح بين المساهمين و المشرفين.

2. *الاتصال الفعال*: المحادثات المتعلقة بأي مساهمة يمكن إعلانها للآخرين للانضمام إلى المناقشة أثناء العمل على الميزات والأفكار الصغيرة. وسيشمل ذلك عددا أكبر من الناس وسيكفل الشفافية في أعمال المصدر المفتوح. من المهم كتابة رسائل وتعليقات على المشكلة وسحب الطلبات، بطريقة واضحة وسهلة الفهم أثناء إجراء استعراض لمساعدة المساهمين على فهم المتطلبات حتى يتمكنوا من الالتزام على نحو أفضل بطلبات السحب الخاصة بهم. ومن الأفضل ذكر الروابط الهامة في الرسائل إذا لزم الأمر.

3. *المساهمات الموجهة*: دور المشرف هو جعل المساهمة عملية سهلة قدر الإمكان. ويمكن أن تكون المساهمات المفتوحة المصدر مصدر تخويف لكثير من المساهمين الجدد. ومن شأن توجيه الناس بإجراء محادثات ودية ومشجعة أن يجعل عملية بدء المساهمين الجدد مريحة. ومن الأفضل إيجاد مسائل وصفية لحلها. ولتقديم مساهمات كبيرة، من الأفضل إيجاد مسائل مختلفة قبل حلها بطلبات الجذب. وسيساعد وضع العلامات على المشكلات وطلبات السحب في الحصول على المزيد من المساهمين في مختلف المهام ذات المتطلبات المختلفة للمهارات. تسمية المشكلات التي تبدو سهلة ب ["المشكلة الأولى الجيدة"](https://help.github.com/en/github/building-a-strong-community/encouraging-helpful-contributions-to-your-project-with-labels) سيساعد المساهمين الجدد على التقاط المهام السهلة مثل التغييرات الطفيفة في التعليمات البرمجية والمحتوى، إصلاح الأخطاء والتوكيو ومشاكل التصميم الصغيرة.

4. *الحفاظ على طلبات السحب*: صيانة طلبات السحب الموجودة بالفعل في المشروع ينطوي على وضع علامة عليها، مراجعتهم وتغيير مراحلهم ودمجهم وإغلاقهم. ويمكن الحفاظ على طلبات السحب عن طريق إعطاء المراجعة الصحيحة في الوقت المناسب. على GitHub هناك طرق مختلفة لتقديم ردود الفعل أثناء المراجعة مثل تقديم ردود الفعل كتعليق على طلب السحب اقتراح تغييرات أثناء المراجعة، اقتراح التغييرات مباشرة في فرع المساهمين أو مناقشة طلب السحب كيف يمكن تحسين المساهمات (أنظر [مشاركة GitHub للحصول على التفاصيل](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-request-reviews)). ويجوز للقائمين على الصيانة أن يبلغوا عن جدول زمني يقومون خلاله باستعراض ودمج طلبات السحب من أجل مشروع نشط، على سبيل المثال أسبوع واحد. ويمكن تغيير العلامات مع مرور الوقت والمراحل لتعكس على نحو صحيح حالة سمة قيد التطوير.

5. *الاعتراف بعمل الآخرين واحترام الوقت*: الترحيب بالأشخاص الذين يساهمون في المشروع هو أحد مفاتيح نجاح المشروع التعاوني. وكلما قدمت مساهمة ذات مغزى ودمجت في العلاقات العامة، ينبغي للقائمين على الصيانة أن يعترفوا بها. رسالة صغيرة تقول "شكراً" غالباً ما تكون كافية، خاصة بالنسبة للمبتدئين في الأماكن المفتوحة المصدر. إنها دائما إيماءة جيدة لمنح الائتمان للمساهمين في المصدر المفتوح من خلال إضافتهم إلى قائمة المساهمين. وأفضل طريقة للقيام بذلك هي إنشاء ملف مخصص يُذكر فيه جميع المساهمين بمساهماتهم في المشاريع. وإذا كان المساهمون في المشاريع موجودين في أنحاء مختلفة من العالم، ينبغي أن يحترموا وقتهم وأن يضعوا جداول أعمالهم وفقا لذلك. وفي حالة عدم تمكن شخص ما من مناقشة الأفكار بسبب جدوله الزمني، ينبغي للقائمين على الصيانة والمساهمين أن يحاولوا التعاون قدر الإمكان. ومن الممارسات الجيدة أيضا أن نطلب بنشاط من المساهمين الذين يشغلون كثيرا أن يقوموا باستراحة وأن يعودوا في وقت لاحق أو أن يشركوا آخرين من المجتمع المحلي أن يتبعوا مساهماتهم الجارية.