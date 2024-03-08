# SW-Lab-2024
First project of the Software Lab Course (404041)

# گزارش پروژه

## شروع پروژه (ساخت مخزن و جدول Kanban)
<div dir="rtl">
پس از آنکه پروژه را در قالب یک ریپوی جدید ایجاد کردیم، تسک‌های لازم را در یک پروژه Kanban به صورت زیر مشخص می‌کنیم.


![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/4538b293-6826-4f74-b3ed-4d748f3074f9)

با کلیک کردن بر روی هر آیتم می‌توان جزئیات آن را مشاهده کرد و ویژگی‌هایی از جمله افراد مسئول (assignees)، اولویت (priority)، تخمین زمان انجام فعالیت، تاریخ شروع، و تاریخ پایان و ... را مشخص کرد. همچنین تاریخچه تغییرات هر آیتم (مثلا جابجا شدن بین ستون‌های backlog و ready و ...) را می‌توانیم در میانه صفحه مشاهده کنیم.

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/1f00d58e-0b39-44b0-9d64-158adf757ac4)

با آماده به شروع شدن آیتم‌ها، از ستون Backlog به ستون Ready منتقل شده و با شروع انجام کار بر روی آنها به ستون In progress انتقال می‌یابند. سپس برای تأیید نهایی به ستون In review رفته و با تأیید PO به ستون Done می‌روند.

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/aa00e36f-a5f0-4742-aefd-ac45b079387d)

همچنین می‌توان آن‌ها را به issueهای پروژه تبدیل کرد. با انجام این کار، در بخش مربوط به issues، این آیتم‌ها به صورت زیر ظاهر می‌شوند:

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/2725f973-3598-4737-a88f-2dfb6acf1f09)

</div>

## ساخت وبسایت تشخیص سرطان و کار با دستورات گیت
<div dir="rtl">
در فایل webpage.html کدهای لازم برای یک سایت دریافت اطلاعات پزشکی و تشخیص سرطان به صورت ساده نوشته شده‌اند. نتیجه نهایی به صورت زیر است:

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/7acc3f02-0e3c-4bd1-841f-b3f515250104)

تعدادی نمونه دستور git استفاده شده در زیر نمایش داده شده است:
```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ touch dummy.py
```
```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        dummy.py

nothing added to commit but untracked files present (use "git add" to track)
```
```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ git add .
```
```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ git commit -m "testing add file"
[main 6c58e14] testing add file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 dummy.py
```


</div>

## ساخت شاخه‌ها و برطرف کردن conflictها
<div dir="rtl">
با استفاده از دستورات زیر می‌توان شاخه‌ها را ایجاد کرد:

```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ git branch initial
```

```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (develop)
$ git branch develop
```

```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (develop)
$ git branch design-webpage
```

با دستور git checkout <branchname> می‌توان بین شاخه‌ها جابجا شد.

```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (main)
$ git checkout develop
Switched to branch 'develop'
```

```
ebrah@DESKTOP-HIUHQ8A MINGW64 ~/My things/university/10th term/SE lab/1/code/SW-Lab-2024 (develop)
$ git branch
  design-webpage
* develop
  initial
  main
```
با مراجعه به تنظیمات مخزن و بخش branches آن، می‌توان از شاخه main محافظت کرد طوری که صرفا از طریق pull request امکان‌پذیر باشد.

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/d3e998bb-41c6-4dfe-b50b-5ee907745bde)

ایجاد conflict در حالتی رخ می‌دهد که در یک شاخه مشخص در حال کار هستیم و هنگام pull request یا merge کردن، مغایرتی با کد در حال کار پیش می‌آید. در این حالت به صورت local این conflict بررسی و برطرف شده سپس به عنوان نتیجه نهایی resolve می‌شود.

برای مثال در تصویر زیر مشاهده می‌شود که در هنگام push کردن با خطا مواجه می‌شویم. زیرا در remote تغییراتی وجود دارد که در local دریافت نشده‌اند. بنابراین ابتدا باید pull انجام شده و سپس با اعمال تغییرات مجددا push انجام شود.

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/3a4dbaff-f1d1-47b7-aaee-327a694a2a67)

حالت دیگر conflict ممکن است هنگامی پیش آید که tip شاخه کنونی عقب‌تر از شاخه معادل آن در remote repository باشد.

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/f9a56edc-3367-42d7-989a-6b2cbd6290ed)

