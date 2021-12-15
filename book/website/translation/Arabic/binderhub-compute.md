(r-binderhub-compute)=
# الموارد الحاسوبية

BinderHub محايد للسحابة، مما يعني أنه يمكن نشره على أي منصة سحابية. لذلك، الحد الأدنى من المتطلبات هو الاشتراك في منصة سحابية من اختيارك.

في الواقع، BinderHub لا يعتمد على استضافة السحابة على الإطلاق ويمكن نشرها في نظام حاسوبي على أساس فرعي.

## Kubernetes

[كوبرنيت](https://kubernetes.io/) هو نظام للتشغيل الآلي للنشر، والتوسع (تصنع أكثر أو أقل من النسخ)، وإدارة الحاويات عبر مجموعة حاسوبية (لا ينبغي أن تكون قائمة على السحب). يستخدم BinderHub كوبرنيتس لإدارة الموارد التي يطلبها مستخدمو خدمة Binder ولدعم الأدوات التي تبني البيئات.

## مرحبا

[Helm](https://helm.sh/) هو مدير حزمة لكوبرنيت. تأتي الحزم في شكل مخططات ** التي هي مجموعة من التعليمات للنشر، قم بترقية وإدارة التطبيقات التي تعمل على مجموعة كوبيرنيتس. ويمكنها أن تجعل تركيب وإدارة تطبيقات كوبرنيتس أسهل بكثير، ويمكن نشر مخططات محددة للمشاريع على الإنترنت. على سبيل المثال، الرسم البياني لـ BinderHub متاح [هنا](https://jupyterhub.github.io/helm-chart/#development-releases-binderhub).

## مستودع

[repo2docker](https://repo2docker.readthedocs.io/en/latest/?badge=latest) هي أداة تبني تلقائياً صورة Docker من مستودع التعليمات البرمجية إذا تم منح ملف الإعداد. سوف تحتوي صورة Docker على كل الكود والبيانات والموارد المدرجة في المستودع. سيتم أيضا تثبيت جميع البرامج المطلوبة لتشغيل الكود مسبقاً من ملف الإعداد.

## JupyterHub

[JupyterHub](https://jupyter.org/hub) هو خادم متعدد المستخدمين لمذكرات المشتري والحاويات على حد سواء. في سياق بيندر، الدور الرئيسي لـ JupyterHub، هو توصيل متصفح المستخدم بمثيل BinderHub الذي يعمل على مجموعة كوبرنيتس. ومع ذلك، يمكن زيادة تخصيص JupyterHub لتوفير قدر أكبر من السيطرة على تشغيل BinderHub.

يمكن التفكير في BinderHub كطبقة رقيقة تجلس فوق repo2docker و JupyterHub، بتنسيق تفاعلاتهم وحل عناوين URLs.

## ماذا يحدث عندما يتم النقر على رابط بيندر؟

1. يتم حل الرابط للمستودع بواسطة BinderHub.
2. BinderHub يبحث عن صورة Docker المتعلقة بالمرجع المقدم (على سبيل المثال، git commit hash، الفرع أو العلامة).
3. **إذا لم يتم العثور على صورة Docker**، BinderHub يطلب موارد من مجموعة Kubernetes لتشغيل repo2docker للقيام بما يلي:
   - إحضار المستودع،
   - بناء صورة Docker تحتوي على البرنامج المطلوب في ملف الإعداد،
   - اضغط هذه الصورة إلى سجل Docker.
4. BinderHub يرسل صورة Docker إلى JupyterHub.
5. يطلب JupyterHub موارد من مجموعة Kbernetes لخدمة صورة Docker.
6. يوصل JupyterHub متصفح المستخدم ببيئة Docker قيد التشغيل.
7. يقوم JupyterHub بمراقبة الحاوية لنشاطها ويدمرها بعد فترة من عدم النشاط.