مشابه تصویر زیر ممکن است conflict در هنگام merge کردن رخ دهد که یک راه برطرف کردن آن، استفاده از دستور git rebase --continue است.

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/5cdb84e4-23d3-4425-a302-d16c45f612e0)

همچنین تاریخچه mergeها در بخش کامیت‌ها قابل مشاهده است. 

![image](https://github.com/AmBadAl/SW-Lab-2024/assets/62250863/a3408498-1a27-4122-9a27-24ed6deb76f9)


</div>



## پرسش‌ها

<div dir="rtl">
۱. هر زمان که یک مخزن گیت ساخته می‌شود، همراه آن فولدر .git نیز ساخته می‌شود. گیت تمامی اطلاعات را در این فولدر ذخیره می‌‌کند. با دستور git init این فولدر ایجاد شده و سپس در هنگام پیشرفت پروژه، فایل‌های آن تغییر یا فایل‌های جدیدی به آن اضافه می‌شوند. تعدادی فایل و فولدر در پوشه .git قرار دارند که در ادامه هر کدام از آنها را بررسی می‌کنیم:

<div dir="rtl">
- پوشه objects: در ابتدا صرفا پوشه‌های info و pack در این فولدر قرار دارند اما در مراحل بعدی پروژه دایرکتوری‌های دیگری به آن اضافه می‌شوند. تمامی فایل‌هایی که منتظر کامیت شدن در مخزن هستند، در این پوشه ذخیره می‌شوند. به طور کلی می‌توان گفت که این پوشه database storage است.
</div>

<div dir="rtl">
- پوشه refs: دو زیربخش در این پوشه وجود دارند. دایرکتوری heads که شامل تمامی شاخه‌ها است و دایرکتوری tags که تمامی bookmarkهای تاریخچه را شامل می‌شود.
- در پوشه heads، یک فایل به نام master وجود دارد که شامل یک ارجاع به آخرین کامیت است. با ساخت یک شاخه جدید، یک فایل با همان نام و حاوی ارجاع به آخرین کامیت، ساخته می‌شود.
- در پوشه tags دو نوع مختلف bookmark وجود دارد. اولین نوع آن‌ها به نام lightweight tags شناخته می‌شود و مانند فایل‌های پوشه heads تنها شامل ارجاع به آخرین کامیت است. دومین نوع bookmarkها به نام annotated tag شناخته شده و اطلاعاتی شامل نام tagger، ایمیل، تاریخ، پیام tagging و ... را ذخیره می‌
</div>

<div dir="rtl">
- پوشه info: اطلاعات بیشتری راجع به مخزن گیت را می‌توان در این پوشه مشاهده کرد. یکی از فایل‌های مهم این پوشه، فایل exclude است که در آن تصمیم گرفته می‌شود که کدام الگو باید نادیده گرفته شود. برای تعریف فایل‌ها و فولدرهای نادیده گرفته شده، از فایل .gitignore در پروژه استفاده می‌کنیم.
</div>

<div dir="rtl">
- پوشه hooks: در این پوشه تعدادی تابع از پیش تعریف شده گیت وجود دارند که در بعضی موقعیت‌ها اجرا می‌شوند. یک نمونه از این موقعیت‌ها حالتی است که فرایند کامیت کامل شده باشد.
</div>

<div dir="rtl">
- پوشه hooks: در این پوشه تعدادی تابع از پیش تعریف شده گیت وجود دارند که در بعضی موقعیت‌ها اجرا می‌شوند. یک نمونه از این موقعیت‌ها حالتی است که فرایند کامیت کامل شده باشد.
</div>

<div dir="rtl">
- فایل HEAD: در این فایل یک ارجاع به شاخه فعال وجود دارد. بنابراین با استفاده از این فایل، گیت متوجه می‌شود که کدام شاخه در حال استفاده است.
</div>

<div dir="rtl">
- فایل config: در این فایل اطلاعات پیکربندی مخزن ذخیره می‌شود. می‌توان پیکربندی‌ را به صورت کلی برای تمامی مخازن یا به صورت محلی تعریف کرد. از جمله پیکربندی‌هایی که می‌توان در این فایل مشخص کرد، نام، ایمیل، ویرایشگر، و ... را اشاره کرد.
</div>

<div dir="rtl">
- فایل description: در اینجا می‌توان یک توصیف کوتاه از مخزن ایجاد کرد. البته در صورتی که از gitweb استفاده نکنیم، عملا کاربردی ندارد.
</div>

۲. در version control، یک atomic commit به کامیتی گفته می‌شود که در آن فرض می‌شود تمامی تغییرات ایجاد شده در آن، در یک زمان واحد اتفاق افتاده و به صورت یک واحد منفرد و غیر قابل تقسیم، به مخزن commit می‌شوند. بنابراین همواره امکان دارد که حالت دقیق کد را در هر لحظه از زمان مشاهده کرده و به ما این  امکان را می‌دهد که در صورت نیاز، تغییرات رخ داده در یک کامیت را به عقب برگردانیم.

منظور از atomic pull request نیز این است که ما هر pull request را به صورت یک کامیت واحد (یک آیتم منفرد در تاریخچه پروژه) در نظر گرفته و در صورتی که ایرادی رخ دهد، آن pull request را به صورت کامل revert می‌کنیم.

۳. هر کدام از دستورهای گفته شده را به ترتیب بررسی می‌کنیم:

- دستور fetch: با استفاده از این دستور شاخه‌های موجود در remote repository ذیل مسیر refs/remotes/<remote>/ به‌روزرسانی می‌شوند. انجام این عملیات امن است زیرا هیچگاه شاخه‌های محلی ذیل refs/heads را تغییر نمی‌دهد.
- دستور pull: با استفاده از این دستور شاخه‌های موجود در local repository با نسخه remote آنها به‌روز شده و همچنین دیگر شاخه‌های remote repository به این وسیله به‌روزرسانی می‌شوند.
- دستور merge: با استفاده از این دستور تغییرات یک شاخه با شاخه دیگر ترکیب شده و یک merge commit جدید ایجاد می‌شود. به این وسیله تاریخچه کامیت هر دو شاخه حفظ می‌شود و می‌تواند بیشتر از یک کامیت والد داشته باشد. از این دستور هنگامی استفاده می‌شود که نگه داشتن یک تاریخچه مشخص از شاخه‌ها اهمیت داشته باشد.
- دستور rebase: این دستور کاربردی مشابه با دستور merge دارد با این تفاوت که کل feature branch را به بالای main branch می‌برد. به این وسیله تاریخچه کامیت به صورت خطی حفظ می‌شود. بنابراین feature branch به‌روز می‌شود در حالی که master branch در جای خود باقی می‌ماند. کاربرد این دستور هنگامی است که  می‌خواهیم قبل از merge کردن شاخه‌ها، تغییرات feature branch را با تغییرات اخیر master branch همگام کنیم.
- دستور cherry-pick: در دستور cherry-pick می‌توانیم یک کامیت مشخص را از یک شاخه انتخاب کرده و در یک شاخه دیگر قرار دهیم. هر دو دستور rebase و cherry-pick دستوراتی هستند که کامیت‌های یک شاخه را بر روی شاخه دیگر می‌نویسند با این تفاوت که در rebase، کامیت‌های شاخه کنونی به شاخه دیگر انتقال داده می‌شوند و در cherry-pick، کامیت‌های شاخه دیگر به شاخه کنونی کپی می‌شوند.

۴. هر کدام از دستورهای گفته شده را به ترتیب بررسی می‌کنیم:

- دستور reset: با استفاده از این دستور، می‌توان بین کامیت‌ها جابجا شد و به این وسیله کامیت‌ها را شاخه حذف یا اضافه کرد. انجام این عملیات همواره تاریخچه کامیت را تغییر می‌دهد.
- دستور restore: با استفاده از این دستور، می‌توان فایل‌های داخل working tree را از طریق index یا یک commit دیگر بازیابی کرد. این دستور شاخه را تغییر نمی‌دهد و همچنین می تواند برای بازیابی فایل‌های داخل index یک commit دیگر استفاده شود.
- دستور revert: با این دستور یک commit جدید ایجاد شده که تغییرات دیگر commitها را برمی‌گرداند.
- دستور checkout: این دستور به نوعی چندکاره است طوری که اگر به صورت git checkout <filename> استفاده شود، تغییرات فایل را برمی‌گرداند و هنگامی استفاده می‌شود که می‌خواهیم قبل از stage کردن تغییرات فایل آنها را کنسل کنیم. این دستور عملا کاربرد دستور git restore را دارد. اگر این دستور به صورت git checkout <branchname> استفاده شود، می‌توان بین شاخه‌ها جابجا شد که کاربردی مشابه دستور git switch خواهد داشت.
- دستور switch: این دستور عملا همان دستور git checkout <branchname> است که با استفاده از آن می‌توان بین شاخه‌ها جابجا شد.

۵. به منطقه stage میان workspace و repository، شاخص (index) گفته می‌شود. کاربرد این شاخص آن است که تمامی تغییرات را قبل از کامیت کردن، جمع می‌کند. هنگامی که در حال کار هستیم، تغییرات ایجاد شده در workspace می‌مانند که می‌توانیم آنها را با دستور git add به مرحله stage یا index ببریم. سپس می‌توان با کامیت کردن، تغییرات موجود در index را در مخزن ثبت کنیم.

از دستور git stash هنگامی استفاده می‌کنیم که می‌خواهیم تغییرات داخل working directory کنونی را ذخیره کنیم اما به یک directory دیگر رفته و بعدا دوباره بازگردیم. این دستور تغییرات local را ذخیره کرده و working directory را revert می‌کند طوری که با کامیت HEAD تطابق داشته باشد.

۶. یک snapshot از یک چیز، به معنای حالت کنونی آن چیز در یک نقطه مشخص از زمان است. Commitها به نوعی یک snapshot در زمان هستند زیرا شامل یک اشاره‌گر به root tree بوده و نمایانگر حالت working directory در هر لحظه می‌باشند.

۷. مخزن محلی (local repository)، یک کپی از تاریخچه پروژه و codebase است که در سیستم توسعه دهنده قرار دارد. این مخزن به توسعه دهندگان امکان می‌دهد که به صورت آفلاین کار کنند، ایده‌های مختلف را آزمایش کنند، و workflow خصوصی خود را داشته باشند.

 در مقابل، remote repository به عنوان یک هاب محلی عمل می‌کند که در آن توسعه‌دهندگان می‌توانند با یکدیگر همکاری کنند و کارشان را با دیگران به اشتراک  بگذارند. این نوع مخزن یک پشتیبان برای پروژه فراهم می‌کند و این امکان را برای افراد تیم به وجود می‌آورد که تغییراتشان را با یکدیگر هماهنگ کنند. 

 تفاوت‌های local repository و remote repository به شرح زیر است: 

 - امکان کار آفلاین در یک local repository فراهم است.
 - سرعت کار و انجام عملیات‌های گیت به صورت محلی سریعتر است.
 - توسعه‌دهندگان برای آزمون ویژگی‌های جدید، تغییر کد، و تست کردن رویکردهای متفاوت،آزادی عمل بیشتری برای کار به صورت local دارند.
 - در remote repository، همکاری آسان‌تر است زیرا مخزن remote به عنوان نقطه مرکزی synchronization عمل می‌کند و به افراد تیم اجازه می‌دهد که تغییرات‌شان را با یکدیگر merge کنند.
 - کار کردن با یک remote repository یک backup برای codebase ایجاد می‌کند.
 - در صورتی که دستگاه‌های محلی دچار آسیب شوند، کدهای موجود در remote repository آسیب نمی‌بینند بنابراین امنیت پروژه نیز تأمین می‌شود.


</div>



## منابع
1. https://medium.com/analytics-vidhya/git-part-3-discover-the-git-folder-ca3e828eab3d
2. https://rajrock38.medium.com/what-are-atomic-commits-96d4daa21fd4#:~:text=In%20version%20control%2C%20an%20atomic%20commit%20is%20a%20commit%20that,repository%20as%20a%20single%20unit.
3. https://sapegin.me/blog/rebels-guide-to-pull-requests-commits-code-reviews/#:~:text=It%27s%20easier%20and%20safer%20to,completely%20if%20something%20goes%20wrong.
4. https://stackoverflow.com/questions/292357/what-is-the-difference-between-git-pull-and-git-fetch
5. https://medium.com/@meghatyagi003/git-merge-vs-rebase-vs-cherry-pick-acfa46acb170
6. https://blog.git-init.com/how-to-undo-changes-in-git-using-reset-revert-and-restore/
7. https://stackoverflow.com/questions/57265785/whats-the-difference-between-git-switch-and-git-checkout-branch
8. https://www.geeksforgeeks.org/git-index/
9. https://git-scm.com/docs/git-stash
10. https://stackoverflow.com/questions/4964099/what-is-a-git-snapshot
11. https://levelup.gitconnected.com/git-working-with-local-repository-vs-working-with-remote-repository-b2ec00df9a2e