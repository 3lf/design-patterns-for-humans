<div dir="rtl">

![Design Patterns For Humans](images/poster.png)

---

<h3 dir="rtl" align="center">
🎉 توضیح ساده دیزاین پترن‌ها ! 🎉
</h3>

<p dir="rtl" align="center">
فهمیدن دیزاین پترن‌ها از اون موضوع‌هاست که ذهن رو به چالش می‌کشه.
 اینجا سعی می‌کنم با مثال‌های ساده از دنیای واقعی و دنیای کد، راحت تو ذهنت جا بندازمش.
</p>

---

منبع اصلی این ریپازیتوری [این](https://github.com/rommel-sunga/design-patterns-for-humans-python) ریپازیتوری هست که
خودش نسخه پایتونیزه شده [این](https://github.com/kamranahmedse/design-patterns-for-humans) ریپازیتوریه.

در ترجمه، تعاریف و مثال‌ها از منابع مختلف فارسی و انگلیسی استفاده شده تا بهترین نتیجه حاصل بشه :)


</div>

---


<div dir="rtl">

<!-- TOC -->

<details open>
<summary><b>فهرست سریع</b></summary>

<br>

| دسته‌بندی | دیزاین پترن‌ها |
| --- | --- |
| 🧱 **اصول SOLID** | [🧱 اصول SOLID (SOLID Principles)](#اصول-solid-solid-principles-)<br>[تک‌مسئولیتی (SRP)](#۱-اصل-تک‌مسئولیتی-single-responsibility-principle-srp-)<br>[باز/بسته (OCP)](#۲-اصل-بازبسته-openclosed-principle-ocp-)<br>[جایگزینی لیسکوف (LSP)](#۳-اصل-جایگزینی-لیسکوف-liskov-substitution-principle-lsp-)<br>[تفکیک اینترفیس (ISP)](#۴-اصل-تفکیک-اینترفیس-interface-segregation-principle-isp-)<br>[وارونگی وابستگی (DIP)](#۵-اصل-وارونگی-وابستگی-dependency-inversion-principle-dip-) |
| 🏗️ **سازنده (Creational)** | [🏠 کارخانه ساده (Simple Factory)](#کارخانه-ساده-simple-factory-)<br>[🏭 فکتوری متد (Factory Method)](#فکتوری-متد-factory-method-)<br>[🔨 کارخانه انتزاعی (Abstract Factory)](#کارخانه-انتزاعی-abstract-factory-)<br>[👷 بیلدر (Builder)](#بیلدر-builder-)<br>[🐑 نمونه اولیه (Prototype)](#نمونه-اولیه-prototype-)<br>[💍 تک‌نمونه (Singleton)](#تک‌نمونه-singleton-) |
| 🧩 **ساختاری (Structural)** | [🔌 مبدل (Adapter)](#مبدل-adapter-)<br>[🌉 پل (Bridge)](#پل-bridge-)<br>[🌿 درختی (Composite)](#درختی-composite-)<br>[☕ دکوریتور (Decorator)](#دکوریتور-decorator-)<br>[📦 نما (Facade)](#نما-facade-)<br>[🍃 فلای‌وِیت (Flyweight)](#فلای‌وِیت-flyweight-)<br>[🎱 پراکسی (Proxy)](#پراکسی-proxy-) |
| 🎭 **رفتاری (Behavioral)** | [🔗 زنجیره مسئولیت (Chain of Responsibility)](#زنجیره-مسئولیت-chain-of-responsibility-)<br>[👮 فرمان (Command)](#فرمان-command-)<br>[➿ پیمایش‌گر (Iterator)](#پیمایش‌گر-iterator-)<br>[👽 میانجی (Mediator)](#میانجی-mediator-)<br>[💾 نقطه‌ی بازگشت (Memento)](#نقطه‌ی-بازگشت-memento-)<br>[😎 ناظر (Observer)](#ناظر-observer-)<br>[🏃 بازدیدکننده (Visitor)](#بازدیدکننده-visitor-)<br>[💡 استراتژی (Strategy)](#استراتژی-strategy-)<br>[💢 حالت (State)](#حالت-state-)<br>[📒 متد قالب (Template Method)](#متد-قالب-template-method-) |

</details>

<!-- TOC -->

</div>

---

<div dir="rtl" align="center">

# مقدمه 🚀

</div>

<div dir="rtl">

دیزاین پترن‌ها یه سری دستورالعمل‌ان برای مقابله با مشکلات رایج.

اونا یه سری کلاس، پکیج یا کتابخونه نیستن که با اضافه کردنشون به پروژه‌ت جادو کنن. در عوض یه سری راه‌حل بهت می‌دن که
در شرایط خاص به مشکل نخوری.

<br>

> پس دیزاین پترن‌ها راه‌حلی برای مشکلات رایج هستن.

<br>

**ویکی‌پدیا** دیزاین پترن‌ها رو اینطوری توصیف می‌کنه:

> در مهندسی نرم‌افزار، الگوی طراحی یک راه‌حل عمومی قابل تکرار برای مشکلات متداول در زمینه طراحی نرم‌افزار است. الگوی
> طراحی، یک طراحی تمام‌شده نیست که به صورت مستقیم بتواند تبدیل به کد منبع یا ماشین شود؛ بلکه، یک توضیح یا قالب برای حل
> یک
> مسئله در شرایط مختلف است. الگوها در واقع بهترین روش ممکن هستند که یک برنامه‌نویس می‌تواند در هنگام طراحی یک برنامه
> برای
> حل مشکلاتش از آن‌ها استفاده کند.

<br>
<div dir="rtl" align="right">

## هشدار ⚠️

</div>

- الگوهای طراحی برای همه مشکلات راه‌حل ندارن.
- سعی نکن حتماً توی پروژه‌هات از اونا استفاده کنی؛ یادت باشه دیزاین پترن‌ها راه‌حلی برای مشکلاتن، نه راهی برای پیدا کردن مشکل. پس خیلی درگیرِ پیدا کردن دلیل برای استفاده ازشون نشو.
- اگه سرِ جای درست از اونا استفاده کنی، پروژه رو از مشکلات نجات می‌دی؛ در غیر این صورت قراره فاجعه به بار بیاد.

<br>
<br>

---

<div align="center">

## این راهنما رو چطوری بخونیم؟ 🧭

</div>

<div dir="rtl">

این راهنما برای کسیه که یه کم با **شیءگرایی (OOP)** آشناست (کلاس، آبجکت، ارث‌بری، اینترفیس) و می‌خواد دیزاین پترن‌ها رو بدون خشکیِ کتاب‌های دانشگاهی یاد بگیره. فرقی نمی‌کنه مبتدی باشی یا فقط دنبال یه مرور سریع.

هر الگو رو با یه قالب ثابت پیش می‌بریم تا راحت دنبالش کنی:

*   🌍 **یه مثال از دنیای واقعی** تا حسش کنی.
*   💡 **به زبون ساده** که ته‌نشین بشه.
*   📖 **تعریف ویکی‌پدیا** (به‌همراه ترجمه فارسی) تا دقیق هم بدونی.
*   💻 **کد، توی ۱۰ زبان** (Python، TypeScript، JavaScript، C#، PHP، Go، Java، C++، Kotlin، Dart)؛ روی زبون خودت کلیک کن و بازش کن.
*   🤔 **کی به کارش ببریم؟** یه جعبه کوتاه که می‌گه کجا به دردت می‌خوره، کجا نه، و فرقش با الگوهای شبیهش چیه.

الگوها هم سه دسته‌ان: **سازنده (Creational)** درباره‌ی ساختن آبجکت‌هاست، **ساختاری (Structural)** درباره‌ی کنار هم چیدنِ کلاس‌ها و آبجکت‌ها، و **رفتاری (Behavioral)** درباره‌ی اینکه آبجکت‌ها چطور با هم حرف می‌زنن و کار رو بین خودشون تقسیم می‌کنن.

> 💡 لازم نیست همه رو یه‌جا حفظ کنی! اینجا رو مثل یه فرهنگِ لغت ببین؛ هر وقت سرِ مشکلی گیر کردی، برگرد و الگوی مناسبش رو پیدا کن.

</div>

---

<div align="center">

## اصول SOLID (SOLID Principles) 🧱

</div>

<div dir="rtl">

قبل از اینکه بریم سراغ دیزاین پترن‌ها، باید الفبای کدنویسی تمیز رو یاد بگیریم. این ۵ تا اصل (SOLID) بهت کمک می‌کنن کدی بنویسی که راحت تغییر کنه و مثل ماکارونی درهم‌پیچیده نشه! 🍝

### ۱. اصل تک‌مسئولیتی (Single Responsibility Principle, SRP) 🧙
> **قانون طلایی:** هر کلاس فقط و فقط باید **یک دلیل** برای تغییر داشته باشه.

<div align="center">
📦 <b>مثال دنیای واقعی: جعبه ابزار vs چاقوی سوئیسی</b>
</div>

فرض کن یه چاقوی سوئیسی داری که هم پیچ‌گوشتیه، هم اره، هم دربازکن. اگه اره‌ش بشکنه، باید کل چاقو رو بدی تعمیر و دیگه پیچ‌گوشتی هم نداری!
بهترین کار اینه که یه جعبه ابزار داشته باشی که توش پیچ‌گوشتی جدا و اره جدا باشه. اینطوری خرابی یکی به بقیه ربطی نداره.

💻 **توی کد یعنی چی؟**
کلاسی که هم اطلاعات یوزر رو ثبت می‌کنه، هم بهش ایمیل خوش‌آمدگویی می‌فرسته، هم لاگ می‌ندازه، اشتباهه!
*   اگه سرویس ایمیل عوض بشه -> کلاس باید تغییر کنه.
*   اگه فرمت لاگ عوض بشه -> کلاس باید تغییر کنه.
✅ **درست:** `UserRepository` برای دیتابیس، `EmailService` برای ایمیل، `Logger` برای لاگ.

---

### ۲. اصل باز/بسته (Open/Closed Principle, OCP) 🚪
> **قانون طلایی:** نرم‌افزار باید برای **توسعه باز** (Open)، اما برای **تغییر بسته** (Closed) باشه.

<div align="center">
🎮 <b>مثال دنیای واقعی: کنسول بازی</b>
</div>

تو یک پلی‌استیشن داری. وقتی بازی جدیدی (مثل GTA VI) میاد، لازم نیست کل دستگاه رو باز کنی و سیم‌کشی‌شو عوض کنی تا بازی جدید رو بخونه!
کنسول **بسته** است (سخت‌افزارش ثابت می‌مونه) اما برای **توسعه** بازه (فقط دیسک بازی جدید رو می‌ذاری توش).

💻 **توی کد یعنی چی؟**
اگه فردا مشتری گفت «حالا می‌خوام پرداخت با بیت‌کوین هم داشته باشیم»، نباید بری توی کلاس `PaymentService` و کد `if (type == 'bitcoin')` اضافه کنی (این یعنی تغییر کد قبلی ❌).
باید طوری کد زده باشی که فقط یه کلاس جدید `BitcoinPayment` بسازی که همون اینترفیس مشترک رو پیاده کنه، و بقیه سیستم بدون تغییر باهاش کار کنه (این یعنی توسعه ✅).

---

### ۳. اصل جایگزینی لیسکوف (Liskov Substitution Principle, LSP) 🧩
> **قانون طلایی:** کلاس فرزند باید بتونه جای کلاس پدر بشینه، بدون اینکه رفتار برنامه عوض بشه یا ارور بده.

<div align="center">
☕️ <b>مثال دنیای واقعی: دستگاه قهوه‌ساز</b>
</div>

فرض کن یه کلاس کلی داریم به اسم **«دستگاه قهوه‌ساز»** که یه دستور داره به اسم: `addMilk()` (شیر اضافه کن).
حالا میایم یه کلاس فرزند می‌سازیم به اسم **«دستگاه اسپرسوساز خالص»** (که فقط قهوه سیاه می‌ده و اصلاً مخزن شیر نداره).

اگه توی کد برنامه، هر جا که «دستگاه قهوه‌ساز» لازم داشتیم، بیایم این «اسپرسوساز» رو بذاریم، چی می‌شه؟
وقتی برنامه دستورِ `addMilk()` رو صدا بزنه، اسپرسوساز قاطی می‌کنه یا ارور می‌ده! 💥

چرا؟ چون این فرزند (اسپرسوساز) به قول‌وقرارِ پدرش وفادار نموند؛ پدر قول داده بود شیر اضافه کنه، ولی این یکی نتونست. پس **اصل جایگزینی** رو نقض کرده.

💻 **توی کد یعنی چی؟**
اگه یه کلاس `Bird` (پدر) داری که متد `fly()` داره، نباید کلاسی مثل `Penguin` (فرزند) بسازی که ازش ارث ببره ولی موقع پرواز ارور `I can't fly` بده!
چون هر جا تو کد از `Bird` استفاده کردی، باید بتونی `Penguin` هم بذاری. اگه پنگوئن پرواز نمی‌کنه، پس نباید از `Bird` (که پرواز می‌کنه) ارث ببره.

---

### ۴. اصل تفکیک اینترفیس (Interface Segregation Principle, ISP) ✂
> **قانون طلایی:** نباید کلاس‌ها رو مجبور کنیم متدهایی رو پیاده‌سازی کنن که بهشون نیاز ندارن.

<div align="center">
🍔 <b>مثال دنیای واقعی: منوی رستوران</b>
</div>

فرض کن رفتی رستوران و فقط یه «سالاد فصل» می‌خوای. اما رستوران فقط یه منوی غول‌آسا داره به اسم «سوپر منو» که توش پیتزا، کباب، سوشی و سالاد هست. گارسون مجبورت می‌کنه کل این منوی سنگین رو دستت بگیری و ورق بزنی تا برسی به سالاد.
خیلی بهتر بود اگه یه «منوی سالاد» جدا و کوچیک و سبک وجود داشت.

💻 **توی کد یعنی چی؟**
اگه یه اینترفیس گنده داری به اسم `Animal` که توش هم `fly()` داره، هم `swim()` و هم `bark()`.
حالا کلاس `Dog` مجبوره `fly()` رو هم داشته باشه (و توش خالی باشه)!
✅ **درست:** اینترفیس‌ها رو بشکنی: `Flyable`، `Swimmable`، `Barkable`. حالا سگ فقط `Barkable` و `Swimmable` رو پیاده‌سازی می‌کنه.

---

### ۵. اصل وارونگی وابستگی (Dependency Inversion Principle, DIP) 🔌
> **قانون طلایی:** به چیزهای واقعی و ملموس (Concrete) وابسته نباش، به مفاهیم کلی (Abstractions) وابسته باش.

<div align="center">
🔌 <b>مثال دنیای واقعی: دوشاخه و پریز برق</b>
</div>

لامپ اتاقت که مستقیم به سیم‌های داخل دیوار لحیم نشده، شده؟ معلومه که نه!
چون اگه اینطوری بود، هر بار که می‌خواستی یه سشوار به برق بزنی یا لامپ رو عوض کنی، باید دیوار رو خراب می‌کردی و سیم‌کشی رو تغییر می‌دادی. 🧱
به جاش چی داریم؟ «پریز برق». پریز یه استاندارد (Interface) هست. سشوار و تلویزیون و لامپ، همگی فقط با پریز کار دارن و براشون اصلا مهم نیست که پشت دیوار سیم‌ها چجوری سیم‌کشی شدن.

💻 **توی کد یعنی چی؟**
کلاس `Store` نباید مستقیم بگه `new MySQLDatabase()`. چون اگه فردا بخوایم بریم روی `PostgreSQL` بیچاره می‌شیم.
کلاس `Store` باید بگه «من یه چیزی می‌خوام که `IDatabase` باشه». حالا اینکه اون پشت MySQL هست یا Mongo، برای `Store` مهم نیست.

</div>

<br>

---

<br>

<div align="center">

# الگوهای سازنده (Creational Design Patterns) 🧱

</div>

به زبون ساده:

> الگوهای سازنده سراغِ دردسرهای ساختنِ آبجکت می‌رن.

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, creational design patterns are design patterns that deal with object creation mechanisms,
> trying to create objects in a manner suitable to the situation.

</div>

خلاصه: الگوهای سازنده روش ساختِ آبجکت‌ها رو طوری مدیریت می‌کنن که برای هر موقعیت، مناسب‌ترین راه انتخاب بشه.

<br>

---

<div align="center">

## کارخانه ساده (Simple Factory) 🏠

</div>

<div align="center">
🚪 <b>مثال دنیای واقعی: کارگاه نجاری</b>
</div>

فرض کن داری یه خونه می‌سازی. برای هر اتاقی یه در لازم داری.
منطقیه که برای هر در، خودت اره و تیشه برداری و بیفتی به جون چوب؟ 🪚 نه! اینطوری که تو گل می‌مونی.

راه‌حل چیه؟ زنگ می‌زنی به «کارگاه نجاری» (Factory) و می‌گی: «آقا یه در چوبی با عرض ۹۰ و ارتفاع ۲۱۰ می‌خوام».
دیگه برات مهم نیست نجار چجوری چوب رو می‌بره یا از چه چسبی استفاده می‌کنه. تو فقط محصول نهایی رو تحویل می‌گیری.

💡 **به زبون ساده:**
> این پترن می‌گه: **«بی‌خیالِ `new` کردنِ مستقیم شو! ساختن آبجکت رو بسپار به یه متد مخصوص.»**
> اینطوری کدت تمیز می‌مونه و اگه فردا خواستی روش ساخت در رو عوض کنی، فقط همون کارگاه رو تغییر می‌دی، نه کل خونه رو.

ویکی‌پدیا:

<div dir="ltr">

> In object-oriented programming (OOP), a factory is an object for creating other objects – formally a factory is a
> function or method that returns objects of a varying prototype or class from some method call, which is assumed to
> be "
> new".

</div>

خلاصه‌ش به زبون خودمون: «کارخانه» یه آبجکته که کارش ساختن آبجکت‌های دیگه‌ست.
یعنی به‌جای اینکه خودت مستقیم `new` بزنی، یه متد صدا می‌زنی و اون برات نمونه‌ی آماده رو تحویل می‌ده.

**مثال برنامه‌نویسی**

توی این مثال دقیقاً همون سناریوی در و کارگاه رو پیاده‌سازی می‌کنیم.
اول یه اینترفیس `Door` داریم، بعد پیاده‌سازی `WoodenDoor`، و در نهایت `DoorFactory` که برامون در می‌سازه.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
from abc import ABC, abstractmethod


class Door(ABC):
    @abstractmethod
    def getWidth(self):
        ...

    @abstractmethod
    def getHeight(self):
        ...


class WoodenDoor(Door):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def getWidth(self):
        return self.width

    def getHeight(self):
        return self.height


class DoorFactory:
    @staticmethod
    def makeDoor(width, height):
        return WoodenDoor(width, height)


# ----------------------------
door = DoorFactory.makeDoor(90, 210)
print(door.getHeight())
print(door.getWidth())
```

</div>

</details>

<details>
<summary>TypeScript</summary>

<div dir="ltr">

```typescript
interface Door {
    getWidth(): number;
    getHeight(): number;
}

class WoodenDoor implements Door {
    private width: number;
    private height: number;

    constructor(width: number, height: number) {
        this.width = width;
        this.height = height;
    }

    getWidth(): number {
        return this.width;
    }

    getHeight(): number {
        return this.height;
    }
}

class DoorFactory {
    static makeDoor(width: number, height: number): Door {
        return new WoodenDoor(width, height);
    }
}

// ----------------------------

const door: Door = DoorFactory.makeDoor(90, 210);
console.log(door.getHeight());
console.log(door.getWidth());
```

</div>

</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class Door {
    getWidth() {
        throw new Error("not implemented");
    }

    getHeight() {
        throw new Error("not implemented");
    }
}

class WoodenDoor extends Door {
    constructor(width, height) {
        super();
        this.width = width;
        this.height = height;
    }

    getWidth() {
        return this.width;
    }

    getHeight() {
        return this.height;
    }
}

class DoorFactory {
    static makeDoor(width, height) {
        return new WoodenDoor(width, height);
    }
}


const door = DoorFactory.makeDoor(90, 210);
console.log(door.getHeight());
console.log(door.getWidth());
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;

public interface IDoor
{
    int GetHeight();
    int GetWidth();
}

public class WoodenDoor : IDoor
{
    private int Height { get; set; }
    private int Width { get; set; }

    public WoodenDoor(int width, int height)
    {
        this.Width = width;
        this.Height = height;
    }

    public int GetHeight()
    {
        return this.Height;
    }
    public int GetWidth()
    {
        return this.Width;
    }
}

public static class DoorFactory
{
    public static IDoor MakeDoor(int width, int height)
    {
        return new WoodenDoor(width, height);
    }
}


// ----------------------------

var door = DoorFactory.MakeDoor(90, 210);
Console.WriteLine(door.GetHeight());
Console.WriteLine(door.GetWidth());
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface DoorInterface {
    public function getHeight();
    public function getWidth();
}

class WoodenDoor implements DoorInterface {
    private $width;
    private $height;

    public function __construct($width, $height) {
        $this->width = $width;
        $this->height = $height;
    }

    public function getHeight() {
        return $this->height;
    }
    public function getWidth() {
        return $this->width;
    }
}

class DoorFactory {
    public static function makeDoor($width, $height) {
        return new WoodenDoor($width, $height);
    }
}

$door = DoorFactory::makeDoor(90, 210);
echo $door->getHeight() . "\n";
echo $door->getWidth() . "\n";

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Door interface {
	getHeight() int
	getWidth() int
}

type WoodenDoor struct {
	width  int
	height int
}

func NewWoodenDoor(width, height int) *WoodenDoor {
	return &WoodenDoor{width: width, height: height}
}

func (w *WoodenDoor) getHeight() int {
	return w.height
}

func (w *WoodenDoor) getWidth() int {
	return w.width
}

type DoorFactory struct{}

func (df *DoorFactory) makeDoor(width, height int) Door {
	return NewWoodenDoor(width, height)
}

func main() {
	doorFactory := &DoorFactory{}
	door := doorFactory.makeDoor(90, 210)
	fmt.Println(door.getHeight())
	fmt.Println(door.getWidth())
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
public interface Door {
    int getHeight();
    int getWidth();
}

public class WoodenDoor implements Door {
    private int width;
    private int height;

    public WoodenDoor(int width, int height) {
        this.width = width;
        this.height = height;
    }

    public int getHeight() {
        return height;
    }
    public int getWidth() {
        return width;
    }
}

public class DoorFactory {
    public static Door makeDoor(int width, int height) {
        return new WoodenDoor(width, height);
    }
}

// ----------------------------

Door door = DoorFactory.makeDoor(90, 210);
System.out.println(door.getHeight());
System.out.println(door.getWidth());
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

// Door interface
class Door {
public:
    virtual ~Door() = default;
    virtual int getWidth() const = 0;
    virtual int getHeight() const = 0;
};

// Wooden door implementation
class WoodenDoor : public Door {
private:
    int width;
    int height;

public:
    WoodenDoor(int width, int height)
        : width(width), height(height) {}

    int getWidth() const override {
        return width;
    }

    int getHeight() const override {
        return height;
    }
};

// Door factory
class DoorFactory {
public:
    static Door* makeDoor(int width, int height) {
        return new WoodenDoor(width, height);
    }
};

// Usage
int main() {
    Door* door = DoorFactory::makeDoor(90, 210);
    std::cout << door->getHeight() << std::endl;
    std::cout << door->getWidth() << std::endl;

    delete door;
    return 0;
}
```

</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Door {
    fun getWidth(): Int
    fun getHeight(): Int
}

class WoodenDoor(private val width: Int, private val height: Int) : Door {
    override fun getWidth(): Int = width
    override fun getHeight(): Int = height
}

object DoorFactory {
    fun makeDoor(width: Int, height: Int): Door {
        return WoodenDoor(width, height)
    }
}

// ----------------------------

fun main() {
    val door = DoorFactory.makeDoor(90, 210)
    println(door.getHeight())
    println(door.getWidth())
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Door {
  int getWidth();
  int getHeight();
}

class WoodenDoor implements Door {
  final int width;
  final int height;

  WoodenDoor(this.width, this.height);

  @override
  int getWidth() => width;

  @override
  int getHeight() => height;
}

class DoorFactory {
  static Door makeDoor(int width, int height) {
    return WoodenDoor(width, height);
  }
}

// ----------------------------

void main() {
  var door = DoorFactory.makeDoor(90, 210);
  print(door.getHeight());
  print(door.getWidth());
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی ساختن یه آبجکت چند خط مقدمه‌چینی داره و نمی‌خوای این شلوغی همه‌جای کدت پخش شه، بسپارش به یه کارخانه ساده؛ ❌ اگه فقط یه `new` ساده‌ست، الکی پیچیده‌ش نکن.
> 🪤 **دام رایج:** کم‌کم همه‌چی رو می‌ریزی توی یه `makeDoor` غول‌پیکر پر از `if`/`else`؛ همون‌جاست که باید بری سراغ الگوهای جدی‌تر.
> 🔗 **فرقش با [فکتوری متد](#فکتوری-متد-factory-method-):** اینجا یه متد ساده (که معمولاً static هست) خودش تصمیم می‌گیره چی بسازه؛ توی فکتوری متد، تصمیمِ ساخت رو به زیرکلاس‌ها واگذار می‌کنی.


<br>

---

<div align="center">

## فکتوری متد (Factory Method) 🏭

</div>

<div align="center">
👔 <b>مثال دنیای واقعی: مدیر استخدام</b>
</div>

فرض کن یه مدیر استخدام (`HiringManager`) داریم. فرآیند استخدام توی این شرکت یه قانون کلی داره:
۱. مصاحبه‌کننده رو انتخاب کن.
۲. ازش بخواه سوال بپرسه.

اما نکته اینجاست: مدیر استخدامِ کل خودش نمی‌دونه برای هر پوزیشن باید چه سوالای تخصصی‌ای پرسید، یا کی صلاحیتش رو داره. پس چی‌کار می‌کنه؟ ساختن «مصاحبه‌کننده» رو می‌سپاره به مدیرهای هر بخش.

*   اگه استخدام برای بخش **فنی** باشه، مدیر فنی (`DevelopmentManager`) میاد و یه **برنامه‌نویس** (`Developer`) رو می‌سازه تا سوالای فنی بپرسه.
*   اگه استخدام برای بخش **مارکتینگ** باشه، مدیر مارکتینگ (`MarketingManager`) میاد و یه **بازاریاب** (`CommunityExecutive`) رو می‌سازه.

پس «فرآیند کلی مصاحبه» ثابته، اما اینکه «کی قراره سوال بپرسه» (یا همون ساختن آبجکت مصاحبه‌کننده) رو می‌سپاریم به زیرکلاس‌ها.

💡 **به زبون ساده:**
> این پترن می‌گه: **«من (کلاس پدر) منطق کلی کار رو می‌دونم، اما ساختن ابزار دقیقش (آبجکت) رو می‌سپارم به بچه‌هام (کلاس‌های فرزند).»**

ویکی‌پدیا:

<div dir="ltr">

> In class-based programming, the factory method pattern is a creational pattern that uses factory methods to deal with
> the problem of creating objects without having to specify the exact class of the object that will be created. This is
> done by creating objects by calling a factory method, either specified in an interface and implemented by child
> classes,
> or implemented in a base class and optionally overridden by derived classes, rather than by calling a constructor.

</div>

خلاصه‌ش این می‌شه: به‌جای اینکه مستقیم با `new` یه آبجکت بسازی، یه متد مخصوص ساخت (همون فکتوری متد) صداش می‌زنی. این متد یا توی یه اینترفیس تعریف شده و فرزندها پیاده‌سازیش می‌کنن، یا توی کلاس پدر یه نسخه پیش‌فرض داره و فرزندها در صورت نیاز بازنویسیش می‌کنن. این‌جوری کدِ پدر لازم نیست بدونه دقیقاً داره کدوم کلاس رو می‌سازه.

**مثال برنامه‌نویسی**

بیا از مثال مدیر استخدام برای درک بهتر استفاده کنیم.

پس اول یه اینترفیس برای مصاحبه‌کننده‌ها می‌سازیم و چند تا نمونه هم براش درست می‌کنیم.

بعدش `HiringManager` رو پیاده‌سازی می‌کنیم

آخرش هم هر فرزند ازش ارث می‌بره و متد `makeInterviewer` خودش رو داره:

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Interviewer:
    def askQuestions(self):
        pass


class Developer(Interviewer):
    def askQuestions(self):
        print('Asking about design patterns!')


class CommunityExecutive(Interviewer):
    def askQuestions(self):
        print('Asking about community building')


class HiringManager:
    def makeInterviewer(self):
        pass

    def takeInterview(self):
        interviewer = self.makeInterviewer()
        interviewer.askQuestions()


class DevelopmentManager(HiringManager):
    def makeInterviewer(self):
        return Developer()


class MarketingManager(HiringManager):
    def makeInterviewer(self):
        return CommunityExecutive()


# ----------------------------

devManager = DevelopmentManager()
devManager.takeInterview()

marketingManager = MarketingManager()
marketingManager.takeInterview()
```

</div>

</details>

<details>
<summary>TypeScript</summary>

<div dir="ltr">

```typescript
interface Interviewer {
  askQuestions(): void;
}

class Developer implements Interviewer {
  askQuestions(): void {
    console.log("Asking about design patterns!");
  }
}

class CommunityExecutive implements Interviewer {
  askQuestions(): void {
    console.log("Asking about community building");
  }
}

abstract class HiringManager {
  abstract makeInterviewer(): Interviewer;

  takeInterview(): void {
    let interviewer = this.makeInterviewer();
    interviewer.askQuestions();
  }
}

class DevelopmentManager extends HiringManager {
  makeInterviewer(): Developer {
    return new Developer();
  }
}

class MarketingManager extends HiringManager {
  makeInterviewer(): CommunityExecutive {
    return new CommunityExecutive();
  }
}

let devManager = new DevelopmentManager();
devManager.takeInterview();

let marketingManager = new MarketingManager();
marketingManager.takeInterview();
```

</div>

</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class Developer {
    askQuestions() {
        console.log("Asking about design patterns!");
    }
}

class CommunityExecutive {
    askQuestions() {
        console.log("Asking about community building");
    }
}

class HiringManager {
    takeInterview() {
        const interviewer = this.makeInterviewer();
        interviewer.askQuestions();
    }
}

class DevelopmentManager extends HiringManager {
    makeInterviewer() {
        return new Developer();
    }
}

class MarketingManager extends HiringManager {
    makeInterviewer() {
        return new CommunityExecutive();
    }
}

const devManager = new DevelopmentManager();
devManager.takeInterview();

const marketingManager = new MarketingManager();
marketingManager.takeInterview();

```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface IInterviewer
{
    void AskQuestions();
}

class Developer : IInterviewer
{
    public void AskQuestions()
    {
        Console.WriteLine("Asking about design patterns!");
    }
}

class CommunityExecutive : IInterviewer
{
    public void AskQuestions()
    {
        Console.WriteLine("Asking about community building");
    }
}

abstract class HiringManager
{
    // Factory method
    abstract protected IInterviewer MakeInterviewer();
    public void TakeInterview()
    {
        var interviewer = this.MakeInterviewer();
        interviewer.AskQuestions();
    }
}

class DevelopmentManager : HiringManager
{
    protected override IInterviewer MakeInterviewer()
    {
        return new Developer();
    }
}

class MarketingManager : HiringManager
{
    protected override IInterviewer MakeInterviewer()
    {
        return new CommunityExecutive();
    }
}


// ----------------------------

var devManager = new DevelopmentManager();
devManager.TakeInterview(); //Output : Asking about design patterns!

var marketingManager = new MarketingManager();
marketingManager.TakeInterview();//Output : Asking about community building

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface InterviewerInterface
{
    public function askQuestions();
}

class Developer implements InterviewerInterface
{
    public function askQuestions()
    {
        echo "Asking about design patterns!\n";
    }
}

class CommunityExecutive implements InterviewerInterface
{
    public function askQuestions()
    {
        echo "Asking about community building\n";
    }
}

abstract class HiringManager
{
    // Factory method
    abstract protected function makeInterviewer(): InterviewerInterface;

    public function takeInterview()
    {
        $interviewer = $this->makeInterviewer();
        $interviewer->askQuestions();
    }
}

class DevelopmentManager extends HiringManager
{
    protected function makeInterviewer(): InterviewerInterface
    {
        return new Developer();
    }
}

class MarketingManager extends HiringManager
{
    protected function makeInterviewer(): InterviewerInterface
    {
        return new CommunityExecutive();
    }
}


// Usage
$devManager = new DevelopmentManager();
$devManager->takeInterview(); // Output: Asking about design patterns!

$marketingManager = new MarketingManager();
$marketingManager->takeInterview(); // Output: Asking about community building

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Interviewer interface {
	AskQuestions()
}

type Developer struct{}

func (d *Developer) AskQuestions() {
	fmt.Println("Asking about design patterns!")
}

type CommunityExecutive struct{}

func (ce *CommunityExecutive) AskQuestions() {
	fmt.Println("Asking about community building")
}

// HiringManager نقش کلاس پدر رو داره: takeInterview فقط یک‌بار اینجا تعریف می‌شه.
// تنها چیزی که توی هر مدیر فرق می‌کنه، فکتوری متد‌ی makeInterviewer هست.
type HiringManager struct {
	makeInterviewer func() Interviewer
}

func (hm *HiringManager) TakeInterview() {
	interviewer := hm.makeInterviewer()
	interviewer.AskQuestions()
}

type DevelopmentManager struct {
	HiringManager
}

func NewDevelopmentManager() *DevelopmentManager {
	return &DevelopmentManager{
		HiringManager{makeInterviewer: func() Interviewer { return &Developer{} }},
	}
}

type MarketingManager struct {
	HiringManager
}

func NewMarketingManager() *MarketingManager {
	return &MarketingManager{
		HiringManager{makeInterviewer: func() Interviewer { return &CommunityExecutive{} }},
	}
}

func main() {
	devManager := NewDevelopmentManager()
	devManager.TakeInterview() // Output: Asking about design patterns!

	marketingManager := NewMarketingManager()
	marketingManager.TakeInterview() // Output: Asking about community building
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Interviewer {
  void askQuestions();
}

class Developer implements Interviewer {

  @Override
  public void askQuestions() {
    System.out.println("Asking about design patterns!");
  }
}

class CommunityExecutive implements Interviewer {

  @Override
  public void askQuestions() {
    System.out.println("Asking about community building");
  }
}

abstract class HiringManager {
  abstract Interviewer makeInterviewer();
  public void takeInterview() {
    Interviewer interviewer = this.makeInterviewer();
    interviewer.askQuestions();
  }
}

class DevelopmentManager extends HiringManager {
  public Developer makeInterviewer() {
    return new Developer();
  }
}

class MarketingManager extends HiringManager {
  public CommunityExecutive makeInterviewer() {
    return new CommunityExecutive();
  }
}

// ----------------------------

DevelopmentManager devManager = new DevelopmentManager();
devManager.takeInterview();

MarketingManager marketingManager = new MarketingManager();
marketingManager.takeInterview();
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <memory>

// Interviewer interface
class Interviewer {
public:
    virtual ~Interviewer() = default;
    virtual void askQuestions() = 0;
};

// Developer interviewer
class Developer : public Interviewer {
public:
    void askQuestions() override {
        std::cout << "Asking about design patterns!" << std::endl;
    }
};

// Community executive interviewer
class CommunityExecutive : public Interviewer {
public:
    void askQuestions() override {
        std::cout << "Asking about community building" << std::endl;
    }
};

// Abstract hiring manager
class HiringManager {
public:
    virtual ~HiringManager() = default;
    virtual std::unique_ptr<Interviewer> makeInterviewer() = 0;
    
    void takeInterview() {
        auto interviewer = makeInterviewer();
        interviewer->askQuestions();
    }
};

// Development manager
class DevelopmentManager : public HiringManager {
public:
    std::unique_ptr<Interviewer> makeInterviewer() override {
        return std::make_unique<Developer>();
    }
};

// Marketing manager
class MarketingManager : public HiringManager {
public:
    std::unique_ptr<Interviewer> makeInterviewer() override {
        return std::make_unique<CommunityExecutive>();
    }
};

// Usage
int main() {
    DevelopmentManager devManager;
    devManager.takeInterview(); // Output: Asking about design patterns!
    
    MarketingManager marketingManager;
    marketingManager.takeInterview(); // Output: Asking about community building
    
    return 0;
}
```

</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Interviewer {
    fun askQuestions()
}

class Developer : Interviewer {
    override fun askQuestions() {
        println("Asking about design patterns!")
    }
}

class CommunityExecutive : Interviewer {
    override fun askQuestions() {
        println("Asking about community building")
    }
}

abstract class HiringManager {
    abstract fun makeInterviewer(): Interviewer

    fun takeInterview() {
        val interviewer = makeInterviewer()
        interviewer.askQuestions()
    }
}

class DevelopmentManager : HiringManager() {
    override fun makeInterviewer(): Interviewer = Developer()
}

class MarketingManager : HiringManager() {
    override fun makeInterviewer(): Interviewer = CommunityExecutive()
}

// ----------------------------

fun main() {
    val devManager = DevelopmentManager()
    devManager.takeInterview()

    val marketingManager = MarketingManager()
    marketingManager.takeInterview()
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Interviewer {
  void askQuestions();
}

class Developer implements Interviewer {
  @override
  void askQuestions() {
    print('Asking about design patterns!');
  }
}

class CommunityExecutive implements Interviewer {
  @override
  void askQuestions() {
    print('Asking about community building');
  }
}

abstract class HiringManager {
  Interviewer makeInterviewer();

  void takeInterview() {
    var interviewer = makeInterviewer();
    interviewer.askQuestions();
  }
}

class DevelopmentManager extends HiringManager {
  @override
  Interviewer makeInterviewer() => Developer();
}

class MarketingManager extends HiringManager {
  @override
  Interviewer makeInterviewer() => CommunityExecutive();
}

// ----------------------------

void main() {
  var devManager = DevelopmentManager();
  devManager.takeInterview();

  var marketingManager = MarketingManager();
  marketingManager.takeInterview();
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی کلاس پدر منطق کلی کار رو بلده، ولی نوع دقیقِ آبجکت به زیرکلاس بستگی داره، ساختش رو می‌سپاری به فرزندها؛ ❌ ولی اگه فقط یه‌جا و بر اساس یه شرط ساده آبجکت می‌سازی، یه if کوچیک یا «کارخانه ساده» کافیه و این الگو زیادی‌ست.
> 🪤 **دام رایج:** برای یه حالتِ ساده کلی زیرکلاس می‌سازی و کد رو بی‌خودی شلوغ می‌کنی؛ این الگو وقتی می‌ارزه که واقعاً چند نوع سازنده داشته باشی.
> 🔗 **فرقش با [کارخانه ساده](#کارخانه-ساده-simple-factory-):** کارخانه ساده همه‌چی رو توی یه متد با شرط جمع می‌کنه، اما اینجا ساختِ آبجکت رو به ارث‌بری و زیرکلاس‌ها می‌سپاری، پس هر نوع جدید یعنی یه زیرکلاس جدید، نه دست‌کاری متدِ موجود.


<br>

---

<div align="center">

## کارخانه انتزاعی (Abstract Factory) 🔨

</div>

<div align="center">
🛠 <b>مثال دنیای واقعی: در و نصاب، با هم</b>
</div>

یادته توی [کارخانه ساده](#کارخانه-ساده-simple-factory-) یه «در» سفارش می‌دادیم؟ بیا همون مثال رو کامل‌تر کنیم. این بار فقط «در» نمی‌خوای، «نصاب»ش رو هم می‌خوای.
نکته مهم اینه که اینا باید با هم **ست** باشن:
*   اگه در **چوبی** خریدی، باید **نجار** بیاد نصبش کنه.
*   اگه در **آهنی** خریدی، باید **جوشکار** بیاد.

فاجعه اونجاست که در چوبی بخری ولی جوشکار بیاد دم خونه! 🔥

اینجاست که **Abstract Factory** میاد وسط. ما به جای اینکه در و نصاب رو جدا جدا سفارش بدیم، زنگ می‌زنیم به «کارخونه محصولات چوبی». اونا هم در چوبی می‌دن، هم نجار رو می‌فرستن. اینطوری خیالمون راحته که همه چی با هم جوره.

💡 **به زبون ساده:**
> این پترن کارخونه‌ای از کارخونه‌هاست! یه کارخونه که یه بسته کامل و هماهنگ (Product Family) بهت می‌ده، تا قطعه ناجور کنار قطعه ناجور نیفته.

ویکی‌پدیا:

<div dir="ltr">

> The abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme
> without specifying their concrete classes

</div>

یعنی الگوی کارخانه انتزاعی بهت یه راه می‌ده که یه گروه از کارخونه‌های هم‌خانواده رو زیر یه چتر جمع کنی؛ بدون اینکه کد مصرف‌کننده بدونه پشت پرده دقیقاً کدوم کلاس واقعی داره ساخته می‌شه. کارش اینه که خانواده‌ای از محصولات سازگار رو با هم بسازه، نه تک‌تک قطعه‌ها رو جدا.

<br>

**مثال برنامه‌نویسی**

خب بیا همون مثال ساخت خونه و درهای جورواجور رو پیاده کنیم.

اول اینترفیس در رو می‌سازیم و چند تا نمونه ازش درمیاریم.

بعد برای هر در، متخصص خودش رو می‌سازیم.

آخر سر هم می‌ریم سراغ خودِ پترن.

مثلاً کلاس `WoodenDoorFactory` رو وقتی به کار می‌بریم که در چوبی بخوایم. کارش اینه: درِ چوبی رو از `WoodenDoor` می‌سازه و متخصصش (همون نجار) رو از `Carpenter`.

برای در آهنی هم دقیقاً همین کارو می‌کنیم.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Door:
    def getDescription(self):
        pass


class WoodenDoor(Door):
    def getDescription(self):
        print('I am a wooden door')


class IronDoor(Door):
    def getDescription(self):
        print('I am an iron door')


class DoorFittingExpert:
    def getDescription(self):
        pass


class Carpenter(DoorFittingExpert):
    def getDescription(self):
        print('I can only fit wooden doors')


class Welder(DoorFittingExpert):
    def getDescription(self):
        print('I can only fit iron doors')


class DoorFactory:
    def makeDoor(self):
        pass

    def makeFittingExpert(self):
        pass


class WoodenDoorFactory(DoorFactory):
    def makeDoor(self):
        return WoodenDoor()

    def makeFittingExpert(self):
        return Carpenter()


class IronDoorFactory(DoorFactory):
    def makeDoor(self):
        return IronDoor()

    def makeFittingExpert(self):
        return Welder()


# ----------------------------

woodenFactory = WoodenDoorFactory()

door = woodenFactory.makeDoor()
expert = woodenFactory.makeFittingExpert()

door.getDescription()    # Output: I am a wooden door
expert.getDescription()  # Output: I can only fit wooden doors

# ----------------------------

ironFactory = IronDoorFactory()

door = ironFactory.makeDoor()
expert = ironFactory.makeFittingExpert()

door.getDescription()    # Output: I am an iron door
expert.getDescription()  # Output: I can only fit iron doors
```

</div>

**می‌بینی که با هر دو نوع در یکجور رفتار می‌کنیم و خیالمون هم راحته که هیچ‌وقت متخصصِ اشتباه پای در اشتباه نمی‌ره.**

</details>

<details>
<summary>TypeScript</summary>

<div dir="ltr">

```typescript
interface Door {
    getDescription(): void;
}

class WoodenDoor implements Door {
    getDescription(): void {
        console.log("I am a wooden door");
    }
}

class IronDoor implements Door {
    getDescription(): void {
        console.log("I am an iron door");
    }
}

interface DoorFittingExpert {
    getDescription(): void;
}

class Carpenter implements DoorFittingExpert {
    getDescription(): void {
        console.log("I can only fit wooden doors");
    }
}

class Welder implements DoorFittingExpert {
    getDescription(): void {
        console.log("I can only fit iron doors");
    }
}

abstract class DoorFactory {
    abstract makeDoor(): Door;

    abstract makeFittingExpert(): DoorFittingExpert;
}

class WoodenDoorFactory extends DoorFactory {
    makeDoor(): WoodenDoor {
        return new WoodenDoor();
    }

    makeFittingExpert(): Carpenter {
        return new Carpenter();
    }
}

class IronDoorFactory extends DoorFactory {
    makeDoor(): IronDoor {
        return new IronDoor();
    }

    makeFittingExpert(): Welder {
        return new Welder();
    }
}

// ----------------------------

let woodenFactory = new WoodenDoorFactory();

let door = woodenFactory.makeDoor();
let expert = woodenFactory.makeFittingExpert();

door.getDescription();   // Output: I am a wooden door
expert.getDescription(); // Output: I can only fit wooden doors

// ----------------------------

let ironFactory = new IronDoorFactory();

door = ironFactory.makeDoor();
expert = ironFactory.makeFittingExpert();

door.getDescription();   // Output: I am an iron door
expert.getDescription(); // Output: I can only fit iron doors

```

</div>

**می‌بینی که با هر دو نوع در یکجور رفتار می‌کنیم و خیالمون هم راحته که هیچ‌وقت متخصصِ اشتباه پای در اشتباه نمی‌ره.**

</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class WoodenDoor {
    getDescription() {
        console.log("I am a wooden door");
    }
}

class IronDoor {
    getDescription() {
        console.log("I am an iron door");
    }
}

class Carpenter {
    getDescription() {
        console.log("I can only fit wooden doors");
    }
}

class Welder {
    getDescription() {
        console.log("I can only fit iron doors");
    }
}

class DoorFactory {
    makeDoor() {
        throw new Error("makeDoor() must be implemented by subclasses");
    }

    makeFittingExpert() {
        throw new Error("makeFittingExpert() must be implemented by subclasses");
    }
}

class WoodenDoorFactory extends DoorFactory {
    makeDoor() {
        return new WoodenDoor();
    }

    makeFittingExpert() {
        return new Carpenter();
    }
}

class IronDoorFactory extends DoorFactory {
    makeDoor() {
        return new IronDoor();
    }

    makeFittingExpert() {
        return new Welder();
    }
}

// ----------------------------

let woodenFactory = new WoodenDoorFactory();

let door = woodenFactory.makeDoor();
let expert = woodenFactory.makeFittingExpert();

door.getDescription();   // Output: I am a wooden door
expert.getDescription(); // Output: I can only fit wooden doors

// ----------------------------

let ironFactory = new IronDoorFactory();

door = ironFactory.makeDoor();
expert = ironFactory.makeFittingExpert();

door.getDescription();   // Output: I am an iron door
expert.getDescription(); // Output: I can only fit iron doors
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface IDoor {

  void GetDescription();

}
class WoodenDoor : IDoor
{
  public void GetDescription()
  {
    Console.WriteLine("I am a wooden door");
  }
}

class IronDoor : IDoor
{
  public void GetDescription()
  {
    Console.WriteLine("I am an iron door");
  }
}

interface IDoorFittingExpert
{
  void GetDescription();
}

class Carpenter : IDoorFittingExpert
{
  public void GetDescription()
  {
    Console.WriteLine("I can only fit wooden doors");
  }
}

class Welder : IDoorFittingExpert
{
  public void GetDescription()
  {
    Console.WriteLine("I can only fit iron doors");
  }
}

interface IDoorFactory {
  IDoor MakeDoor();
  IDoorFittingExpert MakeFittingExpert();
}

// Wooden factory to return carpenter and wooden door
class WoodenDoorFactory : IDoorFactory
{
  public IDoor MakeDoor()
  {
    return new WoodenDoor();
  }

  public IDoorFittingExpert MakeFittingExpert()
  {
    return new Carpenter();
  }
}

// Iron door factory to get iron door and the relevant fitting expert
class IronDoorFactory : IDoorFactory
{
  public IDoor MakeDoor()
  {
    return new IronDoor();
  }

  public IDoorFittingExpert MakeFittingExpert()
  {
    return new Welder();
  }
}
// ----------------------------
var woodenFactory = new WoodenDoorFactory();

var woodenDoor = woodenFactory.MakeDoor();
var woodenExpert = woodenFactory.MakeFittingExpert();

woodenDoor.GetDescription();   // Output: I am a wooden door
woodenExpert.GetDescription(); // Output: I can only fit wooden doors

// ----------------------------

var ironFactory = new IronDoorFactory();

var ironDoor = ironFactory.MakeDoor();
var ironExpert = ironFactory.MakeFittingExpert();

ironDoor.GetDescription();   // Output: I am an iron door
ironExpert.GetDescription(); // Output: I can only fit iron doors

```

</div>

**می‌بینی که با هر دو نوع در یکجور رفتار می‌کنیم و خیالمون هم راحته که هیچ‌وقت متخصصِ اشتباه پای در اشتباه نمی‌ره.**

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php

interface DoorInterface {
  public function getDescription();
}

class WoodenDoor implements DoorInterface {
  public function getDescription() {
    echo "I am a wooden door";
  }
}

class IronDoor implements DoorInterface {
  public function getDescription() {
    echo "I am an iron door";
  }
}

interface DoorFittingExpertInterface {
  public function getDescription();
}

class Carpenter implements DoorFittingExpertInterface {
  public function getDescription() {
    echo "I can only fit wooden doors";
  }
}

class Welder implements DoorFittingExpertInterface {
  public function getDescription() {
    echo "I can only fit iron doors";
  }
}

interface DoorFactoryInterface {
  public function makeDoor(): DoorInterface;
  public function makeFittingExpert(): DoorFittingExpertInterface;
}

// Wooden factory to return carpenter and wooden door
class WoodenDoorFactory implements DoorFactoryInterface {
  public function makeDoor(): DoorInterface {
    return new WoodenDoor();
  }

  public function makeFittingExpert(): DoorFittingExpertInterface {
    return new Carpenter();
  }
}

// Iron door factory to get iron door and the relevant fitting expert
class IronDoorFactory implements DoorFactoryInterface {
  public function makeDoor(): DoorInterface {
    return new IronDoor();
  }

  public function makeFittingExpert(): DoorFittingExpertInterface {
    return new Welder();
  }
}


// Usage
$woodenFactory = new WoodenDoorFactory();

$woodenDoor = $woodenFactory->makeDoor();
$woodenExpert = $woodenFactory->makeFittingExpert();

$woodenDoor->getDescription();   // Output: I am a wooden door
echo "\n";
$woodenExpert->getDescription(); // Output: I can only fit wooden doors
echo "\n";

$ironFactory = new IronDoorFactory();

$ironDoor = $ironFactory->makeDoor();
$ironExpert = $ironFactory->makeFittingExpert();

$ironDoor->getDescription();   // Output: I am an iron door
echo "\n";
$ironExpert->getDescription(); // Output: I can only fit iron doors
echo "\n";

```

</div>

**می‌بینی که با هر دو نوع در یکجور رفتار می‌کنیم و خیالمون هم راحته که هیچ‌وقت متخصصِ اشتباه پای در اشتباه نمی‌ره.**

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

type IDoor interface {
	GetDescription()
}

type WoodenDoor struct{}

func (w *WoodenDoor) GetDescription() {
	fmt.Println("I am a wooden door")
}

type IronDoor struct{}

func (i *IronDoor) GetDescription() {
	fmt.Println("I am an iron door")
}

type IDoorFittingExpert interface {
	GetDescription()
}

type Carpenter struct{}

func (c *Carpenter) GetDescription() {
	fmt.Println("I can only fit wooden doors")
}

type Welder struct{}

func (w *Welder) GetDescription() {
	fmt.Println("I can only fit iron doors")
}

type IDoorFactory interface {
	MakeDoor() IDoor
	MakeFittingExpert() IDoorFittingExpert
}

type WoodenDoorFactory struct{}

func (w *WoodenDoorFactory) MakeDoor() IDoor {
	return &WoodenDoor{}
}

func (w *WoodenDoorFactory) MakeFittingExpert() IDoorFittingExpert {
	return &Carpenter{}
}

type IronDoorFactory struct{}

func (i *IronDoorFactory) MakeDoor() IDoor {
	return &IronDoor{}
}

func (i *IronDoorFactory) MakeFittingExpert() IDoorFittingExpert {
	return &Welder{}
}

func main() {
	woodenFactory := &WoodenDoorFactory{}

	woodenDoor := woodenFactory.MakeDoor()
	woodenExpert := woodenFactory.MakeFittingExpert()

	woodenDoor.GetDescription()   // Output: I am a wooden door
	woodenExpert.GetDescription() // Output: I can only fit wooden doors

	ironFactory := &IronDoorFactory{}

	ironDoor := ironFactory.MakeDoor()
	ironExpert := ironFactory.MakeFittingExpert()

	ironDoor.GetDescription()   // Output: I am an iron door
	ironExpert.GetDescription() // Output: I can only fit iron doors
}

```

</div>

**می‌بینی که با هر دو نوع در یکجور رفتار می‌کنیم و خیالمون هم راحته که هیچ‌وقت متخصصِ اشتباه پای در اشتباه نمی‌ره.**

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Door {
    void getDescription();
}

class WoodenDoor implements Door {
    @Override
    public void getDescription() {
        System.out.println("I am a wooden door");
    }
}

class IronDoor implements Door {
    @Override
    public void getDescription() {
        System.out.println("I am an iron door");
    }
}

interface DoorFittingExpert {
    void getDescription();
}

class Carpenter implements DoorFittingExpert {
    @Override
    public void getDescription() {
        System.out.println("I can only fit wooden doors");
    }
}

class Welder implements DoorFittingExpert {
    @Override
    public void getDescription() {
        System.out.println("I can only fit iron doors");
    }
}

interface DoorFactory {
    Door makeDoor();
    DoorFittingExpert makeFittingExpert();
}

class WoodenDoorFactory implements DoorFactory {
    @Override
    public WoodenDoor makeDoor() {
        return new WoodenDoor();
    }

    @Override
    public Carpenter makeFittingExpert() {
        return new Carpenter();
    }
}

class IronDoorFactory implements DoorFactory {
    @Override
    public IronDoor makeDoor() {
        return new IronDoor();
    }

    @Override
    public Welder makeFittingExpert() {
        return new Welder();
    }
}

// ----------------------------

WoodenDoorFactory woodenFactory = new WoodenDoorFactory();
Door woodenDoor = woodenFactory.makeDoor();
DoorFittingExpert woodenExpert = woodenFactory.makeFittingExpert();

woodenDoor.getDescription();   // Output: I am a wooden door
woodenExpert.getDescription(); // Output: I can only fit wooden doors

// ----------------------------

IronDoorFactory ironFactory = new IronDoorFactory();
Door ironDoor = ironFactory.makeDoor();
DoorFittingExpert ironExpert = ironFactory.makeFittingExpert();

ironDoor.getDescription();   // Output: I am an iron door
ironExpert.getDescription(); // Output: I can only fit iron doors
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <memory>

// Door interface
class Door {
public:
    virtual ~Door() = default;
    virtual void getDescription() = 0;
};

// Wooden door
class WoodenDoor : public Door {
public:
    void getDescription() override {
        std::cout << "I am a wooden door" << std::endl;
    }
};

// Iron door
class IronDoor : public Door {
public:
    void getDescription() override {
        std::cout << "I am an iron door" << std::endl;
    }
};

// Door fitting expert interface
class DoorFittingExpert {
public:
    virtual ~DoorFittingExpert() = default;
    virtual void getDescription() = 0;
};

// Carpenter
class Carpenter : public DoorFittingExpert {
public:
    void getDescription() override {
        std::cout << "I can only fit wooden doors" << std::endl;
    }
};

// Welder
class Welder : public DoorFittingExpert {
public:
    void getDescription() override {
        std::cout << "I can only fit iron doors" << std::endl;
    }
};

// Door factory interface
class DoorFactory {
public:
    virtual ~DoorFactory() = default;
    virtual std::unique_ptr<Door> makeDoor() = 0;
    virtual std::unique_ptr<DoorFittingExpert> makeFittingExpert() = 0;
};

// Wooden door factory
class WoodenDoorFactory : public DoorFactory {
public:
    std::unique_ptr<Door> makeDoor() override {
        return std::make_unique<WoodenDoor>();
    }
    
    std::unique_ptr<DoorFittingExpert> makeFittingExpert() override {
        return std::make_unique<Carpenter>();
    }
};

// Iron door factory
class IronDoorFactory : public DoorFactory {
public:
    std::unique_ptr<Door> makeDoor() override {
        return std::make_unique<IronDoor>();
    }
    
    std::unique_ptr<DoorFittingExpert> makeFittingExpert() override {
        return std::make_unique<Welder>();
    }
};

// Usage
int main() {
    WoodenDoorFactory woodenFactory;
    auto woodenDoor = woodenFactory.makeDoor();
    auto woodenExpert = woodenFactory.makeFittingExpert();

    woodenDoor->getDescription();   // Output: I am a wooden door
    woodenExpert->getDescription(); // Output: I can only fit wooden doors

    IronDoorFactory ironFactory;
    auto ironDoor = ironFactory.makeDoor();
    auto ironExpert = ironFactory.makeFittingExpert();

    ironDoor->getDescription();   // Output: I am an iron door
    ironExpert->getDescription(); // Output: I can only fit iron doors

    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Door {
    fun getDescription()
}

class WoodenDoor : Door {
    override fun getDescription() {
        println("I am a wooden door")
    }
}

class IronDoor : Door {
    override fun getDescription() {
        println("I am an iron door")
    }
}

interface DoorFittingExpert {
    fun getDescription()
}

class Carpenter : DoorFittingExpert {
    override fun getDescription() {
        println("I can only fit wooden doors")
    }
}

class Welder : DoorFittingExpert {
    override fun getDescription() {
        println("I can only fit iron doors")
    }
}

interface DoorFactory {
    fun makeDoor(): Door
    fun makeFittingExpert(): DoorFittingExpert
}

class WoodenDoorFactory : DoorFactory {
    override fun makeDoor(): Door = WoodenDoor()
    override fun makeFittingExpert(): DoorFittingExpert = Carpenter()
}

class IronDoorFactory : DoorFactory {
    override fun makeDoor(): Door = IronDoor()
    override fun makeFittingExpert(): DoorFittingExpert = Welder()
}

// ----------------------------

fun main() {
    val woodenFactory = WoodenDoorFactory()

    val woodenDoor = woodenFactory.makeDoor()
    val woodenExpert = woodenFactory.makeFittingExpert()

    woodenDoor.getDescription()
    woodenExpert.getDescription()

    val ironFactory = IronDoorFactory()

    val ironDoor = ironFactory.makeDoor()
    val ironExpert = ironFactory.makeFittingExpert()

    ironDoor.getDescription()
    ironExpert.getDescription()
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Door {
  void getDescription();
}

class WoodenDoor implements Door {
  @override
  void getDescription() => print('I am a wooden door');
}

class IronDoor implements Door {
  @override
  void getDescription() => print('I am an iron door');
}

abstract class DoorFittingExpert {
  void getDescription();
}

class Carpenter implements DoorFittingExpert {
  @override
  void getDescription() => print('I can only fit wooden doors');
}

class Welder implements DoorFittingExpert {
  @override
  void getDescription() => print('I can only fit iron doors');
}

abstract class DoorFactory {
  Door makeDoor();
  DoorFittingExpert makeFittingExpert();
}

class WoodenDoorFactory implements DoorFactory {
  @override
  Door makeDoor() => WoodenDoor();

  @override
  DoorFittingExpert makeFittingExpert() => Carpenter();
}

class IronDoorFactory implements DoorFactory {
  @override
  Door makeDoor() => IronDoor();

  @override
  DoorFittingExpert makeFittingExpert() => Welder();
}

// ----------------------------

void main() {
  var woodenFactory = WoodenDoorFactory();

  var door = woodenFactory.makeDoor();
  var expert = woodenFactory.makeFittingExpert();

  door.getDescription();
  expert.getDescription();

  var ironFactory = IronDoorFactory();

  door = ironFactory.makeDoor();
  expert = ironFactory.makeFittingExpert();

  door.getDescription();
  expert.getDescription();
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی محصولاتت یه **خانواده هماهنگ** می‌سازن و باید با هم ست بمونن (مثل در چوبی + نجار)، تا یه دفعه قطعه ناجور قاطی نشه؛ ❌ وقتی فقط یه نوع محصول داری یا قرار نیست چند خانواده کنار هم زندگی کنن.
> 🪤 **دام رایج:** خانواده‌ها رو زیادی ریز می‌کنی و کلی کلاس کارخونه می‌سازی که فقط یه محصول می‌ده؛ اونجا داری بی‌خودی پیچیده‌اش می‌کنی.
> 🔗 **فرقش با [فکتوری متد](#فکتوری-متد-factory-method-):** فکتوری متد یه محصول رو می‌سازه، ولی کارخانه انتزاعی یه **خانواده کامل از محصولات مرتبط** رو با هم تحویل می‌ده.


<br>

---

<div align="center">

## بیلدر (Builder) 👷

</div>

<div align="center">
🍔 <b>مثال دنیای واقعی: ساخت ساندویچ سفارشی</b>
</div>

فرض کن رفتی ساندویچ‌فروشی که خودت مواد رو انتخاب می‌کنی (مثل Subway).
تو نمی‌گی «یه ساندویچ بده!» (چون ممکنه توش پیاز باشه و تو ازش متنفر باشی).

بلکه مرحله به مرحله می‌گی:
۱. نون باگت باشه. 🥖
۲. پنیر اضافه بزن. 🧀
۳. گوجه و خیارشور بذار. 🍅
۴. پیاز نذار! 🧅
۵. سس خردل بزن. 🌭

در نهایت ساندویچ مخصوص **خودت** ساخته می‌شه. این دقیقاً کاریه که الگوی **Builder** انجام می‌ده.

💡 **به زبون ساده:**
> دیدی بعضی وقت‌ها یه تابع سازنده (Constructor) داریم که ۱۰ تا ورودی داره و آدم گیج می‌شه کدوم به کدومه؟ 😵‍💫
> (به این مشکل می‌گن "Telescoping Constructor Anti-pattern")
>
> الگوی Builder می‌گه: **«به جای اینکه همه چیز رو یه‌جا بدی دست تابع سازنده، بیا مرحله به مرحله و تمیز آبجکت رو بسازیم.»**

برای همه ما پیش اومده که یه تابع سازنده ترسناک ببینیم؛ از اون‌هایی که آدم رو فراری می‌ده:


<details>
<summary>Python</summary>
<div dir="ltr">

```python
def __init__(self, size, cheese=True, mushrooms=True, tomato=False): ...
```

</div>
</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
constructor(size: number, cheese: boolean = true, mushrooms: boolean = true, tomato: boolean = false) {}
```

</div>
</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
constructor(size, cheese = true, mushrooms = true, tomato = false) {}
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


public Burger(int size, bool cheese, bool mushrooms, bool tomato)

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php

public function __construct(int $size, bool $cheese, bool $mushrooms, bool $tomato)

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

func Burger(size int, cheese bool, mushrooms bool, tomato bool)

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
public Burger(int size, boolean cheese, boolean mushrooms, boolean tomato)
```

</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
class Burger(size: Int, cheese: Boolean, mushrooms: Boolean, tomato: Boolean)
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
class Burger {
  Burger(int size, bool cheese, bool mushrooms, bool tomato);
}
```

</div>
</details>

در این شرایط معمولا Builder می‌تونه به دادمون برسه.

<br>

ویکی‌پدیا:

<div dir="ltr">

> The builder pattern is an object creation software design pattern with the intentions of finding a solution to the
> telescoping constructor anti-pattern.

</div>

خلاصه‌اش این می‌شه که Builder یه الگوی ساخت آبجکته. اومده مشکل «تابع سازنده تلسکوپی (Telescoping Constructor)» رو حل کنه؛ یعنی همون تابع سازنده‌ای که هی ورودی اختیاری بهش اضافه می‌شه و شلوغ‌پلوغ می‌شه. به جاش، آبجکت رو قدم‌به‌قدم و خوانا می‌سازیم.

<br>

**مثال برنامه‌نویسی**

این‌جا هم می‌خوام همون مثال برگر رو با کد برات پیاده کنم.

اولین قدم اینه که یه کلاس برگر معمولی داشته باشیم.

بعدش کلاس Builder رو هم براش می‌سازیم.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Burger:
    def __init__(self, builder):
        self.size = builder.size
        self.cheese = builder.cheese
        self.mushrooms = builder.mushrooms
        self.tomato = builder.tomato

    def get_description(self):
        return (
            f"Burger: size {self.size}, cheese: {str(self.cheese).lower()}, "
            f"mushrooms: {str(self.mushrooms).lower()}, tomato: {str(self.tomato).lower()}"
        )


class BurgerBuilder:
    def __init__(self, size):
        self.size = size
        self.cheese = False
        self.mushrooms = False
        self.tomato = False

    def add_cheese(self):
        self.cheese = True
        return self

    def add_mushrooms(self):
        self.mushrooms = True
        return self

    def add_tomato(self):
        self.tomato = True
        return self

    def build(self):
        return Burger(self)


# ----------------------------

burger = BurgerBuilder(14).add_cheese().add_mushrooms().build()

print(burger.get_description())
# Burger: size 14, cheese: true, mushrooms: true, tomato: false
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class Burger {
    private size: number;
    private cheese: boolean;
    private mushrooms: boolean;
    private tomato: boolean;

    constructor(builder: BurgerBuilder) {
        this.size = builder.size;
        this.cheese = builder.cheese;
        this.mushrooms = builder.mushrooms;
        this.tomato = builder.tomato;
    }

    getDescription(): string {
        return `Burger: size ${this.size}, cheese: ${this.cheese}, ` +
            `mushrooms: ${this.mushrooms}, tomato: ${this.tomato}`;
    }
}

class BurgerBuilder {
    size: number;
    cheese: boolean = false;
    mushrooms: boolean = false;
    tomato: boolean = false;

    constructor(size: number) {
        this.size = size;
    }

    addCheese(): this {
        this.cheese = true;
        return this;
    }

    addMushrooms(): this {
        this.mushrooms = true;
        return this;
    }

    addTomato(): this {
        this.tomato = true;
        return this;
    }

    build(): Burger {
        return new Burger(this);
    }
}

// ----------------------------

const burger = new BurgerBuilder(14)
    .addCheese()
    .addMushrooms()
    .build();

console.log(burger.getDescription());
// Burger: size 14, cheese: true, mushrooms: true, tomato: false
```

</div>
</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class Burger {
    constructor(builder) {
        this.size = builder.size;
        this.cheese = builder.cheese;
        this.mushrooms = builder.mushrooms;
        this.tomato = builder.tomato;
    }

    getDescription() {
        return `Burger: size ${this.size}, cheese: ${this.cheese}, ` +
            `mushrooms: ${this.mushrooms}, tomato: ${this.tomato}`;
    }
}

class BurgerBuilder {
    constructor(size) {
        this.size = size;
        this.cheese = false;
        this.mushrooms = false;
        this.tomato = false;
    }

    addCheese() {
        this.cheese = true;
        return this;
    }

    addMushrooms() {
        this.mushrooms = true;
        return this;
    }

    addTomato() {
        this.tomato = true;
        return this;
    }

    build() {
        return new Burger(this);
    }
}

// ----------------------------

const burger = new BurgerBuilder(14)
    .addCheese()
    .addMushrooms()
    .build();

console.log(burger.getDescription());
// Burger: size 14, cheese: true, mushrooms: true, tomato: false
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;
using System.Text;

class Burger
{
  private int mSize;
  private bool mCheese;
  private bool mMushrooms;
  private bool mTomato;

  public Burger(BurgerBuilder builder)
  {
    this.mSize = builder.Size;
    this.mCheese = builder.Cheese;
    this.mMushrooms = builder.Mushrooms;
    this.mTomato = builder.Tomato;
  }

  public string GetDescription()
  {
    var sb = new StringBuilder();
    sb.Append($"Burger: size {this.mSize}, ");
    sb.Append($"cheese: {this.mCheese.ToString().ToLower()}, ");
    sb.Append($"mushrooms: {this.mMushrooms.ToString().ToLower()}, ");
    sb.Append($"tomato: {this.mTomato.ToString().ToLower()}");
    return sb.ToString();
  }
}

class BurgerBuilder {
  public int Size;
  public bool Cheese;
  public bool Mushrooms;
  public bool Tomato;

  public BurgerBuilder(int size)
  {
    this.Size = size;
  }

  public BurgerBuilder AddCheese()
  {
    this.Cheese = true;
    return this;
  }

  public BurgerBuilder AddMushrooms()
  {
    this.Mushrooms = true;
    return this;
  }

  public BurgerBuilder AddTomato()
  {
    this.Tomato = true;
    return this;
  }

  public Burger Build()
  {
    return new Burger(this);
  }
}

// ----------------------------

var burger = new BurgerBuilder(14)
                .AddCheese()
                .AddMushrooms()
                .Build();
Console.WriteLine(burger.GetDescription());
// Burger: size 14, cheese: true, mushrooms: true, tomato: false

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
class Burger {
    private $size;
    private $cheese = false;
    private $mushrooms = false;
    private $tomato = false;

    public function __construct($builder) {
        $this->size = $builder->size;
        $this->cheese = $builder->cheese;
        $this->mushrooms = $builder->mushrooms;
        $this->tomato = $builder->tomato;
    }

    public function getDescription() {
        $cheese = $this->cheese ? 'true' : 'false';
        $mushrooms = $this->mushrooms ? 'true' : 'false';
        $tomato = $this->tomato ? 'true' : 'false';
        return "Burger: size {$this->size}, cheese: {$cheese}, "
            . "mushrooms: {$mushrooms}, tomato: {$tomato}";
    }
}

class BurgerBuilder {
    public $size;
    public $cheese = false;
    public $mushrooms = false;
    public $tomato = false;

    public function __construct($size) {
        $this->size = $size;
    }

    public function addCheese() {
        $this->cheese = true;
        return $this;
    }

    public function addMushrooms() {
        $this->mushrooms = true;
        return $this;
    }

    public function addTomato() {
        $this->tomato = true;
        return $this;
    }

    public function build() {
        return new Burger($this);
    }
}

$burger = (new BurgerBuilder(14))
            ->addCheese()
            ->addMushrooms()
            ->build();

echo $burger->getDescription() . "\n";
// Burger: size 14, cheese: true, mushrooms: true, tomato: false

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import (
	"fmt"
)

type Burger struct {
	Size      int
	Cheese    bool
	Mushrooms bool
	Tomato    bool
}

func NewBurger(builder *BurgerBuilder) *Burger {
	return &Burger{
		Size:      builder.Size,
		Cheese:    builder.Cheese,
		Mushrooms: builder.Mushrooms,
		Tomato:    builder.Tomato,
	}
}

func (b *Burger) GetDescription() string {
	return fmt.Sprintf("Burger: size %d, cheese: %t, mushrooms: %t, tomato: %t",
		b.Size, b.Cheese, b.Mushrooms, b.Tomato)
}

type BurgerBuilder struct {
	Size      int
	Cheese    bool
	Mushrooms bool
	Tomato    bool
}

func NewBurgerBuilder(size int) *BurgerBuilder {
	return &BurgerBuilder{Size: size}
}

func (b *BurgerBuilder) AddCheese() *BurgerBuilder {
	b.Cheese = true
	return b
}

func (b *BurgerBuilder) AddMushrooms() *BurgerBuilder {
	b.Mushrooms = true
	return b
}

func (b *BurgerBuilder) AddTomato() *BurgerBuilder {
	b.Tomato = true
	return b
}

func (b *BurgerBuilder) Build() *Burger {
	return NewBurger(b)
}

func main() {
	burger := NewBurgerBuilder(14).AddCheese().AddMushrooms().Build()
	fmt.Println(burger.GetDescription())
	// Burger: size 14, cheese: true, mushrooms: true, tomato: false
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class Burger {
    private int size;
    private boolean cheese;
    private boolean mushrooms;
    private boolean tomato;

    public Burger(BurgerBuilder builder) {
        this.size = builder.size;
        this.cheese = builder.cheese;
        this.mushrooms = builder.mushrooms;
        this.tomato = builder.tomato;
    }

    public String getDescription() {
        return "Burger: size " + this.size
                + ", cheese: " + this.cheese
                + ", mushrooms: " + this.mushrooms
                + ", tomato: " + this.tomato;
    }
}

class BurgerBuilder {
    public int size;
    public boolean cheese;
    public boolean mushrooms;
    public boolean tomato;

    public BurgerBuilder(int size) {
        this.size = size;
    }

    public BurgerBuilder addCheese() {
        this.cheese = true;
        return this;
    }

    public BurgerBuilder addMushrooms() {
        this.mushrooms = true;
        return this;
    }

    public BurgerBuilder addTomato() {
        this.tomato = true;
        return this;
    }

    public Burger build() {
        return new Burger(this);
    }
}

// ----------------------------

Burger burger = new BurgerBuilder(14)
        .addCheese()
        .addMushrooms()
        .build();

System.out.println(burger.getDescription());
// Burger: size 14, cheese: true, mushrooms: true, tomato: false
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <memory>

class BurgerBuilder;

class Burger {
private:
    int size;
    bool cheese;
    bool mushrooms;
    bool tomato;

public:
    Burger(int size, bool cheese, bool mushrooms, bool tomato)
        : size(size), cheese(cheese), mushrooms(mushrooms), tomato(tomato) {}

    std::string getDescription() const {
        auto b = [](bool v) { return v ? "true" : "false"; };
        return "Burger: size " + std::to_string(size) +
               ", cheese: " + b(cheese) +
               ", mushrooms: " + b(mushrooms) +
               ", tomato: " + b(tomato);
    }
};

class BurgerBuilder {
private:
    int size;
    bool cheese = false;
    bool mushrooms = false;
    bool tomato = false;

public:
    explicit BurgerBuilder(int size) : size(size) {}

    BurgerBuilder& addCheese() {
        this->cheese = true;
        return *this;
    }

    BurgerBuilder& addMushrooms() {
        this->mushrooms = true;
        return *this;
    }

    BurgerBuilder& addTomato() {
        this->tomato = true;
        return *this;
    }

    std::unique_ptr<Burger> build() {
        return std::make_unique<Burger>(size, cheese, mushrooms, tomato);
    }
};

// ----------------------------

int main() {
    auto burger = BurgerBuilder(14)
        .addCheese()
        .addMushrooms()
        .build();

    std::cout << burger->getDescription() << std::endl;
    // Burger: size 14, cheese: true, mushrooms: true, tomato: false

    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
class Burger(builder: BurgerBuilder) {
    private val size: Int = builder.size
    private val cheese: Boolean = builder.cheese
    private val mushrooms: Boolean = builder.mushrooms
    private val tomato: Boolean = builder.tomato

    fun getDescription(): String {
        return "Burger: size $size, cheese: $cheese, " +
            "mushrooms: $mushrooms, tomato: $tomato"
    }
}

class BurgerBuilder(val size: Int) {
    var cheese: Boolean = false
    var mushrooms: Boolean = false
    var tomato: Boolean = false

    fun addCheese(): BurgerBuilder {
        cheese = true
        return this
    }

    fun addMushrooms(): BurgerBuilder {
        mushrooms = true
        return this
    }

    fun addTomato(): BurgerBuilder {
        tomato = true
        return this
    }

    fun build(): Burger {
        return Burger(this)
    }
}

// ----------------------------

fun main() {
    val burger = BurgerBuilder(14)
        .addCheese()
        .addMushrooms()
        .build()

    println(burger.getDescription())
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
class Burger {
  final int size;
  final bool cheese;
  final bool mushrooms;
  final bool tomato;

  Burger(BurgerBuilder builder)
      : size = builder.size,
        cheese = builder.cheese,
        mushrooms = builder.mushrooms,
        tomato = builder.tomato;

  String getDescription() {
    return 'Burger: size $size, cheese: $cheese, '
        'mushrooms: $mushrooms, tomato: $tomato';
  }
}

class BurgerBuilder {
  final int size;
  bool cheese = false;
  bool mushrooms = false;
  bool tomato = false;

  BurgerBuilder(this.size);

  BurgerBuilder addCheese() {
    cheese = true;
    return this;
  }

  BurgerBuilder addMushrooms() {
    mushrooms = true;
    return this;
  }

  BurgerBuilder addTomato() {
    tomato = true;
    return this;
  }

  Burger build() => Burger(this);
}

// ----------------------------

void main() {
  var burger = BurgerBuilder(14).addCheese().addMushrooms().build();

  print(burger.getDescription());
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی ساختن یه آبجکت کلی گزینه اختیاری داره و می‌خوای قدم‌به‌قدم و خوانا بسازیش»؛ ❌ «وقتی آبجکتت دو سه تا فیلد ساده داره و یه تابع سازنده معمولی کافیه».
> 🪤 **دام رایج:** «build() رو صدا نزنی و با خود Builder کار کنی، یا فیلدهای اجباری رو نگیری و آبجکت نصفه‌نیمه بسازی».
> 🔗 **فرقش با الگوهای دیگه:** «Builder یه آبجکت رو مرحله‌به‌مرحله می‌سازه، نه اینکه بین چند نوع آبجکت آماده انتخاب کنه».


<br>

---

<div align="center">

## نمونه اولیه (Prototype) 🐑

</div>

<div align="center">
🧬 <b>مثال دنیای واقعی: کپی گرفتن از یه سند آماده</b>
</div>

فرض کن یه فایل ورد داری که کلی روش وقت گذاشتی؛ حاشیه و فونت و استایل، همه چی تنظیم شده. حالا برای یه سند جدید، از صفر شروع نمی‌کنی. همون فایل رو **Copy/Paste** می‌کنی و فقط متنش رو عوض می‌کنی. این دقیقاً همون کاریه که این پترن می‌کنه؛ به جای ساختن از صفر، از روی یه نمونه آماده یه **کپی** (Clone) می‌گیری.

توی دنیای کامپیوتر هم خیلی وقتا پیش میاد که ساختن یه آبجکت از صفر خیلی هزینه داره (مثلاً باید کلی به دیتابیس کوئری بزنیم تا ساخته بشه).
به جای اینکه هر دفعه این مسیر سخت رو بریم، میایم از روی یه نمونه آماده (Prototype) یه کپی می‌گیریم. مثل دستور **Copy/Paste**.

💡 **به زبون ساده:**
> این پترن می‌گه: **«به جای اینکه بگی `new` و همه چیز رو از اول بسازی، از روی یکی که داری یه `clone` بگیر.»**
> (مخصوصاً وقتی ساختن آبجکت خیلی زمان‌بر یا پیچیده باشه).

ویکی‌پدیا:

<div dir="ltr">

> The prototype pattern is a creational design pattern in software development. It is used when the type of objects to
> create is determined by a prototypical instance, which is cloned to produce new objects.

</div>

به زبون خودمون: پترن نمونه اولیه (Prototype) یه پترن سازنده (Creational) هست. وقتی به دردت می‌خوره که یه نمونه آماده داری و نوعِ آبجکت جدیدت رو هم همون مشخص می‌کنه؛ پس به جای ساختن از صفر، از روی همون نمونه یه کپی (Clone) می‌گیری و آبجکت جدیدت آماده‌ست.

**مثال برنامه‌نویسی**

فرض کن یه کلاس Person داریم که یه اسم داره و یه آبجکت تو در توی Address که شهر طرف توش نگه‌داری می‌شه.

می‌خوایم دو جور کپی ازش بگیریم؛ یه کپی سطحی (Shallow Copy) و یه کپی عمیق (Deep Copy)، تا فرقشون رو زنده ببینی.

<details>
<summary>Python</summary>

پایتون magic method‌هایی برای این مسئله در نظر گرفته که ما هم از همون دو تابع معروف copy و deep copy استفاده می‌کنیم:

<div dir="ltr">

```python
import copy


class Address:
    def __init__(self, city):
        self.city = city


class Person:
    def __init__(self, name, address):
        self.name = name
        self.address = address  # nested mutable object

    def __copy__(self):
        # Shallow copy: new Person, but the SAME Address object is shared
        return Person(self.name, self.address)

    def __deepcopy__(self, memo):
        # Deep copy: the nested Address is copied too, so it is independent
        return Person(self.name, copy.deepcopy(self.address, memo))


# Shallow clone: shares the nested Address
original = Person("Sara", Address("Tehran"))
shallow = copy.copy(original)
shallow.address.city = "Shiraz"
print(shallow.address.city)    # Shiraz
print(original.address.city)   # Shiraz  -> the original changed too (shared Address)

# Deep clone: gets its own Address
original = Person("Sara", Address("Tehran"))
deep = copy.deepcopy(original)
deep.address.city = "Shiraz"
print(deep.address.city)       # Shiraz
print(original.address.city)   # Tehran  -> the original stayed the same
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class Address {
    city: string;

    constructor(city: string) {
        this.city = city;
    }
}

class Person {
    name: string;
    address: Address; // nested mutable object

    constructor(name: string, address: Address) {
        this.name = name;
        this.address = address;
    }

    // Shallow copy: new Person, but the SAME Address object is shared
    shallowCopy(): Person {
        return new Person(this.name, this.address);
    }

    // Deep copy: the nested Address is copied too, so it is independent
    deepCopy(): Person {
        return new Person(this.name, new Address(this.address.city));
    }
}

// Shallow clone: shares the nested Address
let original = new Person("Sara", new Address("Tehran"));
let shallow = original.shallowCopy();
shallow.address.city = "Shiraz";
console.log(shallow.address.city);    // Shiraz
console.log(original.address.city);   // Shiraz  -> the original changed too (shared Address)

// Deep clone: gets its own Address
original = new Person("Sara", new Address("Tehran"));
let deep = original.deepCopy();
deep.address.city = "Shiraz";
console.log(deep.address.city);       // Shiraz
console.log(original.address.city);   // Tehran  -> the original stayed the same
```

</div>
</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class Address {
    constructor(city) {
        this.city = city;
    }
}

class Person {
    constructor(name, address) {
        this.name = name;
        this.address = address; // nested mutable object
    }

    // Shallow copy: new Person, but the SAME Address object is shared
    shallowCopy() {
        return new Person(this.name, this.address);
    }

    // Deep copy: the nested Address is copied too, so it is independent
    deepCopy() {
        return new Person(this.name, new Address(this.address.city));
    }
}

// Shallow clone: shares the nested Address
let original = new Person("Sara", new Address("Tehran"));
let shallow = original.shallowCopy();
shallow.address.city = "Shiraz";
console.log(shallow.address.city);    // Shiraz
console.log(original.address.city);   // Shiraz  -> the original changed too (shared Address)

// Deep clone: gets its own Address
original = new Person("Sara", new Address("Tehran"));
let deep = original.deepCopy();
deep.address.city = "Shiraz";
console.log(deep.address.city);       // Shiraz
console.log(original.address.city);   // Tehran  -> the original stayed the same
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

using System;

public class Address
{
    public string City;

    public Address(string city)
    {
        City = city;
    }
}

public class Person
{
    public string Name;
    public Address Address; // nested mutable object

    public Person(string name, Address address)
    {
        Name = name;
        Address = address;
    }

    // Shallow copy: MemberwiseClone keeps the SAME Address reference (shared)
    public Person ShallowCopy()
    {
        return (Person)this.MemberwiseClone();
    }

    // Deep copy: also copy the nested Address, so it is independent
    public Person DeepCopy()
    {
        Person clone = (Person)this.MemberwiseClone();
        clone.Address = new Address(this.Address.City);
        return clone;
    }
}

public class Program
{
    public static void Main()
    {
        // Shallow clone: shares the nested Address
        Person original = new Person("Sara", new Address("Tehran"));
        Person shallow = original.ShallowCopy();
        shallow.Address.City = "Shiraz";
        Console.WriteLine(shallow.Address.City);    // Shiraz
        Console.WriteLine(original.Address.City);   // Shiraz  -> the original changed too (shared Address)

        // Deep clone: gets its own Address
        original = new Person("Sara", new Address("Tehran"));
        Person deep = original.DeepCopy();
        deep.Address.City = "Shiraz";
        Console.WriteLine(deep.Address.City);       // Shiraz
        Console.WriteLine(original.Address.City);   // Tehran  -> the original stayed the same
    }
}

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
class Address
{
    public string $city;

    public function __construct(string $city)
    {
        $this->city = $city;
    }
}

class Person
{
    public string $name;
    public Address $address; // nested mutable object

    public function __construct(string $name, Address $address)
    {
        $this->name = $name;
        $this->address = $address;
    }

    // Shallow copy: clone keeps the SAME Address object (shared)
    public function shallowCopy(): Person
    {
        return clone $this;
    }

    // Deep copy: also copy the nested Address, so it is independent
    public function deepCopy(): Person
    {
        $clone = clone $this;
        $clone->address = new Address($this->address->city);
        return $clone;
    }
}

// Shallow clone: shares the nested Address
$original = new Person("Sara", new Address("Tehran"));
$shallow = $original->shallowCopy();
$shallow->address->city = "Shiraz";
echo $shallow->address->city . "\n";    // Shiraz
echo $original->address->city . "\n";   // Shiraz  -> the original changed too (shared Address)

// Deep clone: gets its own Address
$original = new Person("Sara", new Address("Tehran"));
$deep = $original->deepCopy();
$deep->address->city = "Shiraz";
echo $deep->address->city . "\n";       // Shiraz
echo $original->address->city . "\n";   // Tehran  -> the original stayed the same

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Address struct {
	City string
}

type Person struct {
	Name    string
	Address *Address // nested mutable object
}

// Shallow copy: new Person, but the SAME Address pointer is shared
func (p *Person) ShallowCopy() *Person {
	return &Person{Name: p.Name, Address: p.Address}
}

// Deep copy: the nested Address is copied too, so it is independent
func (p *Person) DeepCopy() *Person {
	return &Person{Name: p.Name, Address: &Address{City: p.Address.City}}
}

func main() {
	// Shallow clone: shares the nested Address
	original := &Person{Name: "Sara", Address: &Address{City: "Tehran"}}
	shallow := original.ShallowCopy()
	shallow.Address.City = "Shiraz"
	fmt.Println(shallow.Address.City)  // Shiraz
	fmt.Println(original.Address.City) // Shiraz  -> the original changed too (shared Address)

	// Deep clone: gets its own Address
	original = &Person{Name: "Sara", Address: &Address{City: "Tehran"}}
	deep := original.DeepCopy()
	deep.Address.City = "Shiraz"
	fmt.Println(deep.Address.City)     // Shiraz
	fmt.Println(original.Address.City) // Tehran  -> the original stayed the same
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class Address {
    String city;

    Address(String city) {
        this.city = city;
    }
}

class Person {
    String name;
    Address address; // nested mutable object

    Person(String name, Address address) {
        this.name = name;
        this.address = address;
    }

    // Shallow copy: new Person, but the SAME Address object is shared
    Person shallowCopy() {
        return new Person(this.name, this.address);
    }

    // Deep copy: the nested Address is copied too, so it is independent
    Person deepCopy() {
        return new Person(this.name, new Address(this.address.city));
    }
}

public class Proto {
    public static void main(String[] args) {
        // Shallow clone: shares the nested Address
        Person original = new Person("Sara", new Address("Tehran"));
        Person shallow = original.shallowCopy();
        shallow.address.city = "Shiraz";
        System.out.println(shallow.address.city);    // Shiraz
        System.out.println(original.address.city);   // Shiraz  -> the original changed too (shared Address)

        // Deep clone: gets its own Address
        original = new Person("Sara", new Address("Tehran"));
        Person deep = original.deepCopy();
        deep.address.city = "Shiraz";
        System.out.println(deep.address.city);       // Shiraz
        System.out.println(original.address.city);   // Tehran  -> the original stayed the same
    }
}
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <memory>

class Address {
public:
    std::string city;
    Address(const std::string& city) : city(city) {}
};

class Person {
public:
    std::string name;
    std::shared_ptr<Address> address; // nested mutable object

    Person(const std::string& name, std::shared_ptr<Address> address)
        : name(name), address(address) {}

    // Shallow copy: new Person, but the SAME Address object is shared
    Person shallowCopy() const {
        return Person(name, address);
    }

    // Deep copy: the nested Address is copied too, so it is independent
    Person deepCopy() const {
        return Person(name, std::make_shared<Address>(address->city));
    }
};

int main() {
    // Shallow clone: shares the nested Address
    Person original("Sara", std::make_shared<Address>("Tehran"));
    Person shallow = original.shallowCopy();
    shallow.address->city = "Shiraz";
    std::cout << shallow.address->city << std::endl;   // Shiraz
    std::cout << original.address->city << std::endl;  // Shiraz  -> the original changed too (shared Address)

    // Deep clone: gets its own Address
    original = Person("Sara", std::make_shared<Address>("Tehran"));
    Person deep = original.deepCopy();
    deep.address->city = "Shiraz";
    std::cout << deep.address->city << std::endl;      // Shiraz
    std::cout << original.address->city << std::endl;  // Tehran  -> the original stayed the same

    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
class Address(var city: String)

class Person(val name: String, val address: Address) { // nested mutable object
    // Shallow copy: new Person, but the SAME Address object is shared
    fun shallowCopy(): Person {
        return Person(name, address)
    }

    // Deep copy: the nested Address is copied too, so it is independent
    fun deepCopy(): Person {
        return Person(name, Address(address.city))
    }
}

// ----------------------------

fun main() {
    // Shallow clone: shares the nested Address
    var original = Person("Sara", Address("Tehran"))
    val shallow = original.shallowCopy()
    shallow.address.city = "Shiraz"
    println(shallow.address.city)    // Shiraz
    println(original.address.city)   // Shiraz  -> the original changed too (shared Address)

    // Deep clone: gets its own Address
    original = Person("Sara", Address("Tehran"))
    val deep = original.deepCopy()
    deep.address.city = "Shiraz"
    println(deep.address.city)       // Shiraz
    println(original.address.city)   // Tehran  -> the original stayed the same
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
class Address {
  String city;

  Address(this.city);
}

class Person {
  String name;
  Address address; // nested mutable object

  Person(this.name, this.address);

  // Shallow copy: new Person, but the SAME Address object is shared
  Person shallowCopy() {
    return Person(name, address);
  }

  // Deep copy: the nested Address is copied too, so it is independent
  Person deepCopy() {
    return Person(name, Address(address.city));
  }
}

// ----------------------------

void main() {
  // Shallow clone: shares the nested Address
  var original = Person('Sara', Address('Tehran'));
  var shallow = original.shallowCopy();
  shallow.address.city = 'Shiraz';
  print(shallow.address.city);    // Shiraz
  print(original.address.city);   // Shiraz  -> the original changed too (shared Address)

  // Deep clone: gets its own Address
  original = Person('Sara', Address('Tehran'));
  var deep = original.deepCopy();
  deep.address.city = 'Shiraz';
  print(deep.address.city);       // Shiraz
  print(original.address.city);   // Tehran  -> the original stayed the same
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی ساختن آبجکت از صفر گرونه، و یه نمونه آماده داری که فقط می‌خوای ازش کپی بگیری»؛ ❌ «وقتی آبجکت ساده‌ست و ساختن دوباره‌ش هیچ هزینه‌ای نداره».
> 🪤 **دام رایج:** «کپی سطحی می‌گیری و یادت می‌ره فیلدهای تو در توش هنوز مشترکن؛ بعد تغییر کپی، اصلی رو هم خراب می‌کنه».
> 🔗 **فرقش با کارخانه:** نمونه اولیه از روی یه آبجکت موجود کپی می‌گیره، ولی کارخانه هر بار یه آبجکت تازه از صفر می‌سازه.


<br>

**تفاوت کپی سطحی (Shallow Copy) و کپی عمیق (Deep Copy) چیه؟**
<br>
توی کپی سطحی (Shallow Copy)، یه آبجکت جدید ساخته می‌شه، ولی فیلدهای تو در توش (مثل همون Address توی مثال) کپی نمی‌شن؛ هر دو آبجکت به یه آدرس مشترک توی حافظه اشاره می‌کنن. پس اگه شهرِ اون Address رو از روی کپی عوض کنی، چون آبجکت Address یکی‌ه، آبجکت اصلی هم تغییر می‌کنه.

ولی توی کپی عمیق (Deep Copy)، اون آبجکت تو در تو هم جدا کپی می‌شه. در نتیجه هر کدوم Address خودشون رو دارن و تغییر یکی هیچ اثری روی اون یکی نمی‌ذاره.

<br>

<div align="center">

## تک‌نمونه (Singleton) 💍

</div>

<div align="center">
👑 <b>مثال دنیای واقعی: رئیس‌جمهور</b>
</div>

توی یک کشور، نمی‌شه ۱۰ تا رئیس‌جمهور داشت! 🏛️
همیشه **فقط و فقط یک** رئیس‌جمهور وجود داره. هر وقت هر کسی (از هر وزارتخونه‌ای) با رئیس‌جمهور کار داره، باید به همون **یک نفر واحد** مراجعه کنه، نه اینکه بره برای خودش یه رئیس‌جمهور جدید بسازه!

💡 **به زبون ساده:**
> این پترن تضمین می‌کنه که از یه کلاس، **فقط یه دونه آبجکت** ساخته بشه و همه جای برنامه از همون یکی استفاده کنن. (مثلاً برای کانکشن دیتابیس).

⚠️ **هشدار:**
> دیزاین پترن Singleton یه جورایی «آنتی پترن» (ضد الگو) هم حساب می‌شه! چون مثل «متغیر سراسری» (Global Variable) عمل می‌کنه و اگه زیاده‌روی کنی، تست نوشتن و دیباگ کردن پروژه رو تبدیل به کابوس می‌کنه. پس با احتیاط مصرفش کن! 💊

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a
> class to one object. This is useful when exactly one object is needed to coordinate actions across the system.

</div>

خلاصه‌اش این می‌شه که الگوی تک‌نمونه (Singleton) ساختن آبجکت از یه کلاس رو به فقط یه دونه محدود می‌کنه. این وقتی به درد می‌خوره که دقیقاً یه آبجکت لازم داری تا کارهای کل سیستم رو هماهنگ کنه.

<br>

**مثال برنامه‌نویسی**

معمولاً برای ساختن singleton سه کار می‌کنی: تابع سازنده رو private می‌کنی، جلوی clone و copy رو می‌گیری، و یه تابع استاتیک می‌ذاری که آبجکت رو بسازه.

ولی توی پایتون یه راه‌حل ساده‌تر هست و اون هم استفاده از metaclassهاست:

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class SingletonMeta(type):
    _instances = {}

    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]


class President(metaclass=SingletonMeta):
    pass


if __name__ == "__main__":
    # The client code.

    a = President()
    b = President()

    print("Same instance?", "True" if a is b else "False")
    # Output: Same instance? True
```

</div>

این روش لزوماً Thread Safe نیست؛ یعنی اگه چند نخ (Thread، یعنی چند مسیر اجرای هم‌زمان) اولین بار با هم اولین نمونه رو بسازن، شاید بیشتر از یه نمونه درست بشه. تو محیط چندنخی باید با یه قفل (Lock) جلوش رو بگیری.

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class President {
    private static instance: President;

    private constructor() {
        // Private constructor prevents direct instantiation
    }

    public static getInstance(): President {
        if (!President.instance) {
            President.instance = new President();
        }
        return President.instance;
    }
}

// ----------------------------

const a = President.getInstance();
const b = President.getInstance();

console.log("Same instance?", Object.is(a, b) ? "True" : "False");
// Output: Same instance? True
```

</div>

</details>

<details>
<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class President {
    static #instance;

    static getInstance() {
        if (!President.#instance) {
            President.#instance = new President();
        }
        return President.#instance;
    }
}

const a = President.getInstance();
const b = President.getInstance();

console.log("Same instance?", Object.is(a, b) ? "True" : "False");
// Output: Same instance? True
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


public class President
{
  static President instance;

  // Private constructor hides direct instantiation
  private President()
  {
  }

  public static President GetInstance()
  {
    if (instance == null) {
      instance = new President();
    }
    return instance;
  }
}

// ----------------------------

President a = President.GetInstance();
President b = President.GetInstance();

Console.WriteLine($"Same instance? {(a == b ? "True" : "False")}");
// Output: Same instance? True

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php

class President
{
  private static $instance;

  private function __construct()
  {
    // Hiding the Constructor
  }

  public static function getInstance()
  {
    if (self::$instance == null) {
      self::$instance = new President();
    }
    return self::$instance;
  }
}

$a = President::getInstance();
$b = President::getInstance();

echo "Same instance? " . ($a === $b ? "True" : "False") . "\n";
// Output: Same instance? True

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
type President struct{}

var instance *President

func GetInstance() *President {
  if instance == nil {
    instance = &President{}
  }
  return instance
}

// -----------------------

a := GetInstance()
b := GetInstance()

same := "False"
if a == b {
  same = "True"
}
fmt.Println("Same instance?", same)
// Output: Same instance? True


```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class President {
    private static President instance;
    // Private constructor
    private President() {
        // Hiding the Constructor
    }

    public static President getInstance() {
        if (instance == null) {
            instance = new President();
        }
        return instance;
    }
}

// ----------------------------

President a = President.getInstance();
President b = President.getInstance();

System.out.println("Same instance? " + (a == b ? "True" : "False"));
// Output: Same instance? True
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

class President {
private:
    // Private constructor
    President() = default;

    // Delete copy constructor and assignment operator
    President(const President&) = delete;
    President& operator=(const President&) = delete;

public:
    // Thread-safe in C++11 and later (Meyers singleton)
    static President& getInstance() {
        static President instance;
        return instance;
    }
};

int main() {
    President& a = President::getInstance();
    President& b = President::getInstance();

    std::cout << "Same instance? " << (&a == &b ? "True" : "False") << std::endl;
    // Output: Same instance? True
    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
object President {
    // The single instance is the object itself
}

// ----------------------------

fun main() {
    val a = President
    val b = President

    println("Same instance? " + if (a === b) "True" else "False")
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
class President {
  static final President _instance = President._internal();

  President._internal();

  factory President() {
    return _instance;
  }
}

// ----------------------------

void main() {
  var a = President();
  var b = President();

  print("Same instance? ${identical(a, b) ? "True" : "False"}");
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی واقعاً باید توی کل برنامه فقط یه نمونه از یه چیز وجود داشته باشه، مثل تنظیمات سراسری یا یه مخزنِ اتصال‌ها (Connection Pool)»؛ ❌ «وقتی فقط برای راحتیِ دسترسی می‌خوای همه‌جا بهش برسی، که اون‌وقت داری متغیر سراسری (Global Variable) می‌سازی».
> 🪤 **دام رایج:** «حالت مشترک و قابل‌تغییرِ تک‌نمونه، تست‌ها رو به هم وابسته می‌کنه و توی برنامه‌های چندنخی (Multithreaded) دردسر می‌سازه».


<br>
<br>

---

<br>

<div align="center">

# الگوهای ساختاری (Structural Design Patterns) 🧰

</div>

به زبون ساده:

> به‌طور کلی الگوهای طراحی ساختاری با رابطه بین چیزها و کنار هم چیدنشون کار دارن.

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, structural design patterns are design patterns that ease the design by identifying a simple
> way to realize relationships between entities.

</div>

خلاصه: الگوهای ساختاری کمک می‌کنن کلاس‌ها و آبجکت‌ها رو طوری کنار هم بچینی که رابطه‌هاشون ساده و سرراست بمونه.

<br>

---

<div align="center">

## مبدل (Adapter) 🔌

</div>

<div align="center">
🔌 <b>مثال دنیای واقعی: تبدیل دوشاخه برق</b>
</div>

فرض کن رفتی سفر خارج (مثلاً آمریکا). لپ‌تاپت شارژش تموم شده و می‌خوای بزنی به برق.
اما ای داد بیداد! 😱 پریزهای اونجا سه شاخه‌ست، ولی شارژر تو دو شاخه‌ست.

شارژر تو (کلاینت) نمی‌تونه مستقیم وارد پریز (سرویس) بشه.
اینجا چیکار می‌کنی؟ سیم شارژر رو قیچی می‌کنی؟ دیوار رو خراب می‌کنی؟ نه!
می‌ری یه **«مبدل» (Adapter)** می‌خری. مبدل یه سرش به شارژر تو می‌خوره، سر دیگه‌ش به پریز دیوار.

💡 **به زبون ساده:**
> آداپتور یعنی: **«وقتی دو تا چیز به هم نمی‌خورن، یه واسطه بذار وسط که اینو به اون وصل کنه، بدون اینکه دست به ترکیب اصلیشون بزنی.»**

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, the adapter pattern is a software design pattern that allows the interface of an existing
> class to be used as another interface. It is often used to make existing classes work with others without modifying
> their source code.

</div>

خلاصه‌ش این می‌شه: آداپتور به تو اجازه می‌ده از یه کلاسِ موجود، انگار که یه اینترفیس دیگه‌ست استفاده کنی.
بیشتر وقتی به کارت میاد که بخوای کلاس‌های آماده رو کنار بقیه به کار بگیری، بدون اینکه کد اصلیشون رو دست بزنی.

**مثال برنامه‌نویسی**

فرض کن یه بازی داریم که توش یه «شکارچی» (`Hunter`) هست که عادت داره «شیر» (`Lion`) شکار کنه.
شکارچی وقتی شیر می‌بینه، انتظار داره شیر «غرش» (`roar`) کنه.

حالا یه «سگ وحشی» (`WildDog`) به بازی اضافه شده. اما سگ‌ها غرش نمی‌کنن، «پارس» (`bark`) می‌کنن.
شکارچی قاطی می‌کنه! چون فقط بلده با متد `roar` کار کنه.

اینجا یه `WildDogAdapter` می‌سازیم. این آداپتور:
1.  از بیرون شبیه `Lion` به نظر میاد (متد `roar` داره).
2.  اما اون پشت، وقتی `roar` صدا زده می‌شه، می‌ره `bark` سگ رو صدا می‌زنه.
اینطوری شکارچی فکر می‌کنه داره شیر شکار می‌کنه، ولی در واقع داره سگ شکار می‌کنه! 😉

برای حلش این‌جوری براش آداپتور می‌سازیم:

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Lion:
    def roar(self) -> str:
        raise NotImplementedError


class AfricanLion(Lion):
    def roar(self) -> str:
        return "Roaaar"


class Hunter:
    def hunt(self, lion: Lion) -> None:
        print("The hunter is hunting...")
        print(lion.roar())


class WildDog:
    def bark(self) -> str:
        return "Woof"


class WildDogAdapter(Lion):
    def __init__(self, dog: WildDog):
        self.dog = dog

    def roar(self) -> str:
        return self.dog.bark()


# ----------------------------

african_lion = AfricanLion()
wild_dog = WildDog()
wild_dog_adapter = WildDogAdapter(wild_dog)

hunter = Hunter()
hunter.hunt(african_lion)       # The hunter is hunting... -> Roaaar
hunter.hunt(wild_dog_adapter)   # The hunter is hunting... -> Woof

# Output:
# The hunter is hunting...
# Roaaar
# The hunter is hunting...
# Woof
```

</div>
این مثال یه‌کم انتزاعیه، ولی مفهوم رو خیلی خوب می‌رسونه.

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface Lion {
    roar(): string;
}

class AfricanLion implements Lion {
    roar(): string {
        return "Roaaar";
    }
}

class Hunter {
    hunt(lion: Lion): void {
        console.log("The hunter is hunting...");
        console.log(lion.roar());
    }
}

class WildDog {
    bark(): string {
        return "Woof";
    }
}

class WildDogAdapter implements Lion {
    private dog: WildDog;

    constructor(dog: WildDog) {
        this.dog = dog;
    }

    roar(): string {
        return this.dog.bark();
    }
}

// ----------------------------

const africanLion = new AfricanLion();
const wildDog = new WildDog();
const wildDogAdapter = new WildDogAdapter(wildDog);

const hunter = new Hunter();
hunter.hunt(africanLion);      // The hunter is hunting... -> Roaaar
hunter.hunt(wildDogAdapter);   // The hunter is hunting... -> Woof

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Lion {
    roar() {
        return "";
    }
}

class AfricanLion extends Lion {
    roar() {
        return "Roaaar";
    }
}

class Hunter {
    hunt(lion) {
        console.log("The hunter is hunting...");
        console.log(lion.roar());
    }
}

class WildDog {
    bark() {
        return "Woof";
    }
}

class WildDogAdapter extends Lion {
    constructor(dog) {
        super();
        this.dog = dog;
    }

    roar() {
        return this.dog.bark();
    }
}

// ----------------------------

const africanLion = new AfricanLion();
const wildDog = new WildDog();
const wildDogAdapter = new WildDogAdapter(wildDog);

const hunter = new Hunter();
hunter.hunt(africanLion);      // The hunter is hunting... -> Roaaar
hunter.hunt(wildDogAdapter);   // The hunter is hunting... -> Woof

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;

interface ILion
{
  string Roar();
}

class AfricanLion : ILion
{
  public string Roar()
  {
    return "Roaaar";
  }
}

class Hunter
{
  public void Hunt(ILion lion)
  {
    Console.WriteLine("The hunter is hunting...");
    Console.WriteLine(lion.Roar());
  }
}

// This needs to be added to the game
class WildDog
{
  public string Bark()
  {
    return "Woof";
  }
}

// Adapter around wild dog to make it compatible with our game
class WildDogAdapter : ILion
{
  private WildDog mDog;
  public WildDogAdapter(WildDog dog)
  {
    this.mDog = dog;
  }
  public string Roar()
  {
    return mDog.Bark();
  }
}

// ----------------------------

var africanLion = new AfricanLion();
var wildDog = new WildDog();
var wildDogAdapter = new WildDogAdapter(wildDog);

var hunter = new Hunter();
hunter.Hunt(africanLion);      // The hunter is hunting... -> Roaaar
hunter.Hunt(wildDogAdapter);   // The hunter is hunting... -> Woof

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php

interface Lion {
    public function roar(): string;
}

class AfricanLion implements Lion {
    public function roar(): string {
        return "Roaaar";
    }
}

class Hunter {
    public function hunt(Lion $lion): void {
        echo "The hunter is hunting...\n";
        echo $lion->roar() . "\n";
    }
}

class WildDog {
    public function bark(): string {
        return "Woof";
    }
}

// Adapter around wild dog to make it compatible with our game
class WildDogAdapter implements Lion
{
    private $mDog;
    public function __construct(WildDog $dog)
    {
        $this->mDog = $dog;
    }
    public function roar(): string
    {
        return $this->mDog->bark();
    }
}

$africanLion = new AfricanLion();
$wildDog = new WildDog();
$wildDogAdapter = new WildDogAdapter($wildDog);

$hunter = new Hunter();
$hunter->hunt($africanLion);      // The hunter is hunting... -> Roaaar
$hunter->hunt($wildDogAdapter);   // The hunter is hunting... -> Woof

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

type Lion interface {
	Roar() string
}

type AfricanLion struct{}

func (a AfricanLion) Roar() string {
	return "Roaaar"
}

type Hunter struct{}

func (h Hunter) Hunt(lion Lion) {
	fmt.Println("The hunter is hunting...")
	fmt.Println(lion.Roar())
}

type WildDog struct{}

func (w WildDog) Bark() string {
	return "Woof"
}

type WildDogAdapter struct {
	dog WildDog
}

func (w WildDogAdapter) Roar() string {
	return w.dog.Bark()
}

func main() {
	africanLion := AfricanLion{}
	wildDog := WildDog{}
	wildDogAdapter := WildDogAdapter{dog: wildDog}

	hunter := Hunter{}
	hunter.Hunt(africanLion)    // The hunter is hunting... -> Roaaar
	hunter.Hunt(wildDogAdapter) // The hunter is hunting... -> Woof
}

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Lion {

    String roar();
}

class AfricanLion implements Lion {

    @Override
    public String roar() {
        return "Roaaar";
    }
}

class Hunter {

    public void hunt(Lion lion) {
        System.out.println("The hunter is hunting...");
        System.out.println(lion.roar());
    }
}

class WildDog {

    public String bark() {
        return "Woof";
    }
}

// Adapter around wild dog to make it compatible
class WildDogAdapter implements Lion {
    private WildDog wildDog;

    public WildDogAdapter(WildDog wildDog) {
        this.wildDog = wildDog;
    }

    @Override
    public String roar() {
        return wildDog.bark();
    }
}

// ----------------------------

AfricanLion africanLion = new AfricanLion();
WildDog wildDog = new WildDog();
WildDogAdapter wildDogAdapter = new WildDogAdapter(wildDog);

Hunter hunter = new Hunter();
hunter.hunt(africanLion);      // The hunter is hunting... -> Roaaar
hunter.hunt(wildDogAdapter);   // The hunter is hunting... -> Woof

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>

// Lion interface
class Lion {
public:
    virtual ~Lion() = default;
    virtual std::string roar() = 0;
};

// African lion
class AfricanLion : public Lion {
public:
    std::string roar() override {
        return "Roaaar";
    }
};

// Hunter
class Hunter {
public:
    void hunt(Lion* lion) {
        std::cout << "The hunter is hunting..." << std::endl;
        std::cout << lion->roar() << std::endl;
    }
};

// Wild dog (incompatible interface)
class WildDog {
public:
    std::string bark() {
        return "Woof";
    }
};

// Adapter to make WildDog compatible with the Lion interface
class WildDogAdapter : public Lion {
private:
    WildDog* dog;

public:
    WildDogAdapter(WildDog* dog) : dog(dog) {}

    std::string roar() override {
        return dog->bark();
    }
};

// Usage
int main() {
    AfricanLion africanLion;
    WildDog wildDog;
    WildDogAdapter wildDogAdapter(&wildDog);

    Hunter hunter;
    hunter.hunt(&africanLion);      // The hunter is hunting... -> Roaaar
    hunter.hunt(&wildDogAdapter);   // The hunter is hunting... -> Woof

    return 0;
}

// Output:
// The hunter is hunting...
// Roaaar
// The hunter is hunting...
// Woof
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Lion {
    fun roar(): String
}

class AfricanLion : Lion {
    override fun roar(): String {
        return "Roaaar"
    }
}

class Hunter {
    fun hunt(lion: Lion) {
        println("The hunter is hunting...")
        println(lion.roar())
    }
}

class WildDog {
    fun bark(): String {
        return "Woof"
    }
}

// Adapter around wild dog to make it compatible
class WildDogAdapter(private val wildDog: WildDog) : Lion {
    override fun roar(): String {
        return wildDog.bark()
    }
}

// ----------------------------

fun main() {
    val africanLion = AfricanLion()
    val wildDog = WildDog()
    val wildDogAdapter = WildDogAdapter(wildDog)

    val hunter = Hunter()
    hunter.hunt(africanLion)
    hunter.hunt(wildDogAdapter)
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Lion {
  String roar();
}

class AfricanLion implements Lion {
  @override
  String roar() {
    return "Roaaar";
  }
}

class Hunter {
  void hunt(Lion lion) {
    print("The hunter is hunting...");
    print(lion.roar());
  }
}

class WildDog {
  String bark() {
    return "Woof";
  }
}

// Adapter around wild dog to make it compatible
class WildDogAdapter implements Lion {
  final WildDog _wildDog;

  WildDogAdapter(this._wildDog);

  @override
  String roar() {
    return _wildDog.bark();
  }
}

// ----------------------------

void main() {
  var africanLion = AfricanLion();
  var wildDog = WildDog();
  var wildDogAdapter = WildDogAdapter(wildDog);

  var hunter = Hunter();
  hunter.hunt(africanLion);
  hunter.hunt(wildDogAdapter);
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یه کلاس کارِتو راه می‌اندازه ولی امضای متدهاش با چیزی که کدت انتظار داره جور نیست»؛ ❌ «وقتی خودت کنترل هر دو طرف رو داری و می‌تونی همون اول اینترفیس رو درست طراحی کنی».
> 🪤 **دام رایج:** «آداپتور رو کم‌کم پر از منطق اضافه می‌کنی تا جایی که از یه واسطه ساده تبدیل می‌شه به یه لایه شلوغ که فهمیدنش سخته».
> 🔗 **فرقش با [پل (Bridge)](#پل-bridge-):** «پل رو از اول طراحی می‌کنی تا انتزاع و پیاده‌سازی مستقل از هم رشد کنن؛ ولی آداپتور بعد از ماجرا میاد که دو تا چیزِ ناسازگارِ موجود رو به هم برسونه. به [پراکسی (Proxy)](#پراکسی-proxy-) و [دکوریتور (Decorator)](#دکوریتور-decorator-) هم نزدیکه، ولی اون‌ها برخلاف آداپتور اینترفیس رو عوض نمی‌کنن».


<br>

---

<div align="center">

## پل (Bridge) 🌉

</div>

<div align="center">
🎨 <b>مثال دنیای واقعی: تم وب‌سایت</b>
</div>

فرض کن یه وب‌سایت داری که ۲ تا صفحه داره: `About` و `Careers`.
حالا می‌خوای ۳ تا تم رنگی هم اضافه کنی: `Dark`, `Light`, `Aqua`.

اگه از روش معمولی (ارث‌بری) بری، باید برای هر صفحه، ۳ تا حالت بسازی:
*   `AboutDark`, `AboutLight`, `AboutAqua`
*   `CareersDark`, `CareersLight`, `CareersAqua`

می‌بینی؟ تعداد کلاس‌ها داره منفجر می‌شه! (تعداد صفحات × تعداد تم‌ها). 💣
اگه فردا ۱۰ تا صفحه و ۵ تا تم داشته باشی، باید ۵۰ تا کلاس بسازی!

**راه‌حل Bridge چیه؟**
می‌گه این دوتا رو از هم جدا کن:
۱. یه سلسله‌مراتب برای **صفحات** (About, Careers).
۲. یه سلسله‌مراتب برای **تم‌ها** (Dark, Light).
حالا توی هر صفحه، یه «پل» (Bridge) می‌زنیم به تم مورد نظر. اینطوری فقط ۱۰ + ۵ کلاس داریم، نه ۱۰ × ۵.

💡 **به زبون ساده:**
> دوتا چیزی که دارن جدا جدا تغییر می‌کنن، مثلاً «صفحه» و «تم»، رو به دوتا سلسله‌مراتب مستقل بشکن و با یه «پل» به هم وصلشون کن؛ اینطوری به جای ضرب کردن حالت‌ها در هم، فقط جمعشون می‌کنی.
> به جای اینکه بگی «من یه صفحه درباره ما هستم که سیاهه»، بگو «من یه صفحه درباره ما هستم که یه تم، حالا هر چی، دارم.»

![With and without the bridge pattern](images/without_bridge.png)

ویکی‌پدیا:

<div dir="ltr">

> The bridge pattern is a design pattern used in software engineering that is meant to "decouple an abstraction from its
> implementation so that the two can vary independently"

</div>

خلاصه‌اش این می‌شه: «انتزاع» (Abstraction) یعنی همون چیزی که باهاش کار می‌کنی؛ اینو از «پیاده‌سازی» (Implementation) جدا نگه دار. اونوقت هر کدوم می‌تونن مستقل از اون یکی رشد کنن، بی‌اینکه به هم گره بخورن.

**مثال برنامه‌نویسی**

بیا همون مثال سایت و تم که بالاتر گفتیم رو پیاده کنیم.

در مرحله اول کلاس `WebPage` و پیاده‌سازی‌هایی از اون رو داریم.

برای تم هم باید کلاس و پیاده‌سازی‌های مختلف بنویسیم:

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Theme:
    def getColor(self):
        pass


class DarkTheme(Theme):
    def getColor(self):
        return "Dark Black"


class LightTheme(Theme):
    def getColor(self):
        return "Off white"


class AquaTheme(Theme):
    def getColor(self):
        return "Light blue"


class WebPage:
    def __init__(self, theme):
        self.theme = theme

    def getContent(self):
        pass


class About(WebPage):
    def getContent(self):
        return "About page in " + self.theme.getColor()


class Careers(WebPage):
    def getContent(self):
        return "Careers page in " + self.theme.getColor()


# ----------------------------

darkTheme = DarkTheme()
aquaTheme = AquaTheme()

about = About(darkTheme)
careers = Careers(aquaTheme)

print(about.getContent())    # About page in Dark Black
print(careers.getContent())  # Careers page in Light blue
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface Theme {
    getColor(): string;
}

class DarkTheme implements Theme {
    getColor(): string {
        return "Dark Black";
    }
}

class LightTheme implements Theme {
    getColor(): string {
        return "Off white";
    }
}

class AquaTheme implements Theme {
    getColor(): string {
        return "Light blue";
    }
}

abstract class WebPage {
    protected theme: Theme;

    constructor(theme: Theme) {
        this.theme = theme;
    }

    abstract getContent(): string;
}

class About extends WebPage {
    getContent(): string {
        return "About page in " + this.theme.getColor();
    }
}

class Careers extends WebPage {
    getContent(): string {
        return "Careers page in " + this.theme.getColor();
    }
}

// ----------------------------

const darkTheme = new DarkTheme();
const aquaTheme = new AquaTheme();

const about = new About(darkTheme);
const careers = new Careers(aquaTheme);

console.log(about.getContent());    // About page in Dark Black
console.log(careers.getContent());  // Careers page in Light blue
```

</div>

</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Theme {
    getColor() {
        return "";
    }
}

class DarkTheme extends Theme {
    getColor() {
        return "Dark Black";
    }
}

class LightTheme extends Theme {
    getColor() {
        return "Off white";
    }
}

class AquaTheme extends Theme {
    getColor() {
        return "Light blue";
    }
}

class WebPage {
    constructor(theme) {
        this._theme = theme;
    }

    getContent() {
        return "";
    }
}

class About extends WebPage {
    getContent() {
        return `About page in ${this._theme.getColor()}`;
    }
}

class Careers extends WebPage {
    getContent() {
        return `Careers page in ${this._theme.getColor()}`;
    }
}


const darkTheme = new DarkTheme();
const aquaTheme = new AquaTheme();

const about = new About(darkTheme);
const careers = new Careers(aquaTheme);

console.log(about.getContent());    // About page in Dark Black
console.log(careers.getContent());  // Careers page in Light blue
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface IWebPage
{
  string GetContent();
}

class About : IWebPage
{
  protected ITheme theme;

  public About(ITheme theme)
  {
    this.theme = theme;
  }

  public string GetContent()
  {
    return $"About page in {theme.GetColor()}";
  }
}

class Careers : IWebPage
{
  protected ITheme theme;

  public Careers(ITheme theme)
  {
    this.theme = theme;
  }

  public string GetContent()
  {
    return $"Careers page in {theme.GetColor()}";
  }
}


interface ITheme
{
  string GetColor();
}

class DarkTheme : ITheme
{
  public string GetColor()
  {
    return "Dark Black";
  }
}

class LightTheme : ITheme
{
  public string GetColor()
  {
    return "Off white";
  }
}

class AquaTheme : ITheme
{
  public string GetColor()
  {
    return "Light blue";
  }
}

// ----------------------------

var darkTheme = new DarkTheme();
var aquaTheme = new AquaTheme();

var about = new About(darkTheme);
var careers = new Careers(aquaTheme);

Console.WriteLine(about.GetContent());   // About page in Dark Black
Console.WriteLine(careers.GetContent()); // Careers page in Light blue

```

</div>

</details>

<details>
<summary>PHP</summary>
<div dir="ltr">

```php
interface WebPageInterface {
  public function getContent();
}

class About implements WebPageInterface {
  protected $theme;

  public function __construct(ThemeInterface $theme) {
    $this->theme = $theme;
  }

  public function getContent() {
    return "About page in " . $this->theme->getColor();
  }
}

class Careers implements WebPageInterface {
  protected $theme;

  public function __construct(ThemeInterface $theme) {
    $this->theme = $theme;
  }

  public function getContent() {
    return "Careers page in " . $this->theme->getColor();
  }
}

interface ThemeInterface {
  public function getColor();
}

class DarkTheme implements ThemeInterface {
  public function getColor() {
    return "Dark Black";
  }
}

class LightTheme implements ThemeInterface {
  public function getColor() {
    return "Off white";
  }
}

class AquaTheme implements ThemeInterface {
  public function getColor() {
    return "Light blue";
  }
}

$darkTheme = new DarkTheme();
$aquaTheme = new AquaTheme();

$about = new About($darkTheme);
$careers = new Careers($aquaTheme);

echo $about->getContent() . "\n";   // About page in Dark Black
echo $careers->getContent() . "\n"; // Careers page in Light blue

```

</div>

</details>

<details>
<summary>Go</summary>
<div dir="ltr">

```go
package main

import "fmt"

type IWebPage interface {
GetContent() string
}

type About struct {
theme ITheme
}

func NewAbout(theme ITheme) *About {
return &About{theme: theme}
}

func (a *About) GetContent() string {
return fmt.Sprintf("About page in %s", a.theme.GetColor())
}

type Careers struct {
theme ITheme
}

func NewCareers(theme ITheme) *Careers {
return &Careers{theme: theme}
}

func (c *Careers) GetContent() string {
return fmt.Sprintf("Careers page in %s", c.theme.GetColor())
}

type ITheme interface {
GetColor() string
}

type DarkTheme struct{}

func (d *DarkTheme) GetColor() string {
return "Dark Black"
}

type LightTheme struct{}

func (l *LightTheme) GetColor() string {
return "Off white"
}

type AquaTheme struct{}

func (a *AquaTheme) GetColor() string {
return "Light blue"
}

func main() {
darkTheme := &DarkTheme{}
aquaTheme := &AquaTheme{}

about := NewAbout(darkTheme)
careers := NewCareers(aquaTheme)

fmt.Println(about.GetContent())   // About page in Dark Black
fmt.Println(careers.GetContent()) // Careers page in Light blue
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface WebPage {
    String getContent();
}

interface Theme {
    String getColor();
}

class About implements WebPage {
    private Theme theme;

    public About(Theme theme) {
        this.theme = theme;
    }

    public String getContent() {
        return "About page in " + theme.getColor();
    }
}

class Careers implements WebPage {
    private Theme theme;

    public Careers(Theme theme) {
        this.theme = theme;
    }

    public String getContent(){
        return "Careers page in "+ theme.getColor();
    }
}

class DarkTheme implements Theme {
    public String getColor() {
        return "Dark Black";
    }
}

class LightTheme implements Theme {
    public String getColor() {
        return "Off white";
    }
}

class AquaTheme implements Theme {
    public String getColor() {
        return "Light blue";
    }
}

// ----------------------------


DarkTheme darkTheme = new DarkTheme();
AquaTheme aquaTheme = new AquaTheme();

About about = new About(darkTheme);
Careers careers = new Careers(aquaTheme);

System.out.println(about.getContent());     // About page in Dark Black
System.out.println(careers.getContent());   // Careers page in Light blue
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <memory>

// Theme interface (Implementor)
class Theme {
public:
    virtual ~Theme() = default;
    virtual std::string getColor() = 0;
};

// Dark theme implementation
class DarkTheme : public Theme {
public:
    std::string getColor() override {
        return "Dark Black";
    }
};

// Light theme implementation
class LightTheme : public Theme {
public:
    std::string getColor() override {
        return "Off white";
    }
};

// Aqua theme implementation
class AquaTheme : public Theme {
public:
    std::string getColor() override {
        return "Light blue";
    }
};

// Web page abstraction
class WebPage {
protected:
    std::unique_ptr<Theme> theme;

public:
    WebPage(std::unique_ptr<Theme> theme) : theme(std::move(theme)) {}
    virtual ~WebPage() = default;
    virtual std::string getContent() = 0;
};

// About page
class About : public WebPage {
public:
    About(std::unique_ptr<Theme> theme) : WebPage(std::move(theme)) {}
    
    std::string getContent() override {
        return "About page in " + theme->getColor();
    }
};

// Careers page
class Careers : public WebPage {
public:
    Careers(std::unique_ptr<Theme> theme) : WebPage(std::move(theme)) {}
    
    std::string getContent() override {
        return "Careers page in " + theme->getColor();
    }
};

// Usage
int main() {
    About about(std::make_unique<DarkTheme>());
    Careers careers(std::make_unique<AquaTheme>());

    std::cout << about.getContent() << std::endl;     // About page in Dark Black
    std::cout << careers.getContent() << std::endl;   // Careers page in Light blue

    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Theme {
    fun getColor(): String
}

interface WebPage {
    fun getContent(): String
}

class DarkTheme : Theme {
    override fun getColor() = "Dark Black"
}

class LightTheme : Theme {
    override fun getColor() = "Off white"
}

class AquaTheme : Theme {
    override fun getColor() = "Light blue"
}

class About(private val theme: Theme) : WebPage {
    override fun getContent() = "About page in " + theme.getColor()
}

class Careers(private val theme: Theme) : WebPage {
    override fun getContent() = "Careers page in " + theme.getColor()
}

// ----------------------------

fun main() {
    val darkTheme = DarkTheme()
    val aquaTheme = AquaTheme()

    val about = About(darkTheme)
    val careers = Careers(aquaTheme)

    println(about.getContent())
    println(careers.getContent())
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Theme {
  String getColor();
}

abstract class WebPage {
  final Theme theme;

  WebPage(this.theme);

  String getContent();
}

class DarkTheme implements Theme {
  @override
  String getColor() => "Dark Black";
}

class LightTheme implements Theme {
  @override
  String getColor() => "Off white";
}

class AquaTheme implements Theme {
  @override
  String getColor() => "Light blue";
}

class About extends WebPage {
  About(Theme theme) : super(theme);

  @override
  String getContent() => "About page in " + theme.getColor();
}

class Careers extends WebPage {
  Careers(Theme theme) : super(theme);

  @override
  String getContent() => "Careers page in " + theme.getColor();
}

// ----------------------------

void main() {
  var darkTheme = DarkTheme();
  var aquaTheme = AquaTheme();

  var about = About(darkTheme);
  var careers = Careers(aquaTheme);

  print(about.getContent());
  print(careers.getContent());
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی دوتا بُعد مستقل داری که جدا جدا زیاد می‌شن، مثل صفحه × تم، و نمی‌خوای ضربشون کنی در هم»؛ ❌ «وقتی فقط یه بُعد داری یا حالت‌ها هیچ‌وقت قرار نیست زیاد بشن».
> 🪤 **دام رایج:** «از همون اول همه‌چی رو با پل می‌سازی و کد رو الکی پیچیده می‌کنی، در حالی که هنوز انفجار کلاس‌ها اتفاق نیفتاده».
> 🔗 **فرقش با [مبدل (Adapter)](#مبدل-adapter-):** «مبدل بعد از ساخته‌شدن کد، دوتا چیز ناسازگار رو به هم می‌چسبونه؛ پل از اول طراحی می‌شه تا دو بُعد جدا بمونن».


<br>

---

<div align="center">

## درختی (Composite) 🌿

</div>

<div align="center">
📦 <b>مثال دنیای واقعی: جعبه تو جعبه</b>
</div>

فرض کن قراره قیمت یه بسته پستی بزرگ رو حساب کنی.
توی این بسته بزرگ، ممکنه:
۱. چندتا محصول تکی باشه (مثلاً یه کتاب، یه گوشی).
۲. چندتا «جعبه کوچیک‌تر» باشه که توی اون جعبه‌ها هم دوباره محصول یا حتی جعبه‌های دیگه هست!

اگه بخوای قیمت کل رو حساب کنی، باید دونه دونه جعبه‌ها رو باز کنی.
اما توی دنیای کامپیوتر، ما دوست داریم با **کل بسته** یه طوری رفتار کنیم که انگار یه **محصول تکی** هست.
یعنی همین که `GetPrice()` رو صدا بزنیم، خودش بره سراغ همه زیرمجموعه‌ها، قیمتشون رو جمع بزنه و کل رو برگردونه.

💡 **به زبون ساده:**
> این پترن برای ساختن **ساختارهای درختی** (Tree Structures) عالیه.
> به تو اجازه می‌ده با یک «گروه از آبجکت‌ها» (Composite) دقیقاً همون‌طوری رفتار کنی که با یک «آبجکت تکی» (Leaf) رفتار می‌کنی.

![Composite](images/Composite.png)

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, the composite pattern is a partitioning design pattern. The composite pattern describes that
> a group of objects is to be treated in the same way as a single instance of an object. The intent of a composite is
> to "
> compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets
> clients treat individual objects and compositions uniformly.

</div>

خلاصه‌اش این می‌شه که الگوی درختی بهت اجازه می‌ده آبجکت‌ها رو توی یه ساختار درختی بچینی و بعد با کل اون درخت درست مثل یه آبجکت تکی رفتار کنی.
فرقی نمی‌کنه طرفت یه «برگ» تنهاست یا یه «شاخه» پر از زیرمجموعه؛ با هردوشون عین هم رفتار می‌کنی و خود ساختار، ته‌توش رو در میاره.

**مثال برنامه‌نویسی**

توی الگوی درختی (Composite) ما دو نوع جزء داریم:

یک: خودِ Composite که می‌تونه زیرمجموعه داشته باشه (و خودش هم ممکنه وظیفه‌ای داشته باشه).

دو: Leaf که زیرمجموعه نداره و فقط یه سری وظیفه داره.

خب اول بیایم یک اینترفیس پایه برای کامپوننت‌هامون بسازیم و در ادامه هم اینترفیس‌های Composite و Leaf رو بسازیم:

<details>

<summary>Python</summary>

<div dir="ltr">

```python
from abc import ABC, abstractmethod
from typing import List


class Employee(ABC):
    @abstractmethod
    def get_name(self) -> str: ...

    @abstractmethod
    def get_salary(self) -> float: ...


class Developer(Employee):
    def __init__(self, name: str, salary: float) -> None:
        self._name = name
        self._salary = salary

    def get_name(self) -> str:
        return self._name

    def get_salary(self) -> float:
        return self._salary


class Designer(Employee):
    def __init__(self, name: str, salary: float) -> None:
        self._name = name
        self._salary = salary

    def get_name(self) -> str:
        return self._name

    def get_salary(self) -> float:
        return self._salary


# Organization is itself an Employee (the Composite); it can hold sub-members
class Organization(Employee):
    def __init__(self, name: str) -> None:
        self._name = name
        self._members: List[Employee] = []

    def add(self, employee: Employee) -> None:
        self._members.append(employee)

    def get_name(self) -> str:
        return self._name

    def get_salary(self) -> float:
        total = 0.0
        for member in self._members:
            total += member.get_salary()  # recurses into sub-organizations
        return total


# ----------------------------

design_team = Organization("Design Team")
design_team.add(Designer("Arya", 4000))

company = Organization("Acme")
company.add(Developer("John", 5000))
company.add(Developer("Jane", 6000))
company.add(design_team)

print(f"Total salary: {company.get_salary():g}")
# Total salary: 15000
```

</div>

</details>

<details>

<summary>TypeScript</summary>

<div dir="ltr">

```typescript
interface Employee {
    getName(): string;

    getSalary(): number;
}

class Developer implements Employee {
    constructor(private name: string, private salary: number) {
    }

    getName(): string {
        return this.name;
    }

    getSalary(): number {
        return this.salary;
    }
}

class Designer implements Employee {
    constructor(private name: string, private salary: number) {
    }

    getName(): string {
        return this.name;
    }

    getSalary(): number {
        return this.salary;
    }
}

// Organization is itself an Employee (the Composite); it can hold sub-members
class Organization implements Employee {
    private members: Employee[] = [];

    constructor(private name: string) {
    }

    add(employee: Employee): void {
        this.members.push(employee);
    }

    getName(): string {
        return this.name;
    }

    getSalary(): number {
        let total = 0;
        for (const member of this.members) {
            total += member.getSalary(); // recurses into sub-organizations
        }
        return total;
    }
}

// ----------------------------

const designTeam = new Organization("Design Team");
designTeam.add(new Designer("Arya", 4000));

const company = new Organization("Acme");
company.add(new Developer("John", 5000));
company.add(new Developer("Jane", 6000));
company.add(designTeam);

console.log(`Total salary: ${company.getSalary()}`);
// Total salary: 15000
```

</div>

</details>

<details>

<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class Developer {
    constructor(name, salary) {
        this.name = name;
        this.salary = salary;
    }

    getName() {
        return this.name;
    }

    getSalary() {
        return this.salary;
    }
}

class Designer {
    constructor(name, salary) {
        this.name = name;
        this.salary = salary;
    }

    getName() {
        return this.name;
    }

    getSalary() {
        return this.salary;
    }
}

// Organization is itself an Employee (the Composite); it can hold sub-members
class Organization {
    constructor(name) {
        this.name = name;
        this.members = [];
    }

    add(employee) {
        this.members.push(employee);
    }

    getName() {
        return this.name;
    }

    getSalary() {
        let total = 0;
        for (const member of this.members) {
            total += member.getSalary(); // recurses into sub-organizations
        }
        return total;
    }
}

// ----------------------------

const designTeam = new Organization("Design Team");
designTeam.add(new Designer("Arya", 4000));

const company = new Organization("Acme");
company.add(new Developer("John", 5000));
company.add(new Developer("Jane", 6000));
company.add(designTeam);

console.log(`Total salary: ${company.getSalary()}`);
// Total salary: 15000
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;
using System.Collections.Generic;

interface IEmployee
{
  string GetName();
  float GetSalary();
}

class Developer : IEmployee
{
  private string mName;
  private float mSalary;

  public Developer(string name, float salary)
  {
    this.mName = name;
    this.mSalary = salary;
  }

  public string GetName()
  {
    return this.mName;
  }

  public float GetSalary()
  {
    return this.mSalary;
  }
}

class Designer : IEmployee
{
  private string mName;
  private float mSalary;

  public Designer(string name, float salary)
  {
    this.mName = name;
    this.mSalary = salary;
  }

  public string GetName()
  {
    return this.mName;
  }

  public float GetSalary()
  {
    return this.mSalary;
  }
}

// Organization is itself an IEmployee (the Composite); it can hold sub-members
class Organization : IEmployee
{
  private string mName;
  private List<IEmployee> mMembers = new List<IEmployee>();

  public Organization(string name)
  {
    this.mName = name;
  }

  public void Add(IEmployee employee)
  {
    mMembers.Add(employee);
  }

  public string GetName()
  {
    return this.mName;
  }

  public float GetSalary()
  {
    float total = 0;
    foreach (var member in mMembers)
    {
      total += member.GetSalary(); // recurses into sub-organizations
    }
    return total;
  }
}

// ----------------------------

var designTeam = new Organization("Design Team");
designTeam.Add(new Designer("Arya", 4000));

var company = new Organization("Acme");
company.Add(new Developer("John", 5000));
company.Add(new Developer("Jane", 6000));
company.Add(designTeam);

Console.WriteLine($"Total salary: {company.GetSalary()}");
// Total salary: 15000
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface EmployeeInterface {
  function getName(): string;
  function getSalary(): float;
}

class Developer implements EmployeeInterface {
  private string $name;
  private float $salary;

  public function __construct(string $name, float $salary) {
    $this->name = $name;
    $this->salary = $salary;
  }

  public function getName(): string {
    return $this->name;
  }

  public function getSalary(): float {
    return $this->salary;
  }
}

class Designer implements EmployeeInterface {
  private string $name;
  private float $salary;

  public function __construct(string $name, float $salary) {
    $this->name = $name;
    $this->salary = $salary;
  }

  public function getName(): string {
    return $this->name;
  }

  public function getSalary(): float {
    return $this->salary;
  }
}

// Organization is itself an EmployeeInterface (the Composite); it can hold sub-members
class Organization implements EmployeeInterface {
  private string $name;
  private array $members = array();

  public function __construct(string $name) {
    $this->name = $name;
  }

  public function add(EmployeeInterface $employee): void {
    $this->members[] = $employee;
  }

  public function getName(): string {
    return $this->name;
  }

  public function getSalary(): float {
    $total = 0;
    foreach ($this->members as $member) {
      $total += $member->getSalary(); // recurses into sub-organizations
    }
    return $total;
  }
}

// ----------------------------

$designTeam = new Organization("Design Team");
$designTeam->add(new Designer("Arya", 4000));

$company = new Organization("Acme");
$company->add(new Developer("John", 5000));
$company->add(new Developer("Jane", 6000));
$company->add($designTeam);

echo "Total salary: " . $company->getSalary() . PHP_EOL;
// Total salary: 15000
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Employee interface {
    GetName() string
    GetSalary() float64
}

type Developer struct {
    Name   string
    Salary float64
}

func (d *Developer) GetName() string {
    return d.Name
}

func (d *Developer) GetSalary() float64 {
    return d.Salary
}

type Designer struct {
    Name   string
    Salary float64
}

func (d *Designer) GetName() string {
    return d.Name
}

func (d *Designer) GetSalary() float64 {
    return d.Salary
}

// Organization is itself an Employee (the Composite); it can hold sub-members
type Organization struct {
    Name    string
    members []Employee
}

func (o *Organization) Add(employee Employee) {
    o.members = append(o.members, employee)
}

func (o *Organization) GetName() string {
    return o.Name
}

func (o *Organization) GetSalary() float64 {
    total := float64(0)
    for _, member := range o.members {
        total += member.GetSalary() // recurses into sub-organizations
    }
    return total
}

func main() {
    designTeam := &Organization{Name: "Design Team"}
    designTeam.Add(&Designer{Name: "Arya", Salary: 4000})

    company := &Organization{Name: "Acme"}
    company.Add(&Developer{Name: "John", Salary: 5000})
    company.Add(&Developer{Name: "Jane", Salary: 6000})
    company.Add(designTeam)

    fmt.Printf("Total salary: %g\n", company.GetSalary())
    // Total salary: 15000
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
import java.util.*;

interface Employee {

    String getName();
    float getSalary();
}

class Developer implements Employee {
    private String name;
    private float salary;

    public Developer(String name, float salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return this.name;
    }
    public float getSalary() {
        return this.salary;
    }
}

class Designer implements Employee {
    private String name;
    private float salary;

    public Designer(String name, float salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return this.name;
    }
    public float getSalary() {
        return this.salary;
    }
}

// Organization is itself an Employee (the Composite); it can hold sub-members
class Organization implements Employee {
    private String name;
    private List<Employee> members = new ArrayList<>();

    public Organization(String name) {
        this.name = name;
    }

    public void add(Employee employee) {
        members.add(employee);
    }

    public String getName() {
        return this.name;
    }

    public float getSalary() {
        float total = 0;
        for (Employee member : members) {
            total += member.getSalary(); // recurses into sub-organizations
        }
        return total;
    }
}

// ----------------------------

Organization designTeam = new Organization("Design Team");
designTeam.add(new Designer("Arya", 4000));

Organization company = new Organization("Acme");
company.add(new Developer("John", 5000));
company.add(new Developer("Jane", 6000));
company.add(designTeam);

System.out.printf("Total salary: %.0f%n", company.getSalary());
// Total salary: 15000
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <memory>

// Employee interface
class Employee {
public:
    virtual ~Employee() = default;
    virtual std::string getName() const = 0;
    virtual double getSalary() const = 0;
};

// Developer leaf
class Developer : public Employee {
private:
    std::string name;
    double salary;

public:
    Developer(const std::string& name, double salary) : name(name), salary(salary) {}

    std::string getName() const override {
        return name;
    }

    double getSalary() const override {
        return salary;
    }
};

// Designer leaf
class Designer : public Employee {
private:
    std::string name;
    double salary;

public:
    Designer(const std::string& name, double salary) : name(name), salary(salary) {}

    std::string getName() const override {
        return name;
    }

    double getSalary() const override {
        return salary;
    }
};

// Organization is itself an Employee (the Composite); it can hold sub-members
class Organization : public Employee {
private:
    std::string name;
    std::vector<std::shared_ptr<Employee>> members;

public:
    explicit Organization(const std::string& name) : name(name) {}

    void add(std::shared_ptr<Employee> employee) {
        members.push_back(std::move(employee));
    }

    std::string getName() const override {
        return name;
    }

    double getSalary() const override {
        double total = 0.0;
        for (const auto& member : members) {
            total += member->getSalary(); // recurses into sub-organizations
        }
        return total;
    }
};

// Usage
int main() {
    auto designTeam = std::make_shared<Organization>("Design Team");
    designTeam->add(std::make_shared<Designer>("Arya", 4000));

    auto company = std::make_shared<Organization>("Acme");
    company->add(std::make_shared<Developer>("John", 5000));
    company->add(std::make_shared<Developer>("Jane", 6000));
    company->add(designTeam);

    std::cout << "Total salary: " << company->getSalary() << std::endl;
    // Total salary: 15000

    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Employee {
    fun getName(): String
    fun getSalary(): Double
}

class Developer(private val name: String, private val salary: Double) : Employee {
    override fun getName() = name
    override fun getSalary() = salary
}

class Designer(private val name: String, private val salary: Double) : Employee {
    override fun getName() = name
    override fun getSalary() = salary
}

// Organization is itself an Employee (the Composite); it can hold sub-members
class Organization(private val name: String) : Employee {
    private val members = mutableListOf<Employee>()

    fun add(employee: Employee) {
        members.add(employee)
    }

    override fun getName() = name

    override fun getSalary(): Double {
        var total = 0.0
        for (member in members) {
            total += member.getSalary() // recurses into sub-organizations
        }
        return total
    }
}

// ----------------------------

fun main() {
    val designTeam = Organization("Design Team")
    designTeam.add(Designer("Arya", 4000.0))

    val company = Organization("Acme")
    company.add(Developer("John", 5000.0))
    company.add(Developer("Jane", 6000.0))
    company.add(designTeam)

    println("Total salary: ${company.getSalary().toInt()}")
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Employee {
  String getName();
  double getSalary();
}

class Developer implements Employee {
  final String _name;
  final double _salary;

  Developer(this._name, this._salary);

  @override
  String getName() => _name;

  @override
  double getSalary() => _salary;
}

class Designer implements Employee {
  final String _name;
  final double _salary;

  Designer(this._name, this._salary);

  @override
  String getName() => _name;

  @override
  double getSalary() => _salary;
}

// Organization is itself an Employee (the Composite); it can hold sub-members
class Organization implements Employee {
  final String _name;
  final List<Employee> _members = [];

  Organization(this._name);

  void add(Employee employee) {
    _members.add(employee);
  }

  @override
  String getName() => _name;

  @override
  double getSalary() {
    double total = 0;
    for (var member in _members) {
      total += member.getSalary(); // recurses into sub-organizations
    }
    return total;
  }
}

// ----------------------------

void main() {
  var designTeam = Organization("Design Team");
  designTeam.add(Designer("Arya", 4000));

  var company = Organization("Acme");
  company.add(Developer("John", 5000));
  company.add(Developer("Jane", 6000));
  company.add(designTeam);

  print("Total salary: ${company.getSalary().toInt()}");
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی داده‌هات یه ساختار درختی دارن (بخش‌ها و کل‌ها) و می‌خوای با تک‌آبجکت و گروه یه‌جور رفتار کنی»؛ ❌ «وقتی آبجکت‌هات سلسله‌مراتب ندارن و صاف کنار هم‌ان؛ اون‌جا درختی فقط پیچیدگی الکی اضافه می‌کنه».
> 🪤 **دام رایج:** «این‌قدر هوس می‌کنی همه‌چی رو یکدست کنی که متدهای بی‌معنی مثل add رو روی «برگ» هم می‌ذاری، و بعد برنامه موقع اجرا می‌ترکه».


<br>

---

<div align="center">

## دکوریتور (Decorator) ☕

</div>

<div align="center">
☕ <b>مثال دنیای واقعی: کافی‌شاپ</b>
</div>

فرض کن رفتی کافی‌شاپ و سفارش قهوه می‌دی.
اول یه «قهوه ساده» سفارش می‌دی. ☕
بعد می‌گی «شیر هم اضافه کن». 🥛 (الآن شد قهوه با شیر)
بعد می‌گی «شکر هم بریز توش». 🧂 (الآن شد قهوه با شیر و شکر)

آیا برای هر کدوم از این ترکیب‌ها باید یه کلاس جدید بسازیم؟
*   `SimpleCoffee`
*   `CoffeeWithMilk`
*   `CoffeeWithMilkAndSugar`
*   ...

نه! اینطوری که کلاس‌ها منفجر می‌شن!
الگوی **Decorator** می‌گه: «قهوه ساده رو پایه قرار بده و هر چیزی که خواستی رو مثل لایه‌های مختلف دورش بپیچ (Decorate کن).»

💡 **به زبون ساده:**
> این پترن می‌گه: **«به جای اینکه کلاس رو تغییر بدی، قابلیت‌های جدید رو لایه لایه بهش اضافه کن.»**
> (دقیقا مثل لباس پوشیدن! اول لباس زیر، بعد پیراهن، بعد کاپشن. هر لایه یه چیزی به قبلی اضافه می‌کنه).

ویکی‌پدیا:

<div dir="ltr">

> In object-oriented programming, the decorator pattern is a design pattern that allows behavior to be added to an
> individual object, either statically or dynamically, without affecting the behavior of other objects from the same
> class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows
> functionality to be divided between classes with unique areas of concern.

</div>

به زبون خودمون: الگوی دکوریتور می‌گه می‌تونی بدون دست زدن به خود کلاس، رفتار و قابلیت‌های تازه رو لایه‌لایه به یه آبجکت مشخص اضافه کنی؛ اونم درست همون لحظه که برنامه داره اجرا می‌شه. اینطوری هر کلاس مسئول یه کار می‌مونه و آبجکت‌های دیگه از همون کلاس دست‌نخورده باقی می‌مونن.

**مثال برنامه‌نویسی**

بیا برگردیم سراغ همون قهوه. اول یه قهوه ساده داریم که اینترفیس `Coffee` رو پیاده‌سازی می‌کنه.

می‌خوایم کد رو جوری بسازیم که هر وقت لازم شد، گزینه‌های جدید بتونن رفتارش رو عوض کنن.

پس بیا چند دکوریتور (Decorator) براش بسازیم.

همون‌طور که می‌بینی، خیلی ساده می‌تونیم هر آبجکت رو ورودیِ تابع بعدی بدیم و چند مرحله افزودنی رو پشت‌سرهم به آبجکتمون اضافه کنیم!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Coffee:
    def cost(self):
        pass

    def description(self):
        pass


class SimpleCoffee(Coffee):
    def cost(self):
        return 10

    def description(self):
        return 'Simple coffee'


class MilkDecorator(Coffee):
    def __init__(self, coffee):
        self._coffee = coffee

    def cost(self):
        return self._coffee.cost() + 2

    def description(self):
        return self._coffee.description() + ', milk'


class SugarDecorator(Coffee):
    def __init__(self, coffee):
        self._coffee = coffee

    def cost(self):
        return self._coffee.cost() + 1

    def description(self):
        return self._coffee.description() + ', sugar'


# ----------------------------

coffee = SimpleCoffee()
print(f"{coffee.description()}: {coffee.cost()}")  # Simple coffee: 10

coffee = MilkDecorator(coffee)
print(f"{coffee.description()}: {coffee.cost()}")  # Simple coffee, milk: 12

coffee = SugarDecorator(coffee)
print(f"{coffee.description()}: {coffee.cost()}")  # Simple coffee, milk, sugar: 13
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface Coffee {
    cost(): number;
    description(): string;
}

class SimpleCoffee implements Coffee {
    cost(): number {
        return 10;
    }

    description(): string {
        return "Simple coffee";
    }
}

class MilkDecorator implements Coffee {
    private coffee: Coffee;

    constructor(coffee: Coffee) {
        this.coffee = coffee;
    }

    cost(): number {
        return this.coffee.cost() + 2;
    }

    description(): string {
        return this.coffee.description() + ", milk";
    }
}

class SugarDecorator implements Coffee {
    private coffee: Coffee;

    constructor(coffee: Coffee) {
        this.coffee = coffee;
    }

    cost(): number {
        return this.coffee.cost() + 1;
    }

    description(): string {
        return this.coffee.description() + ", sugar";
    }
}

// ----------------------------

let coffee: Coffee = new SimpleCoffee();
console.log(`${coffee.description()}: ${coffee.cost()}`); // Simple coffee: 10

coffee = new MilkDecorator(coffee);
console.log(`${coffee.description()}: ${coffee.cost()}`); // Simple coffee, milk: 12

coffee = new SugarDecorator(coffee);
console.log(`${coffee.description()}: ${coffee.cost()}`); // Simple coffee, milk, sugar: 13
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Coffee {
    cost() {
        throw new Error("cost() must be implemented by subclasses");
    }

    description() {
        throw new Error("description() must be implemented by subclasses");
    }
}

class SimpleCoffee extends Coffee {
    cost() {
        return 10;
    }

    description() {
        return "Simple coffee";
    }
}

class MilkDecorator extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }

    cost() {
        return this.coffee.cost() + 2;
    }

    description() {
        return this.coffee.description() + ", milk";
    }
}

class SugarDecorator extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }

    cost() {
        return this.coffee.cost() + 1;
    }

    description() {
        return this.coffee.description() + ", sugar";
    }
}


let coffee = new SimpleCoffee();
console.log(`${coffee.description()}: ${coffee.cost()}`); // Simple coffee: 10

coffee = new MilkDecorator(coffee);
console.log(`${coffee.description()}: ${coffee.cost()}`); // Simple coffee, milk: 12

coffee = new SugarDecorator(coffee);
console.log(`${coffee.description()}: ${coffee.cost()}`); // Simple coffee, milk, sugar: 13
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface ICoffee
{
  int Cost();
  string Description();
}

class SimpleCoffee : ICoffee
{
  public int Cost()
  {
    return 10;
  }

  public string Description()
  {
    return "Simple coffee";
  }
}

class MilkDecorator : ICoffee
{
  private readonly ICoffee mCoffee;

  public MilkDecorator(ICoffee coffee)
  {
    mCoffee = coffee ?? throw new ArgumentNullException("coffee", "coffee should not be null");
  }

  public int Cost()
  {
    return mCoffee.Cost() + 2;
  }

  public string Description()
  {
    return String.Concat(mCoffee.Description(), ", milk");
  }
}

class SugarDecorator : ICoffee
{
  private readonly ICoffee mCoffee;

  public SugarDecorator(ICoffee coffee)
  {
    mCoffee = coffee ?? throw new ArgumentNullException("coffee", "coffee should not be null");
  }

  public int Cost()
  {
    return mCoffee.Cost() + 1;
  }

  public string Description()
  {
    return String.Concat(mCoffee.Description(), ", sugar");
  }
}


// ----------------------------

ICoffee coffee = new SimpleCoffee();
Console.WriteLine($"{coffee.Description()}: {coffee.Cost()}"); // Simple coffee: 10

coffee = new MilkDecorator(coffee);
Console.WriteLine($"{coffee.Description()}: {coffee.Cost()}"); // Simple coffee, milk: 12

coffee = new SugarDecorator(coffee);
Console.WriteLine($"{coffee.Description()}: {coffee.Cost()}"); // Simple coffee, milk, sugar: 13

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface CoffeeInterface {
  public function cost();
  public function description();
}

class SimpleCoffee implements CoffeeInterface {
  public function cost() {
    return 10;
  }

  public function description() {
    return "Simple coffee";
  }
}

class MilkDecorator implements CoffeeInterface {
  private $coffee;

  public function __construct(CoffeeInterface $coffee) {
    $this->coffee = $coffee ?? throw new Exception("coffee should not be null");
  }

  public function cost() {
    return $this->coffee->cost() + 2;
  }

  public function description() {
    return $this->coffee->description() . ", milk";
  }
}

class SugarDecorator implements CoffeeInterface {
  private $coffee;

  public function __construct(CoffeeInterface $coffee) {
    $this->coffee = $coffee ?? throw new Exception("coffee should not be null");
  }

  public function cost() {
    return $this->coffee->cost() + 1;
  }

  public function description() {
    return $this->coffee->description() . ", sugar";
  }
}

$coffee = new SimpleCoffee();
echo $coffee->description() . ": " . $coffee->cost() . "\n"; // Simple coffee: 10

$coffee = new MilkDecorator($coffee);
echo $coffee->description() . ": " . $coffee->cost() . "\n"; // Simple coffee, milk: 12

$coffee = new SugarDecorator($coffee);
echo $coffee->description() . ": " . $coffee->cost() . "\n"; // Simple coffee, milk, sugar: 13

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import (
	"fmt"
)

type Coffee interface {
	Cost() int
	Description() string
}

type SimpleCoffee struct{}

func (c *SimpleCoffee) Cost() int {
	return 10
}

func (c *SimpleCoffee) Description() string {
	return "Simple coffee"
}

type MilkDecorator struct {
	coffee Coffee
}

func NewMilkDecorator(coffee Coffee) *MilkDecorator {
	if coffee == nil {
		panic("coffee should not be nil")
	}
	return &MilkDecorator{coffee: coffee}
}

func (c *MilkDecorator) Cost() int {
	return c.coffee.Cost() + 2
}

func (c *MilkDecorator) Description() string {
	return fmt.Sprintf("%s, milk", c.coffee.Description())
}

type SugarDecorator struct {
	coffee Coffee
}

func NewSugarDecorator(coffee Coffee) *SugarDecorator {
	if coffee == nil {
		panic("coffee should not be nil")
	}
	return &SugarDecorator{coffee: coffee}
}

func (c *SugarDecorator) Cost() int {
	return c.coffee.Cost() + 1
}

func (c *SugarDecorator) Description() string {
	return fmt.Sprintf("%s, sugar", c.coffee.Description())
}

func main() {
	var coffee Coffee = &SimpleCoffee{}
	fmt.Printf("%s: %d\n", coffee.Description(), coffee.Cost()) // Simple coffee: 10

	coffee = NewMilkDecorator(coffee)
	fmt.Printf("%s: %d\n", coffee.Description(), coffee.Cost()) // Simple coffee, milk: 12

	coffee = NewSugarDecorator(coffee)
	fmt.Printf("%s: %d\n", coffee.Description(), coffee.Cost()) // Simple coffee, milk, sugar: 13
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Coffee {

    int cost();
    String description();
}

class SimpleCoffee implements Coffee {

    public int cost() {
        return 10;
    }

    public String description() {
        return "Simple coffee";
    }
}

class MilkDecorator implements Coffee {
    private final Coffee coffee;

    public MilkDecorator(Coffee coffee) {
        if(coffee == null)
            throw new IllegalArgumentException("coffee should not be null");
        this.coffee = coffee;
    }

    public int cost() {
        return coffee.cost() + 2;
    }

    public String description() {
        return coffee.description() + ", milk";
    }
}

class SugarDecorator implements Coffee {
    private final Coffee coffee;

    public SugarDecorator(Coffee coffee) {
        if(coffee == null)
            throw new IllegalArgumentException("coffee should not be null");
        this.coffee = coffee;
    }

    public int cost() {
        return coffee.cost() + 1;
    }

    public String description() {
        return coffee.description() + ", sugar";
    }
}

// ----------------------------

Coffee coffee = new SimpleCoffee();
System.out.println(coffee.description() + ": " + coffee.cost()); // Simple coffee: 10

coffee = new MilkDecorator(coffee);
System.out.println(coffee.description() + ": " + coffee.cost()); // Simple coffee, milk: 12

coffee = new SugarDecorator(coffee);
System.out.println(coffee.description() + ": " + coffee.cost()); // Simple coffee, milk, sugar: 13
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <memory>

// Coffee interface
class Coffee {
public:
    virtual ~Coffee() = default;
    virtual int cost() const = 0;
    virtual std::string description() const = 0;
};

// Simple coffee
class SimpleCoffee : public Coffee {
public:
    int cost() const override {
        return 10;
    }

    std::string description() const override {
        return "Simple coffee";
    }
};

// Milk decorator
class MilkDecorator : public Coffee {
    std::unique_ptr<Coffee> coffee;

public:
    MilkDecorator(std::unique_ptr<Coffee> coffee) : coffee(std::move(coffee)) {}

    int cost() const override {
        return coffee->cost() + 2;
    }

    std::string description() const override {
        return coffee->description() + ", milk";
    }
};

// Sugar decorator
class SugarDecorator : public Coffee {
    std::unique_ptr<Coffee> coffee;

public:
    SugarDecorator(std::unique_ptr<Coffee> coffee) : coffee(std::move(coffee)) {}

    int cost() const override {
        return coffee->cost() + 1;
    }

    std::string description() const override {
        return coffee->description() + ", sugar";
    }
};

// Usage
int main() {
    std::unique_ptr<Coffee> coffee = std::make_unique<SimpleCoffee>();
    std::cout << coffee->description() << ": " << coffee->cost() << std::endl; // Simple coffee: 10

    coffee = std::make_unique<MilkDecorator>(std::move(coffee));
    std::cout << coffee->description() << ": " << coffee->cost() << std::endl; // Simple coffee, milk: 12

    coffee = std::make_unique<SugarDecorator>(std::move(coffee));
    std::cout << coffee->description() << ": " << coffee->cost() << std::endl; // Simple coffee, milk, sugar: 13

    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Coffee {
    fun cost(): Int
    fun description(): String
}

class SimpleCoffee : Coffee {
    override fun cost() = 10
    override fun description() = "Simple coffee"
}

class MilkDecorator(private val coffee: Coffee) : Coffee {
    override fun cost() = coffee.cost() + 2
    override fun description() = coffee.description() + ", milk"
}

class SugarDecorator(private val coffee: Coffee) : Coffee {
    override fun cost() = coffee.cost() + 1
    override fun description() = coffee.description() + ", sugar"
}

// ----------------------------

fun main() {
    var coffee: Coffee = SimpleCoffee()
    println("${coffee.description()}: ${coffee.cost()}")

    coffee = MilkDecorator(coffee)
    println("${coffee.description()}: ${coffee.cost()}")

    coffee = SugarDecorator(coffee)
    println("${coffee.description()}: ${coffee.cost()}")
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Coffee {
  int cost();
  String description();
}

class SimpleCoffee implements Coffee {
  @override
  int cost() => 10;

  @override
  String description() => "Simple coffee";
}

class MilkDecorator implements Coffee {
  final Coffee _coffee;

  MilkDecorator(this._coffee);

  @override
  int cost() => _coffee.cost() + 2;

  @override
  String description() => _coffee.description() + ", milk";
}

class SugarDecorator implements Coffee {
  final Coffee _coffee;

  SugarDecorator(this._coffee);

  @override
  int cost() => _coffee.cost() + 1;

  @override
  String description() => _coffee.description() + ", sugar";
}

// ----------------------------

void main() {
  Coffee coffee = SimpleCoffee();
  print("${coffee.description()}: ${coffee.cost()}");

  coffee = MilkDecorator(coffee);
  print("${coffee.description()}: ${coffee.cost()}");

  coffee = SugarDecorator(coffee);
  print("${coffee.description()}: ${coffee.cost()}");
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی می‌خوای قابلیت‌ها رو لایه‌لایه و موقع اجرا به یه آبجکت اضافه کنی، بدون اینکه کلاسش رو دست بزنی»؛ ❌ «وقتی فقط یکی دو حالت ثابت داری و یه ساب‌کلاس ساده کافیه».
> 🪤 **دام رایج:** «وقتی ده‌ها لایه روی هم می‌پیچی، دنبال کردن مسیر و دیباگ کردنش سخت و گیج‌کننده می‌شه».
> 🔗 **فرقش با [پراکسی (Proxy)](#پراکسی-proxy-):** «دکوریتور قابلیت تازه به آبجکت اضافه می‌کنه؛ پراکسی همون رفتار رو نگه می‌داره ولی دسترسی بهش رو کنترل می‌کنه».


<br>

---

<div align="center">

## نما (Facade) 📦

</div>

<div align="center">
💻 <b>مثال دنیای واقعی: دکمه پاور لپ‌تاپ</b>
</div>

تو برای روشن کردن لپ‌تاپ فقط یه کار می‌کنی: دکمه پاور رو می‌زنی.
ولی پشت همون یک دکمه، کلی کار ریز و درشت اتفاق می‌افته: برق‌رسانی، چک کردن سخت‌افزار، بوت شدن سیستم‌عامل، بالا اومدن سرویس‌ها و...

تو نه لازم داری این مراحل رو حفظ باشی، نه دوست داری هر بار ۱۰ تا دکمه بزنی. فقط می‌خوای «روشن بشه». 😄

💡 **به زبون ساده:**
> این پترن می‌گه: **«برای یک سیستم شلوغ و پیچیده، یه ورودیِ ساده و خوش‌دست درست کن.»**
> کاربر فقط با همون ورودی ساده کار می‌کنه و جزئیاتِ پشت پرده قایم می‌مونه.

ویکی‌پدیا:

<div dir="ltr">

> A facade is an object that provides a simplified interface to a larger body of code, such as a class library.

</div>

نما یه آبجکته که یه رابط ساده‌شده جلوی یه تیکه کدِ بزرگ‌تر می‌ذاره، مثل یه کتابخونه کلاس‌ها. تو با همون رابط ساده کار می‌کنی و درگیر پیچیدگی پشتش نمی‌شی.

**مثال برنامه‌نویسی**

بیا همون مثال مربوط به کامپیوتر رو پیاده‌سازی کنیم!

اول باید کلاس کامپیوتر رو بسازیم.

کلاس Facade این‌طوری کار می‌کنه: یه آبجکت رو به عنوان ورودی می‌گیره و با هر تابعش یه سری کار روی اون آبجکت انجام می‌ده.

<details>

<summary>Python</summary>

<div dir="ltr">

```python
class Computer:
    def getElectricShock(self):
        print("Ouch!")

    def makeSound(self):
        print("Beep beep!")

    def showLoadingScreen(self):
        print("Loading..")

    def bam(self):
        print("Ready to be used!")

    def closeEverything(self):
        print("Bup bup..")

    def pullCurrent(self):
        print("Haaah!")

    def sooth(self):
        print("Zzzzz")


class ComputerFacade:
    def __init__(self, computer):
        self.computer = computer

    def turnOn(self):
        self.computer.getElectricShock()
        self.computer.makeSound()
        self.computer.showLoadingScreen()
        self.computer.bam()

    def turnOff(self):
        self.computer.closeEverything()
        self.computer.pullCurrent()
        self.computer.sooth()


# ----------------------------

computer = ComputerFacade(Computer())
computer.turnOn()
computer.turnOff()

'''
Output:
Ouch!
Beep beep!
Loading..
Ready to be used!
Bup bup..
Haaah!
Zzzzz
'''
```

</div>

</details>

<details>

<summary>TypeScript</summary>

<div dir="ltr">

```typescript
class Computer {
    getElectricShock() {
        console.log("Ouch!");
    }

    makeSound() {
        console.log("Beep beep!");
    }

    showLoadingScreen() {
        console.log("Loading..");
    }

    bam() {
        console.log("Ready to be used!");
    }

    closeEverything() {
        console.log("Bup bup..");
    }

    pullCurrent() {
        console.log("Haaah!");
    }

    sooth() {
        console.log("Zzzzz");
    }
}

class ComputerFacade {
    private computer: Computer;

    constructor(computer: Computer) {
        this.computer = computer;
    }

    turnOn() {
        this.computer.getElectricShock();
        this.computer.makeSound();
        this.computer.showLoadingScreen();
        this.computer.bam();
    }

    turnOff() {
        this.computer.closeEverything();
        this.computer.pullCurrent();
        this.computer.sooth();
    }
}

// ----------------------------

const computer = new ComputerFacade(new Computer());
computer.turnOn();
computer.turnOff();

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz
```

</div>

</details>

<details>

<summary>JavaScript</summary>

<div dir="ltr">

```javascript
class Computer {
    getElectricShock() {
        console.log("Ouch!");
    }

    makeSound() {
        console.log("Beep beep!");
    }

    showLoadingScreen() {
        console.log("Loading..");
    }

    bam() {
        console.log("Ready to be used!");
    }

    closeEverything() {
        console.log("Bup bup..");
    }

    pullCurrent() {
        console.log("Haaah!");
    }

    sooth() {
        console.log("Zzzzz");
    }
}

class ComputerFacade {
    constructor(computer) {
        this.computer = computer;
    }

    turnOn() {
        this.computer.getElectricShock();
        this.computer.makeSound();
        this.computer.showLoadingScreen();
        this.computer.bam();
    }

    turnOff() {
        this.computer.closeEverything();
        this.computer.pullCurrent();
        this.computer.sooth();
    }
}

const computer = new ComputerFacade(new Computer());
computer.turnOn();
computer.turnOff();

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


class Computer
{
  public void GetElectricShock()
  {
    Console.WriteLine("Ouch!");
  }

  public void MakeSound()
  {
    Console.WriteLine("Beep beep!");
  }

  public void ShowLoadingScreen()
  {
    Console.WriteLine("Loading..");
  }

  public void Bam()
  {
    Console.WriteLine("Ready to be used!");
  }

  public void CloseEverything()
  {
    Console.WriteLine("Bup bup..");
  }

  public void PullCurrent()
  {
    Console.WriteLine("Haaah!");
  }

  public void Sooth()
  {
    Console.WriteLine("Zzzzz");
  }
}


class ComputerFacade
{
  private readonly Computer mComputer;

  public ComputerFacade(Computer computer)
  {
    this.mComputer = computer ?? throw new ArgumentNullException("computer", "computer cannot be null");
  }

  public void TurnOn()
  {
    mComputer.GetElectricShock();
    mComputer.MakeSound();
    mComputer.ShowLoadingScreen();
    mComputer.Bam();
  }

  public void TurnOff()
  {
    mComputer.CloseEverything();
    mComputer.PullCurrent();
    mComputer.Sooth();
  }
}

// ----------------------------

var computer = new ComputerFacade(new Computer());
computer.TurnOn();
computer.TurnOff();

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
class Computer
{
  public function getElectricShock()
  {
    echo "Ouch!" . PHP_EOL;
  }

  public function makeSound()
  {
    echo "Beep beep!" . PHP_EOL;
  }

  public function showLoadingScreen()
  {
    echo "Loading.." . PHP_EOL;
  }

  public function bam()
  {
    echo "Ready to be used!" . PHP_EOL;
  }

  public function closeEverything()
  {
    echo "Bup bup.." . PHP_EOL;
  }

  public function pullCurrent()
  {
    echo "Haaah!" . PHP_EOL;
  }

  public function sooth()
  {
    echo "Zzzzz" . PHP_EOL;
  }
}

class ComputerFacade
{
  public function __construct(private Computer $computer)
  {
  }

  public function turnOn()
  {
    $this->computer->getElectricShock();
    $this->computer->makeSound();
    $this->computer->showLoadingScreen();
    $this->computer->bam();
  }

  public function turnOff()
  {
    $this->computer->closeEverything();
    $this->computer->pullCurrent();
    $this->computer->sooth();
  }
}

$computerFacade = new ComputerFacade(new Computer());
$computerFacade->turnOn();
$computerFacade->turnOff();

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import (
    "fmt"
)

type computer struct{}

func (c *computer) getElectricShock() {
    fmt.Println("Ouch!")
}

func (c *computer) makeSound() {
    fmt.Println("Beep beep!")
}

func (c *computer) showLoadingScreen() {
    fmt.Println("Loading..")
}

func (c *computer) bam() {
    fmt.Println("Ready to be used!")
}

func (c *computer) closeEverything() {
    fmt.Println("Bup bup..")
}

func (c *computer) pullCurrent() {
    fmt.Println("Haaah!")
}

func (c *computer) sooth() {
    fmt.Println("Zzzzz")
}

type computerFacade struct {
    computer *computer
}

func newComputerFacade(c *computer) *computerFacade {
    if c == nil {
        panic("computer cannot be nil")
    }
    return &computerFacade{computer: c}
}

func (cf *computerFacade) turnOn() {
    cf.computer.getElectricShock()
    cf.computer.makeSound()
    cf.computer.showLoadingScreen()
    cf.computer.bam()
}

func (cf *computerFacade) turnOff() {
    cf.computer.closeEverything()
    cf.computer.pullCurrent()
    cf.computer.sooth()
}

func main() {
    c := newComputerFacade(&computer{})
    c.turnOn()
    c.turnOff()
}

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class Computer {
    public void getElectricShock() {
        System.out.println("Ouch!");
    }

    public void makeSound() {
        System.out.println("Beep beep!");
    }

    public void showLoadingScreen() {
        System.out.println("Loading..");
    }

    public void bam() {
        System.out.println("Ready to be used!");
    }

    public void closeEverything() {
        System.out.println("Bup bup..");
    }

    public void pullCurrent() {
        System.out.println("Haaah!");
    }

    public void sooth() {
        System.out.println("Zzzzz");
    }
}

class ComputerFacade {
    private Computer computer;

    public ComputerFacade(Computer computer) {
        if (computer == null)
            throw new IllegalArgumentException("computer cannot be null");
        this.computer = computer;
    }

    public void turnOn() {
        computer.getElectricShock();
        computer.makeSound();
        computer.showLoadingScreen();
        computer.bam();
    }

    public void turnOff() {
        computer.closeEverything();
        computer.pullCurrent();
        computer.sooth();
    }
}

// ----------------------------

ComputerFacade computer = new ComputerFacade(new Computer());
computer.turnOn();
computer.turnOff();

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

class Computer {
public:
    void getElectricShock() {
        std::cout << "Ouch!" << std::endl;
    }

    void makeSound() {
        std::cout << "Beep beep!" << std::endl;
    }

    void showLoadingScreen() {
        std::cout << "Loading.." << std::endl;
    }

    void bam() {
        std::cout << "Ready to be used!" << std::endl;
    }

    void closeEverything() {
        std::cout << "Bup bup.." << std::endl;
    }

    void pullCurrent() {
        std::cout << "Haaah!" << std::endl;
    }

    void sooth() {
        std::cout << "Zzzzz" << std::endl;
    }
};

class ComputerFacade {
private:
    Computer& computer;

public:
    ComputerFacade(Computer& comp) : computer(comp) {}

    void turnOn() {
        computer.getElectricShock();
        computer.makeSound();
        computer.showLoadingScreen();
        computer.bam();
    }

    void turnOff() {
        computer.closeEverything();
        computer.pullCurrent();
        computer.sooth();
    }
};

// ----------------------------

int main() {
    Computer comp;
    ComputerFacade computer(comp);
    computer.turnOn();
    computer.turnOff();
    return 0;
}

// Output:
// Ouch!
// Beep beep!
// Loading..
// Ready to be used!
// Bup bup..
// Haaah!
// Zzzzz
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
class Computer {
    fun getElectricShock() = println("Ouch!")
    fun makeSound() = println("Beep beep!")
    fun showLoadingScreen() = println("Loading..")
    fun bam() = println("Ready to be used!")
    fun closeEverything() = println("Bup bup..")
    fun pullCurrent() = println("Haaah!")
    fun sooth() = println("Zzzzz")
}

class ComputerFacade(private val computer: Computer) {
    fun turnOn() {
        computer.getElectricShock()
        computer.makeSound()
        computer.showLoadingScreen()
        computer.bam()
    }

    fun turnOff() {
        computer.closeEverything()
        computer.pullCurrent()
        computer.sooth()
    }
}

// ----------------------------

fun main() {
    val computer = ComputerFacade(Computer())
    computer.turnOn()
    computer.turnOff()
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
class Computer {
  void getElectricShock() => print('Ouch!');
  void makeSound() => print('Beep beep!');
  void showLoadingScreen() => print('Loading..');
  void bam() => print('Ready to be used!');
  void closeEverything() => print('Bup bup..');
  void pullCurrent() => print('Haaah!');
  void sooth() => print('Zzzzz');
}

class ComputerFacade {
  final Computer _computer;

  ComputerFacade(this._computer);

  void turnOn() {
    _computer.getElectricShock();
    _computer.makeSound();
    _computer.showLoadingScreen();
    _computer.bam();
  }

  void turnOff() {
    _computer.closeEverything();
    _computer.pullCurrent();
    _computer.sooth();
  }
}

// ----------------------------

void main() {
  var computer = ComputerFacade(Computer());
  computer.turnOn();
  computer.turnOff();
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یه زیرسیستم شلوغ و چندمرحله‌ای داری و می‌خوای یه ورودی ساده و خوش‌دست جلوش بذاری»؛ ❌ «وقتی فقط یه کلاس ساده داری که اصلاً پیچیدگی‌ای برای قایم کردن نداره».
> 🪤 **دام رایج:** «نما رو نکن یه گاد آبجکت (God Object) که خودش همه‌کاره‌ست؛ نما فقط هماهنگ‌کننده‌ست، نه انجام‌دهنده همه‌چی».


<br>

---

<div align="center">

## فلای‌وِیت (Flyweight) 🍃

</div>

<div align="center">
🍵 <b>مثال دنیای واقعی: غرفه چای</b>
</div>

توی غرفه چای معمولاً یه دیگ چای آماده هست و فروشنده فقط برای هر نفر یه لیوان می‌ریزه.
یعنی برای ۱۰۰ تا مشتری قرار نیست ۱۰۰ بار «چای رو از صفر درست کنه». بخش اصلی و مشترک، یعنی خودِ چای، رو نگه می‌داره و فقط چیزهای متفاوتِ هر نفر رو جدا حساب می‌کنه؛ مثلاً «کم‌شکر»، «با شیر» یا «لیوانِ میز ۵».

💡 **به زبون ساده:**
> این پترن می‌گه: **«بخش‌های مشترکِ آبجکت‌ها رو به اشتراک بذار؛ تفاوت‌ها رو از بیرون بهش بده.»**
> نتیجه؟ وقتی تعداد آبجکت‌ها خیلی زیاد می‌شه، حافظه و هزینه ساختن‌شون کمتر می‌شه.

ویکی‌پدیا:

<div dir="ltr">

> In computer programming, flyweight is a software design pattern. A flyweight is an object that minimizes memory use by
> sharing as much data as possible with other similar objects; it is a way to use objects in large numbers when a simple
> repeated representation would use an unacceptable amount of memory.

</div>

به زبون خودمون: فلای‌وِیت هرچی داده مشترک داره رو بین آبجکت‌های شبیه هم پخش می‌کنه تا حافظه کمتری بخورن.
وقتی قراره کلی آبجکتِ شبیه هم بسازی و این‌همه نسخه تکراری داره حافظه رو می‌بلعه، این پترن به دادت می‌رسه.

**مثال برنامه‌نویسی**

بیا مثال غرفه چای رو پیاده کنیم. اول باید چای و چای‌ساز رو بسازیم.

بعدش یه کلاس `TeaShop` داریم که سفارش‌ها رو می‌گیره و آماده‌شون می‌کنه.

برای اینکه حواس‌مون پیشِ خودِ پترن بمونه، اینجا کلاس چای رو خالی گذاشتیم؛ توی دنیای واقعی همین آبجکتِ مشترک می‌تونه داده‌های سنگین رو نگه داره. نکته اصلی اینه که چای‌ساز برای هر «نوع» چای فقط یه بار آبجکت می‌سازه و دفعه‌های بعد همون رو پس می‌ده. شماره میز هم از بیرون به سفارش وصل می‌شه، نه داخل خودِ چای.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
# KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea:
    pass


# TeaMaker acts as the factory and caches one tea object per type.
class TeaMaker:
    def __init__(self):
        self.available_tea = {}

    def make(self, tea_type):
        if tea_type not in self.available_tea:
            self.available_tea[tea_type] = KarakTea()

        return self.available_tea[tea_type]

    def total_teas_made(self):
        return len(self.available_tea)


class TeaShop:
    def __init__(self, tea_maker):
        self.orders = {}
        self.tea_maker = tea_maker

    def take_order(self, tea_type, table):
        # Table number is the extrinsic state, passed in from outside.
        self.orders[table] = self.tea_maker.make(tea_type)

    def serve(self):
        for table in self.orders:
            print("Serving Karak Tea to table #" + str(table))


# ----------------------------

tea_maker = TeaMaker()
shop = TeaShop(tea_maker)

shop.take_order("Karak", 1)
shop.take_order("Karak", 3)
shop.take_order("Karak", 5)
shop.take_order("Karak", 7)
shop.take_order("Karak", 9)

shop.serve()

print("Total tea objects made: " + str(tea_maker.total_teas_made()))
# Serving Karak Tea to table #1
# Serving Karak Tea to table #3
# Serving Karak Tea to table #5
# Serving Karak Tea to table #7
# Serving Karak Tea to table #9
# Total tea objects made: 1
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea {
}

// TeaMaker acts as the factory and caches one tea object per type.
class TeaMaker {
    private availableTea: { [key: string]: KarakTea } = {};

    make(teaType: string): KarakTea {
        if (!(teaType in this.availableTea)) {
            this.availableTea[teaType] = new KarakTea();
        }

        return this.availableTea[teaType];
    }

    totalTeasMade(): number {
        return Object.keys(this.availableTea).length;
    }
}

class TeaShop {
    private orders: { [key: number]: KarakTea } = {};
    private teaMaker: TeaMaker;

    constructor(teaMaker: TeaMaker) {
        this.teaMaker = teaMaker;
    }

    takeOrder(teaType: string, table: number): void {
        // Table number is the extrinsic state, passed in from outside.
        this.orders[table] = this.teaMaker.make(teaType);
    }

    serve(): void {
        for (const table in this.orders) {
            console.log("Serving Karak Tea to table #" + table);
        }
    }
}

// ----------------------------

const teaMaker = new TeaMaker();
const shop = new TeaShop(teaMaker);

shop.takeOrder("Karak", 1);
shop.takeOrder("Karak", 3);
shop.takeOrder("Karak", 5);
shop.takeOrder("Karak", 7);
shop.takeOrder("Karak", 9);

shop.serve();

console.log("Total tea objects made: " + teaMaker.totalTeasMade());
// Serving Karak Tea to table #1
// Serving Karak Tea to table #3
// Serving Karak Tea to table #5
// Serving Karak Tea to table #7
// Serving Karak Tea to table #9
// Total tea objects made: 1
```

</div>

</details>

<details>

<summary>JavaScript</summary>

<div dir="ltr">

```javascript
// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea {
}

// TeaMaker acts as the factory and caches one tea object per type.
class TeaMaker {
    constructor() {
        this.availableTea = {};
    }

    make(teaType) {
        if (!(teaType in this.availableTea)) {
            this.availableTea[teaType] = new KarakTea();
        }

        return this.availableTea[teaType];
    }

    totalTeasMade() {
        return Object.keys(this.availableTea).length;
    }
}

class TeaShop {
    constructor(teaMaker) {
        this.orders = {};
        this.teaMaker = teaMaker;
    }

    takeOrder(teaType, table) {
        // Table number is the extrinsic state, passed in from outside.
        this.orders[table] = this.teaMaker.make(teaType);
    }

    serve() {
        for (const table in this.orders) {
            console.log("Serving Karak Tea to table #" + table);
        }
    }
}


const teaMaker = new TeaMaker();
const shop = new TeaShop(teaMaker);

shop.takeOrder("Karak", 1);
shop.takeOrder("Karak", 3);
shop.takeOrder("Karak", 5);
shop.takeOrder("Karak", 7);
shop.takeOrder("Karak", 9);

shop.serve();

console.log("Total tea objects made: " + teaMaker.totalTeasMade());
// Serving Karak Tea to table #1
// Serving Karak Tea to table #3
// Serving Karak Tea to table #5
// Serving Karak Tea to table #7
// Serving Karak Tea to table #9
// Total tea objects made: 1
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;
using System.Collections.Generic;


// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea
{
}

// Acts as a factory and caches one tea object per type.
class TeaMaker
{
  private Dictionary<string, KarakTea> mAvailableTea = new Dictionary<string, KarakTea>();

  public KarakTea Make(string teaType)
  {
    if (!mAvailableTea.ContainsKey(teaType))
    {
      mAvailableTea[teaType] = new KarakTea();
    }

    return mAvailableTea[teaType];
  }

  public int TotalTeasMade()
  {
    return mAvailableTea.Count;
  }
}

class TeaShop
{
  private Dictionary<int, KarakTea> mOrders = new Dictionary<int, KarakTea>();
  private readonly TeaMaker mTeaMaker;

  public TeaShop(TeaMaker teaMaker)
  {
    mTeaMaker = teaMaker ?? throw new ArgumentNullException("teaMaker", "teaMaker cannot be null");
  }

  public void TakeOrder(string teaType, int table)
  {
    // Table number is the extrinsic state, passed in from outside.
    mOrders[table] = mTeaMaker.Make(teaType);
  }

  public void Serve()
  {
    foreach (var table in mOrders.Keys)
    {
      Console.WriteLine("Serving Karak Tea to table #" + table);
    }
  }
}

// ----------------------------

var teaMaker = new TeaMaker();
var teaShop = new TeaShop(teaMaker);

teaShop.TakeOrder("Karak", 1);
teaShop.TakeOrder("Karak", 3);
teaShop.TakeOrder("Karak", 5);
teaShop.TakeOrder("Karak", 7);
teaShop.TakeOrder("Karak", 9);

teaShop.Serve();

Console.WriteLine("Total tea objects made: " + teaMaker.TotalTeasMade());
// Serving Karak Tea to table #1
// Serving Karak Tea to table #3
// Serving Karak Tea to table #5
// Serving Karak Tea to table #7
// Serving Karak Tea to table #9
// Total tea objects made: 1

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea
{
}

// Acts as a factory and caches one tea object per type.
class TeaMaker
{
  private array $mAvailableTea = [];

  public function make(string $teaType): KarakTea
  {
    if (!array_key_exists($teaType, $this->mAvailableTea)) {
      $this->mAvailableTea[$teaType] = new KarakTea();
    }

    return $this->mAvailableTea[$teaType];
  }

  public function totalTeasMade(): int
  {
    return count($this->mAvailableTea);
  }
}

class TeaShop
{
  private array $mOrders = [];

  public function __construct(private TeaMaker $teaMaker)
  {
  }

  public function takeOrder(string $teaType, int $table): void
  {
    // Table number is the extrinsic state, passed in from outside.
    $this->mOrders[$table] = $this->teaMaker->make($teaType);
  }

  public function serve(): void
  {
    foreach ($this->mOrders as $table => $tea) {
      echo "Serving Karak Tea to table #$table\n";
    }
  }
}

$teaMaker = new TeaMaker();
$teaShop = new TeaShop($teaMaker);

$teaShop->takeOrder("Karak", 1);
$teaShop->takeOrder("Karak", 3);
$teaShop->takeOrder("Karak", 5);
$teaShop->takeOrder("Karak", 7);
$teaShop->takeOrder("Karak", 9);

$teaShop->serve();

echo "Total tea objects made: " . $teaMaker->totalTeasMade() . "\n";
// Serving Karak Tea to table #1
// Serving Karak Tea to table #3
// Serving Karak Tea to table #5
// Serving Karak Tea to table #7
// Serving Karak Tea to table #9
// Total tea objects made: 1


```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

// KarakTea is the flyweight: the shared, intrinsic part.
type KarakTea struct{}

// TeaMaker acts as the factory and caches one tea object per type.
type TeaMaker struct {
    mAvailableTea map[string]*KarakTea
}

func NewTeaMaker() *TeaMaker {
    return &TeaMaker{mAvailableTea: make(map[string]*KarakTea)}
}

func (tm *TeaMaker) Make(teaType string) *KarakTea {
    if _, ok := tm.mAvailableTea[teaType]; !ok {
        tm.mAvailableTea[teaType] = &KarakTea{}
    }
    return tm.mAvailableTea[teaType]
}

func (tm *TeaMaker) TotalTeasMade() int {
    return len(tm.mAvailableTea)
}

type TeaShop struct {
    mTables   []int
    mOrders   map[int]*KarakTea
    mTeaMaker *TeaMaker
}

func NewTeaShop(teaMaker *TeaMaker) *TeaShop {
    return &TeaShop{
        mOrders:   make(map[int]*KarakTea),
        mTeaMaker: teaMaker,
    }
}

func (ts *TeaShop) TakeOrder(teaType string, table int) {
    // Table number is the extrinsic state, passed in from outside.
    if _, ok := ts.mOrders[table]; !ok {
        ts.mTables = append(ts.mTables, table)
    }
    ts.mOrders[table] = ts.mTeaMaker.Make(teaType)
}

func (ts *TeaShop) Serve() {
    for _, table := range ts.mTables {
        fmt.Printf("Serving Karak Tea to table #%d\n", table)
    }
}
// ---------------------------
teaMaker := NewTeaMaker()
teaShop := NewTeaShop(teaMaker)

teaShop.TakeOrder("Karak", 1)
teaShop.TakeOrder("Karak", 3)
teaShop.TakeOrder("Karak", 5)
teaShop.TakeOrder("Karak", 7)
teaShop.TakeOrder("Karak", 9)

teaShop.Serve()

fmt.Printf("Total tea objects made: %d\n", teaMaker.TotalTeasMade())
// Serving Karak Tea to table #1
// Serving Karak Tea to table #3
// Serving Karak Tea to table #5
// Serving Karak Tea to table #7
// Serving Karak Tea to table #9
// Total tea objects made: 1

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
import java.util.*;

// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea {
}

// Acts as a factory and caches one tea object per type.
class TeaMaker {
    private Map<String, KarakTea> availableTea = new HashMap<>();

    public KarakTea make(String teaType) {
        if (!availableTea.containsKey(teaType)) {
            availableTea.put(teaType, new KarakTea());
        }
        return availableTea.get(teaType);
    }

    public int totalTeasMade() {
        return availableTea.size();
    }
}

class TeaShop {
    private Map<Integer, KarakTea> orders = new LinkedHashMap<>();
    private TeaMaker teaMaker;

    public TeaShop(TeaMaker teaMaker) {
        if (teaMaker == null)
            throw new IllegalArgumentException("teaMaker cannot be null");
        this.teaMaker = teaMaker;
    }

    public void takeOrder(String teaType, int table) {
        // Table number is the extrinsic state, passed in from outside.
        orders.put(table, teaMaker.make(teaType));
    }

    public void serve() {
        for (Integer table : orders.keySet()) {
            System.out.println("Serving Karak Tea to table #" + table);
        }
    }
}

// ----------------------------

TeaMaker teaMaker = new TeaMaker();
TeaShop teaShop = new TeaShop(teaMaker);

teaShop.takeOrder("Karak", 1);
teaShop.takeOrder("Karak", 3);
teaShop.takeOrder("Karak", 5);
teaShop.takeOrder("Karak", 7);
teaShop.takeOrder("Karak", 9);

teaShop.serve();

System.out.println("Total tea objects made: " + teaMaker.totalTeasMade());
// Serving Karak Tea to table #1
// Serving Karak Tea to table #3
// Serving Karak Tea to table #5
// Serving Karak Tea to table #7
// Serving Karak Tea to table #9
// Total tea objects made: 1
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <unordered_map>
#include <string>
#include <vector>

// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea {
    // Tea implementation
};

// TeaMaker acts as the factory and caches one tea object per type.
class TeaMaker {
private:
    std::unordered_map<std::string, KarakTea*> availableTea;

public:
    KarakTea* make(const std::string& teaType) {
        if (availableTea.find(teaType) == availableTea.end()) {
            availableTea[teaType] = new KarakTea();
        }
        return availableTea[teaType];
    }

    int totalTeasMade() const {
        return availableTea.size();
    }
};

class TeaShop {
private:
    std::vector<int> tables;
    std::unordered_map<int, KarakTea*> orders;
    TeaMaker& teaMaker;

public:
    TeaShop(TeaMaker& maker) : teaMaker(maker) {}

    void takeOrder(const std::string& teaType, int table) {
        // Table number is the extrinsic state, passed in from outside.
        if (orders.find(table) == orders.end()) {
            tables.push_back(table);
        }
        orders[table] = teaMaker.make(teaType);
    }

    void serve() {
        for (int table : tables) {
            std::cout << "Serving Karak Tea to table #" << table << std::endl;
        }
    }
};

// ----------------------------

int main() {
    TeaMaker teaMaker;
    TeaShop teaShop(teaMaker);

    teaShop.takeOrder("Karak", 1);
    teaShop.takeOrder("Karak", 3);
    teaShop.takeOrder("Karak", 5);
    teaShop.takeOrder("Karak", 7);
    teaShop.takeOrder("Karak", 9);

    teaShop.serve();

    std::cout << "Total tea objects made: " << teaMaker.totalTeasMade() << std::endl;
    // Serving Karak Tea to table #1
    // Serving Karak Tea to table #3
    // Serving Karak Tea to table #5
    // Serving Karak Tea to table #7
    // Serving Karak Tea to table #9
    // Total tea objects made: 1
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea

// TeaMaker acts as the factory and caches one tea object per type.
class TeaMaker {
    private val availableTea = mutableMapOf<String, KarakTea>()

    fun make(teaType: String): KarakTea =
        availableTea.getOrPut(teaType) { KarakTea() }

    fun totalTeasMade(): Int = availableTea.size
}

class TeaShop(private val teaMaker: TeaMaker) {
    private val orders = mutableMapOf<Int, KarakTea>()

    fun takeOrder(teaType: String, table: Int) {
        // Table number is the extrinsic state, passed in from outside.
        orders[table] = teaMaker.make(teaType)
    }

    fun serve() {
        for (table in orders.keys) {
            println("Serving Karak Tea to table #" + table)
        }
    }
}

// ----------------------------

fun main() {
    val teaMaker = TeaMaker()
    val shop = TeaShop(teaMaker)

    shop.takeOrder("Karak", 1)
    shop.takeOrder("Karak", 3)
    shop.takeOrder("Karak", 5)
    shop.takeOrder("Karak", 7)
    shop.takeOrder("Karak", 9)

    shop.serve()

    println("Total tea objects made: " + teaMaker.totalTeasMade())
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
// KarakTea is the flyweight: the shared, intrinsic part.
class KarakTea {}

// TeaMaker acts as the factory and caches one tea object per type.
class TeaMaker {
  final Map<String, KarakTea> _availableTea = {};

  KarakTea make(String teaType) {
    return _availableTea.putIfAbsent(teaType, () => KarakTea());
  }

  int totalTeasMade() => _availableTea.length;
}

class TeaShop {
  final Map<int, KarakTea> _orders = {};
  final TeaMaker _teaMaker;

  TeaShop(this._teaMaker);

  void takeOrder(String teaType, int table) {
    // Table number is the extrinsic state, passed in from outside.
    _orders[table] = _teaMaker.make(teaType);
  }

  void serve() {
    for (var table in _orders.keys) {
      print('Serving Karak Tea to table #$table');
    }
  }
}

// ----------------------------

void main() {
  var teaMaker = TeaMaker();
  var shop = TeaShop(teaMaker);

  shop.takeOrder('Karak', 1);
  shop.takeOrder('Karak', 3);
  shop.takeOrder('Karak', 5);
  shop.takeOrder('Karak', 7);
  shop.takeOrder('Karak', 9);

  shop.serve();

  print('Total tea objects made: ${teaMaker.totalTeasMade()}');
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی قراره تعداد خیلی زیادی آبجکت بسازی که بخش بزرگی از داده‌شون مشترکه و حافظه داره می‌ترکه»؛ ❌ «وقتی آبجکت‌هات کم‌اند یا حالت مشترکی ندارن که بشه share کرد».
> 🪤 **دام رایج:** «به جای حالتِ مشترک و ثابت، روی حالتِ متغیر و بیرونی کش بگیری؛ اون‌وقت دیگه چیزی مشترک نمی‌مونه و کل ماجرا بی‌اثر می‌شه».


<br>

---

<div align="center">

## پراکسی (Proxy) 🎱

</div>

<div align="center">
🔐 <b>مثال دنیای واقعی: درِ رمزدار</b>
</div>

فرض کن یه درِ مهم داری (مثلاً درِ آزمایشگاه).
تو مستقیم سراغ خودِ در نمی‌ری؛ اول رمز می‌زنی یا کارت می‌کشی.

اگه رمز درست بود، در باز می‌شه. اگه غلط بود، اصلاً اجازه نمی‌ده به «درِ اصلی» دسترسی پیدا کنی.
اون قفل/کارت‌خوان دقیقاً نقش یه واسطه رو داره که قبل از رسیدن تو به شیء اصلی، یه سری کار اضافه انجام می‌ده (امنیت، لاگ، محدودیت، حتی کش!). 🛡️

💡 **به زبون ساده:**
> این پترن می‌گه: **«به جای دسترسی مستقیم به شیء اصلی، از یه واسطه استفاده کن که کنترل و قابلیت‌های اضافه بده.»**

ویکی‌پدیا:

<div dir="ltr">

> A proxy, in its most general form, is a class functioning as an interface to something else. A proxy is a wrapper or
> agent object that is being called by the client to access the real serving object behind the scenes. Use of the proxy
> can simply be forwarding to the real object, or can provide additional logic. In the proxy extra functionality can be
> provided, for example caching when operations on the real object are resource intensive, or checking preconditions
> before operations on the real object are invoked.

</div>

خلاصه‌اش این می‌شه که پراکسی یه کلاسه که نقش رابط رو برای یه شیء دیگه بازی می‌کنه.
کلاینت به جای اینکه مستقیم سراغ شیء اصلی بره، با همین پراکسی حرف می‌زنه و اون پشت‌صحنه درخواست رو به شیء واقعی می‌رسونه.
پراکسی می‌تونه فقط درخواست رو پاس بده، یا قبلش یه کار اضافه هم انجام بده؛ مثل کش کردن وقتی کار روی شیء اصلی سنگینه، یا چک کردن شرط‌ها قبل از اینکه به شیء اصلی دست بزنیم.

**مثال برنامه‌نویسی**

خب بیا مثال در رو پیاده کنیم.

اول اینترفیس در رو می‌سازیم و بعدش یه مدل واقعی از در پیاده می‌کنیم.
آخرش هم یه پراکسی می‌ذاریم روش که امنیت رو اضافه کنه.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Door:
    def open(self, password):
        raise NotImplementedError

    def close(self):
        raise NotImplementedError


class LabDoor(Door):
    def open(self, password):
        print("Opening lab door")

    def close(self):
        print("Closing lab door")


class SecurityProxy(Door):
    def __init__(self, door):
        self.door = door

    def open(self, password):
        if self.authenticate(password):
            self.door.open(password)
        else:
            print("Big no! It is not possible.")

    def authenticate(self, password):
        return password == "$ecr@t"

    def close(self):
        self.door.close()


# ----------------------------

door = SecurityProxy(LabDoor())
door.open("invalid")   # Big no! It is not possible.
door.open("$ecr@t")    # Opening lab door
door.close()           # Closing lab door
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface Door {
    open(password: string): void;
    close(): void;
}

class LabDoor implements Door {
    open(password: string): void {
        console.log("Opening lab door");
    }

    close(): void {
        console.log("Closing lab door");
    }
}

class SecurityProxy implements Door {
    private door: Door;

    constructor(door: Door) {
        this.door = door;
    }

    open(password: string): void {
        if (this.authenticate(password)) {
            this.door.open(password);
        } else {
            console.log("Big no! It is not possible.");
        }
    }

    private authenticate(password: string): boolean {
        return password === "$ecr@t";
    }

    close(): void {
        this.door.close();
    }
}

// ----------------------------

const door = new SecurityProxy(new LabDoor());
door.open("invalid");   // Big no! It is not possible.
door.open("$ecr@t");    // Opening lab door
door.close();           // Closing lab door
```

</div>

</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class LabDoor {
    open(password) {
        console.log("Opening lab door");
    }

    close() {
        console.log("Closing lab door");
    }
}

class SecurityProxy {
    constructor(door) {
        this.door = door;
    }

    open(password) {
        if (this.authenticate(password)) {
            this.door.open(password);
        } else {
            console.log("Big no! It is not possible.");
        }
    }

    authenticate(password) {
        return password === "$ecr@t";
    }

    close() {
        this.door.close();
    }
}


const door = new SecurityProxy(new LabDoor());
door.open("invalid");   // Big no! It is not possible.
door.open("$ecr@t");    // Opening lab door
door.close();           // Closing lab door
```

</div>

</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface IDoor
{
  void Open(string password);
  void Close();
}

class LabDoor : IDoor
{
  public void Open(string password)
  {
    Console.WriteLine("Opening lab door");
  }

  public void Close()
  {
    Console.WriteLine("Closing lab door");
  }
}

class SecurityProxy : IDoor
{
  private IDoor mDoor;

  public SecurityProxy(IDoor door)
  {
    mDoor = door ?? throw new ArgumentNullException("door", "door can not be null");
  }

  public void Open(string password)
  {
    if (Authenticate(password))
    {
      mDoor.Open(password);
    }
    else
    {
      Console.WriteLine("Big no! It is not possible.");
    }
  }

  private bool Authenticate(string password)
  {
    return password == "$ecr@t";
  }

  public void Close()
  {
    mDoor.Close();
  }
}

// ----------------------------

IDoor door = new SecurityProxy(new LabDoor());
door.Open("invalid"); // Big no! It is not possible.
door.Open("$ecr@t");  // Opening lab door
door.Close();         // Closing lab door

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface DoorInterface {
  public function open(string $password);
  public function close();
}

class LabDoor implements DoorInterface {
  public function open(string $password) {
    echo "Opening lab door\n";
  }

  public function close() {
    echo "Closing lab door\n";
  }
}

class SecurityProxy implements DoorInterface {
  public function __construct(private DoorInterface $door) {
  }

  public function open(string $password) {
    if ($this->authenticate($password)) {
      $this->door->open($password);
    } else {
      echo "Big no! It is not possible.\n";
    }
  }

  private function authenticate(string $password): bool {
    return $password === '$ecr@t';
  }

  public function close() {
    $this->door->close();
  }
}

$door = new SecurityProxy(new LabDoor());
$door->open('invalid');  // Big no! It is not possible.
$door->open('$ecr@t');   // Opening lab door
$door->close();          // Closing lab door
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Door interface {
    Open(password string)
    Close()
}

type LabDoor struct{}

func (d LabDoor) Open(password string) {
    fmt.Println("Opening lab door")
}

func (d LabDoor) Close() {
    fmt.Println("Closing lab door")
}

type SecurityProxy struct {
    door Door
}

func NewSecurityProxy(door Door) *SecurityProxy {
    return &SecurityProxy{door: door}
}

func (d *SecurityProxy) Open(password string) {
    if d.authenticate(password) {
        d.door.Open(password)
    } else {
        fmt.Println("Big no! It is not possible.")
    }
}

func (d *SecurityProxy) authenticate(password string) bool {
    return password == "$ecr@t"
}

func (d *SecurityProxy) Close() {
    d.door.Close()
}

func main() {
    door := NewSecurityProxy(LabDoor{})
    door.Open("invalid") // Big no! It is not possible.
    door.Open("$ecr@t")  // Opening lab door
    door.Close()         // Closing lab door
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Door {
    void open(String password);
    void close();
}

class LabDoor implements Door {
    public void open(String password) {
        System.out.println("Opening lab door");
    }

    public void close() {
        System.out.println("Closing lab door");
    }
}

class SecurityProxy implements Door {
    private Door door;

    public SecurityProxy(Door door) {
        if (door == null)
            throw new IllegalArgumentException("door can not be null");
        this.door = door;
    }

    @Override
    public void open(String password) {
        if (authenticate(password)) {
            door.open(password);
        } else {
            System.out.println("Big no! It is not possible.");
        }
    }

    private boolean authenticate(String password) {
        return "$ecr@t".equals(password);
    }

    @Override
    public void close() {
        door.close();
    }
}

// ----------------------------

Door door = new SecurityProxy(new LabDoor());

door.open("invalid");       // Big no! It is not possible.
door.open("$ecr@t");        // Opening lab door
door.close();               // Closing lab door
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>

class Door {
public:
    virtual ~Door() = default;
    virtual void open(const std::string& password) = 0;
    virtual void close() = 0;
};

class LabDoor : public Door {
public:
    void open(const std::string& password) override {
        std::cout << "Opening lab door" << std::endl;
    }

    void close() override {
        std::cout << "Closing lab door" << std::endl;
    }
};

class SecurityProxy : public Door {
private:
    Door& door;

    bool authenticate(const std::string& password) {
        return password == "$ecr@t";
    }

public:
    SecurityProxy(Door& d) : door(d) {}

    void open(const std::string& password) override {
        if (authenticate(password)) {
            door.open(password);
        } else {
            std::cout << "Big no! It is not possible." << std::endl;
        }
    }

    void close() override {
        door.close();
    }
};

// ----------------------------

int main() {
    LabDoor labDoor;
    SecurityProxy door(labDoor);

    door.open("invalid");       // Big no! It is not possible.
    door.open("$ecr@t");        // Opening lab door
    door.close();               // Closing lab door
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface Door {
    fun open(password: String)
    fun close()
}

class LabDoor : Door {
    override fun open(password: String) = println("Opening lab door")
    override fun close() = println("Closing lab door")
}

class SecurityProxy(private val door: Door) : Door {
    override fun open(password: String) {
        if (authenticate(password)) {
            door.open(password)
        } else {
            println("Big no! It is not possible.")
        }
    }

    private fun authenticate(password: String): Boolean = password == "\$ecr@t"

    override fun close() {
        door.close()
    }
}

// ----------------------------

fun main() {
    val door = SecurityProxy(LabDoor())
    door.open("invalid")
    door.open("\$ecr@t")
    door.close()
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Door {
  void open(String password);
  void close();
}

class LabDoor implements Door {
  @override
  void open(String password) => print('Opening lab door');

  @override
  void close() => print('Closing lab door');
}

class SecurityProxy implements Door {
  final Door _door;

  SecurityProxy(this._door);

  @override
  void open(String password) {
    if (authenticate(password)) {
      _door.open(password);
    } else {
      print('Big no! It is not possible.');
    }
  }

  bool authenticate(String password) => password == r'$ecr@t';

  @override
  void close() => _door.close();
}

// ----------------------------

void main() {
  var door = SecurityProxy(LabDoor());
  door.open('invalid');
  door.open(r'$ecr@t');
  door.close();
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی می‌خوای دسترسی به یه شیء رو کنترل کنی یا قبل و بعدش یه کار اضافه (امنیت، کش، لاگ) بچسبونی، بی‌اینکه خودِ شیء اصلی عوض بشه؛ ❌ وقتی فقط می‌خوای رفتارش رو گسترش بدی نه کنترلش، که اون‌وقت کار دکوریتوره.
> 🪤 **دام رایج:** پراکسی رو این‌قدر چاق نکن که کم‌کم منطق اصلی بره توش و دیگه معلوم نباشه شیء واقعی کیه.
> 🔗 **فرقش با [دکوریتور (Decorator)](#دکوریتور-decorator-):** دکوریتور قابلیت تازه اضافه می‌کنه و خودش رو قاطی نمی‌کنه (کلاینت همون آبجکت رو می‌بینه)؛ پراکسی دسترسی رو واسطه‌گری و کنترل می‌کنه. فرقش با [مبدل (Adapter)](#مبدل-adapter-) هم اینه که مبدل اینترفیس رو عوض می‌کنه، ولی پراکسی همون اینترفیس رو نگه می‌داره.


<br>
<br>

---

<br>

<div align="center">

# الگوهای رفتاری (Behavioral Design Patterns) 🎭

</div>

به زبون ساده:

> این الگوها بهت می‌گن آبجکت‌ها چطور با هم حرف بزنن و کارها رو بین خودشون پاس بدن، بدون اینکه بدجوری به هم گره بخورن.

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, behavioral design patterns are design patterns that identify common communication patterns
> among objects. By doing so, these patterns increase flexibility in carrying out communication.

</div>

خلاصه: الگوهای رفتاری روی این تمرکز دارن که آبجکت‌ها چطور با هم حرف بزنن و کار رو بین خودشون تقسیم کنن.

<br>

---

<div align="center">

## زنجیره مسئولیت (Chain of Responsibility) 🔗

</div>

<div align="center">
💳 <b>مثال دنیای واقعی: پرداخت از چند حساب</b>
</div>

فرض کن ۳ تا منبع پول داری: حساب بانکی، حساب `PayPal` و کیف پول `Bitcoin`.
حالا می‌خوای یک خرید انجام بدی. منطقیه سیستم چی‌کار کنه؟
۱. اول تلاش کن از حساب بانکی پرداخت کنه.
۲. اگه موجودی کافی نبود، بره سراغ `PayPal`.
۳. اگه اونم نشد، بره سراغ `Bitcoin`.

یعنی درخواست پرداخت، توی یه مسیرِ مرحله‌به‌مرحله جلو می‌ره تا یکی بالاخره جواب بده. 🧾

💡 **به زبون ساده:**
> این پترن می‌گه: **«درخواست رو بنداز توی یک زنجیره؛ هر مرحله نتونست انجام بده، پاس بده مرحله بعدی.»**

ویکی‌پدیا:

<div dir="ltr">

> In object-oriented design, the chain-of-responsibility pattern is a design pattern consisting of a source of command
> objects and a series of processing objects. Each processing object contains logic that defines the types of command
> objects that it can handle; the rest are passed to the next processing object in the chain.

</div>

به زبون خودمون: یک منبعِ درخواست داریم و یک رشته پردازنده که پشت سر هم چیده شدن. هر پردازنده می‌دونه چه درخواستی رو خودش می‌تونه جواب بده؛ بقیه رو دست‌نخورده پاس می‌ده به پردازندهٔ بعدیِ زنجیره.

**مثال برنامه‌نویسی**

می‌خوایم همون مثال پرداخت رو باهم پیاده‌سازی کنیم.

بیا یه کلاس مرجع به اسم `Account` بسازیم که یه متد `pay` داره. این متد یه مقدار می‌گیره و سعی می‌کنه از حساب خودش پرداخت کنه؛ اگه موجودی کم بیاد، درخواست رو به حساب بعدی پاس می‌ده.

نکته:
متد `getName` هر حساب، اسم کلاس خودش (`Bank` یا `Paypal` یا `Bitcoin`) رو برمی‌گردونه؛ این کار رو با `type(self).__name__` انجام می‌ده. این‌جوری توی پیام پرداخت دقیقاً معلوم می‌شه کدوم حساب جواب داده.

حالا یه حساب بانکی، یه حساب `PayPal` و یه حساب `Bitcoin` می‌سازیم.

بعد که ساختیمشون، حساب‌ها رو به‌ترتیب به هم وصل می‌کنیم تا یه زنجیره بشن.

وقتی پرداخت رو شروع کنیم، اول می‌ره سراغ حساب بانکی. چون موجودیش کم میاد، درخواست رو پاس می‌ده به `PayPal` و این بار پرداخت می‌شه.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Account:
    _successor = None

    def setNext(self, account):
        self._successor = account

    def pay(self, amountToPay):
        if self.canPay(amountToPay):
            print("Paid " + str(amountToPay) + " using " + self.getName())
        elif self._successor:
            print("Cannot pay using " + self.getName() + ". Proceeding ..")
            self._successor.pay(amountToPay)
        else:
            print("None of the accounts have enough balance")

    def canPay(self, amount):
        return self.balance >= amount

    def getName(self):
        return type(self).__name__


class Bank(Account):
    def __init__(self, balance):
        self.balance = balance


class Paypal(Account):
    def __init__(self, balance):
        self.balance = balance


class Bitcoin(Account):
    def __init__(self, balance):
        self.balance = balance


# ----------------------------

bank = Bank(100)        # Bank with balance 100
paypal = Paypal(300)    # Paypal with balance 300
bitcoin = Bitcoin(1000) # Bitcoin with balance 1000

bank.setNext(paypal)
paypal.setNext(bitcoin)

bank.pay(259)


'''
Output will be
==============
Cannot pay using Bank. Proceeding ..
Paid 259 using Paypal
'''
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class Account {
    protected _successor: Account | null = null;
    protected _balance: number = 0;

    setNext(account: Account): void {
        this._successor = account;
    }

    pay(amountToPay: number): void {
        if (this.canPay(amountToPay)) {
            console.log(`Paid ${amountToPay} using ${this.getName()}`);
        } else if (this._successor) {
            console.log(`Cannot pay using ${this.getName()}. Proceeding ..`);
            this._successor.pay(amountToPay);
        } else {
            console.log("None of the accounts have enough balance");
        }
    }

    canPay(amount: number): boolean {
        return this._balance >= amount;
    }

    getName(): string {
        return this.constructor.name;
    }
}

class Bank extends Account {
    constructor(balance: number) {
        super();
        this._balance = balance;
    }
}

class Paypal extends Account {
    constructor(balance: number) {
        super();
        this._balance = balance;
    }
}

class Bitcoin extends Account {
    constructor(balance: number) {
        super();
        this._balance = balance;
    }
}

// ----------------------------

const bank = new Bank(100);        // Bank with balance 100
const paypal = new Paypal(300);    // Paypal with balance 300
const bitcoin = new Bitcoin(1000); // Bitcoin with balance 1000

bank.setNext(paypal);
paypal.setNext(bitcoin);

bank.pay(259);
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Account {
    constructor() {
        this._successor = null;
        this._balance = null;
    }

    setNext(account) {
        this._successor = account;
    }

    pay(amountToPay) {
        if (this.canPay(amountToPay)) {
            console.log(`Paid ${amountToPay} using ${this.getName()}`);
        } else if (this._successor) {
            console.log(`Cannot pay using ${this.getName()}. Proceeding ..`);
            this._successor.pay(amountToPay);
        } else {
            console.log("None of the accounts have enough balance");
        }
    }

    canPay(amount) {
        return this._balance >= amount;
    }

    getName() {
        return this.constructor.name;
    }
}

class Bank extends Account {
    constructor(balance) {
        super();
        this._balance = balance;
    }
}

class Paypal extends Account {
    constructor(balance) {
        super();
        this._balance = balance;
    }
}

class Bitcoin extends Account {
    constructor(balance) {
        super();
        this._balance = balance;
    }
}

// ----------------------------

const bank = new Bank(100);        // Bank with balance 100
const paypal = new Paypal(300);    // Paypal with balance 300
const bitcoin = new Bitcoin(1000); // Bitcoin with balance 1000

bank.setNext(paypal);
paypal.setNext(bitcoin);

bank.pay(259);
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;

abstract class Account
{
  private Account mSuccessor;
  protected int mBalance;

  public void SetNext(Account account)
  {
    mSuccessor = account;
  }

  public void Pay(int amountToPay)
  {
    if (CanPay(amountToPay))
    {
      Console.WriteLine($"Paid {amountToPay} using {this.GetType().Name}");
    }
    else if (this.mSuccessor != null)
    {
      Console.WriteLine($"Cannot pay using {this.GetType().Name}. Proceeding ..");
      mSuccessor.Pay(amountToPay);
    }
    else
    {
      Console.WriteLine("None of the accounts have enough balance");
    }
  }

  private bool CanPay(int amount)
  {
    return mBalance >= amount;
  }
}

class Bank : Account
{
  public Bank(int balance)
  {
    this.mBalance = balance;
  }
}

class Paypal : Account
{
  public Paypal(int balance)
  {
    this.mBalance = balance;
  }
}

class Bitcoin : Account
{
  public Bitcoin(int balance)
  {
    this.mBalance = balance;
  }
}

// ----------------------------

var bank = new Bank(100);        // Bank with balance 100
var paypal = new Paypal(300);    // Paypal with balance 300
var bitcoin = new Bitcoin(1000); // Bitcoin with balance 1000

bank.SetNext(paypal);
paypal.SetNext(bitcoin);

bank.Pay(259);
// Output will be
// ==============
// Cannot pay using Bank. Proceeding ..
// Paid 259 using Paypal
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
abstract class Account
{
    private $successor;
    protected $balance;

    public function setNext(Account $account)
    {
        $this->successor = $account;
    }

    public function pay($amountToPay)
    {
        if ($this->canPay($amountToPay)) {
            echo "Paid " . $amountToPay . " using " . get_class($this) . PHP_EOL;
        } elseif ($this->successor != null) {
            echo "Cannot pay using " . get_class($this) . ". Proceeding .." . PHP_EOL;
            $this->successor->pay($amountToPay);
        } else {
            echo "None of the accounts have enough balance" . PHP_EOL;
        }
    }

    private function canPay($amount)
    {
        return $this->balance >= $amount;
    }
}

class Bank extends Account
{
    public function __construct($balance)
    {
        $this->balance = $balance;
    }
}

class Paypal extends Account
{
    public function __construct($balance)
    {
        $this->balance = $balance;
    }
}

class Bitcoin extends Account
{
    public function __construct($balance)
    {
        $this->balance = $balance;
    }
}

// ----------------------------

$bank = new Bank(100);        // Bank with balance 100
$paypal = new Paypal(300);    // Paypal with balance 300
$bitcoin = new Bitcoin(1000); // Bitcoin with balance 1000

$bank->setNext($paypal);
$paypal->setNext($bitcoin);

$bank->pay(259);
// Output will be
// ==============
// Cannot pay using Bank. Proceeding ..
// Paid 259 using Paypal
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type payer interface {
	Pay(amountToPay int)
}

type Account struct {
	successor payer
	balance   int
	name      string
}

func (a *Account) SetNext(account payer) {
	a.successor = account
}

func (a *Account) Pay(amountToPay int) {
	if a.canPay(amountToPay) {
		fmt.Printf("Paid %d using %s\n", amountToPay, a.name)
	} else if a.successor != nil {
		fmt.Printf("Cannot pay using %s. Proceeding ..\n", a.name)
		a.successor.Pay(amountToPay)
	} else {
		fmt.Println("None of the accounts have enough balance")
	}
}

func (a *Account) canPay(amount int) bool {
	return a.balance >= amount
}

func NewBank(balance int) *Account {
	return &Account{balance: balance, name: "Bank"}
}

func NewPaypal(balance int) *Account {
	return &Account{balance: balance, name: "Paypal"}
}

func NewBitcoin(balance int) *Account {
	return &Account{balance: balance, name: "Bitcoin"}
}

func main() {
	bank := NewBank(100)        // Bank with balance 100
	paypal := NewPaypal(300)    // Paypal with balance 300
	bitcoin := NewBitcoin(1000) // Bitcoin with balance 1000

	bank.SetNext(paypal)
	paypal.SetNext(bitcoin)

	bank.Pay(259)
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
abstract class Account {
  private Account successor;
  protected Integer balance;

  public void setNext(Account account) {
    successor = account;
  }

  public void pay(Integer amountToPay) {
    String accountType = this.getClass().getSimpleName();
    if (canPay(amountToPay)) {
      System.out.println("Paid " + amountToPay + " using " + accountType);
    } else if (this.successor != null) {
      System.out.println("Cannot pay using " + accountType + ". Proceeding ..");
      successor.pay(amountToPay);
    } else {
      System.out.println("None of the accounts have enough balance");
    }
  }

  private boolean canPay(Integer amount) {
    return balance >= amount;
  }
}

class Bank extends Account {
  public Bank(Integer balance) {
    this.balance = balance;
  }
}

class Paypal extends Account {
  public Paypal(Integer balance) {
    this.balance = balance;
  }
}

class Bitcoin extends Account {
  public Bitcoin(Integer balance) {
    this.balance = balance;
  }
}

// ----------------------------

Bank bank = new Bank(100);           // Bank with balance 100
Paypal paypal = new Paypal(300);     // Paypal with balance 300
Bitcoin bitcoin = new Bitcoin(1000); // Bitcoin with balance 1000

bank.setNext(paypal);
paypal.setNext(bitcoin);

bank.pay(259);
// Output will be
// ==============
// Cannot pay using Bank. Proceeding ..
// Paid 259 using Paypal
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>

class Account {
protected:
    Account* successor = nullptr;
    int balance = 0;

public:
    virtual ~Account() = default;

    void setNext(Account* account) {
        successor = account;
    }

    void pay(int amountToPay) {
        if (canPay(amountToPay)) {
            std::cout << "Paid " << amountToPay << " using " << getName() << std::endl;
        } else if (successor != nullptr) {
            std::cout << "Cannot pay using " << getName() << ". Proceeding .." << std::endl;
            successor->pay(amountToPay);
        } else {
            std::cout << "None of the accounts have enough balance" << std::endl;
        }
    }

    virtual std::string getName() = 0;

private:
    bool canPay(int amount) {
        return balance >= amount;
    }
};

class Bank : public Account {
public:
    Bank(int bal) { balance = bal; }
    std::string getName() override { return "Bank"; }
};

class Paypal : public Account {
public:
    Paypal(int bal) { balance = bal; }
    std::string getName() override { return "Paypal"; }
};

class Bitcoin : public Account {
public:
    Bitcoin(int bal) { balance = bal; }
    std::string getName() override { return "Bitcoin"; }
};

// ----------------------------

int main() {
    Bank bank(100);        // Bank with balance 100
    Paypal paypal(300);    // Paypal with balance 300
    Bitcoin bitcoin(1000); // Bitcoin with balance 1000

    bank.setNext(&paypal);
    paypal.setNext(&bitcoin);

    bank.pay(259);
    // Cannot pay using Bank. Proceeding ..
    // Paid 259 using Paypal
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
abstract class Account(protected var balance: Int) {
    private var successor: Account? = null

    fun setNext(account: Account) {
        successor = account
    }

    fun pay(amountToPay: Int) {
        if (canPay(amountToPay)) {
            println("Paid " + amountToPay + " using " + getName())
        } else if (successor != null) {
            println("Cannot pay using " + getName() + ". Proceeding ..")
            successor!!.pay(amountToPay)
        } else {
            println("None of the accounts have enough balance")
        }
    }

    private fun canPay(amount: Int): Boolean = balance >= amount

    protected fun getName(): String = this::class.simpleName!!
}

class Bank(balance: Int) : Account(balance)

class Paypal(balance: Int) : Account(balance)

class Bitcoin(balance: Int) : Account(balance)

// ----------------------------

fun main() {
    val bank = Bank(100)        // Bank with balance 100
    val paypal = Paypal(300)    // Paypal with balance 300
    val bitcoin = Bitcoin(1000) // Bitcoin with balance 1000

    bank.setNext(paypal)
    paypal.setNext(bitcoin)

    bank.pay(259)
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Account {
  Account? _successor;
  late int balance;

  void setNext(Account account) {
    _successor = account;
  }

  void pay(int amountToPay) {
    if (canPay(amountToPay)) {
      print('Paid $amountToPay using ${getName()}');
    } else if (_successor != null) {
      print('Cannot pay using ${getName()}. Proceeding ..');
      _successor!.pay(amountToPay);
    } else {
      print('None of the accounts have enough balance');
    }
  }

  bool canPay(int amount) => balance >= amount;

  String getName() => runtimeType.toString();
}

class Bank extends Account {
  Bank(int balance) {
    this.balance = balance;
  }
}

class Paypal extends Account {
  Paypal(int balance) {
    this.balance = balance;
  }
}

class Bitcoin extends Account {
  Bitcoin(int balance) {
    this.balance = balance;
  }
}

// ----------------------------

void main() {
  var bank = Bank(100); // Bank with balance 100
  var paypal = Paypal(300); // Paypal with balance 300
  var bitcoin = Bitcoin(1000); // Bitcoin with balance 1000

  bank.setNext(paypal);
  paypal.setNext(bitcoin);

  bank.pay(259);
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یک درخواست چند تا پردازندهٔ احتمالی داره و نمی‌دونی کدوم بالاخره جوابش رو می‌ده، بسپارش به زنجیره»؛ ❌ «وقتی همیشه دقیقاً یک نفر مسئوله و مقصد از اول معلومه، زنجیره فقط شلوغش می‌کنه».
> 🪤 **دام رایج:** «اگه هیچ حلقه‌ای درخواست رو برنداره و ته زنجیره رو خالی بذاری، درخواست بی‌صدا گم می‌شه؛ همیشه حالت آخر رو مدیریت کن».


<br>

---

<div align="center">

## فرمان (Command) 👮

</div>

<div align="center">
🎮 <b>مثال دنیای واقعی: ریموت کنترل</b>
</div>

فرض کن یه ریموت داری و می‌خوای لامپ رو روشن/خاموش کنی.
ریموت خودش «لامپ» نیست و قرار هم نیست بدونه دقیقاً لامپ چطوری روشن می‌شه؛ فقط یه دستور آماده داره: «روشن کن» یا «خاموش کن».

حالا مزیتش چیه؟ چون دستورها آبجکت شدن، می‌تونی:
*   چندتا دستور رو صف کنی
*   لاگ بگیری چی اجرا شد
*   حتی (اگه خواستی) undo/redo هم اضافه کنی

💡 **به زبون ساده:**
> این پترن می‌گه: **«درخواست رو تبدیل کن به یک آبجکتِ مستقل (Command) تا فرستنده از اجراکننده جدا بشه.»**

ویکی‌پدیا:

<div dir="ltr">

> In object-oriented programming, the command pattern is a behavioral design pattern in which an object is used to
> encapsulate all information needed to perform an action or trigger an event at a later time. This information includes
> the method name, the object that owns the method and values for the method parameters.

</div>

خلاصه‌اش این می‌شه: توی برنامه‌نویسی شیءگرا، الگوی فرمان (Command) یه الگوی رفتاریه که یه درخواست رو می‌بنده توی یه آبجکت.
این آبجکت هر چیزی رو که برای اون کار لازمه نگه می‌داره: اسم متد، آبجکتی که متد رو داره، و مقدار پارامترها.
این‌جوری می‌تونی همون درخواست رو نگه داری و هر وقت خواستی بعداً اجراش کنی.

**مثال برنامه‌نویسی**

می‌خوایم یه ریموت برای لامپ بسازیم. سه تا تیکه داریم: خودِ لامپ که کارِ واقعی رو انجام می‌ده (Receiver)، دستورها مثل روشن و خاموش (Command)، و ریموتی که دستورها رو اجرا می‌کنه (Invoker).

اول لامپ رو می‌سازیم، بعد دستورهای روشن و خاموش کردن رو، و آخرش ریموت رو. بعد هر وقت بخوایم چراغ رو روشن یا خاموش کنیم، دستورش رو به ریموت می‌دیم و اون اجراش می‌کنه.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Bulb:
    def turnOn(self):
        print("Bulb has been lit")

    def turnOff(self):
        print("Darkness!")


class Command:
    def __init__(self, bulb):
        self._bulb = bulb

    def execute(self):
        pass

    def undo(self):
        pass


class TurnOn(Command):
    def execute(self):
        self._bulb.turnOn()

    def undo(self):
        self._bulb.turnOff()


class TurnOff(Command):
    def execute(self):
        self._bulb.turnOff()

    def undo(self):
        self._bulb.turnOn()


class RemoteControl:
    def submit(self, command):
        command.execute()


# ----------------------------

bulb = Bulb()

turnOn = TurnOn(bulb)
turnOff = TurnOff(bulb)

remote = RemoteControl()
remote.submit(turnOn)   # Bulb has been lit
remote.submit(turnOff)  # Darkness!

```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class Bulb {
    turnOn(): void {
        console.log("Bulb has been lit");
    }

    turnOff(): void {
        console.log("Darkness!");
    }
}

interface Command {
    execute(): void;
    undo(): void;
}

class TurnOn implements Command {
    constructor(private bulb: Bulb) {}

    execute(): void {
        this.bulb.turnOn();
    }

    undo(): void {
        this.bulb.turnOff();
    }
}

class TurnOff implements Command {
    constructor(private bulb: Bulb) {}

    execute(): void {
        this.bulb.turnOff();
    }

    undo(): void {
        this.bulb.turnOn();
    }
}

class RemoteControl {
    submit(command: Command): void {
        command.execute();
    }
}

// ----------------------------

const bulb = new Bulb();

const turnOn = new TurnOn(bulb);
const turnOff = new TurnOff(bulb);

const remote = new RemoteControl();
remote.submit(turnOn);  // Bulb has been lit
remote.submit(turnOff); // Darkness!
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Bulb {
    turnOn() {
        console.log("Bulb has been lit");
    }

    turnOff() {
        console.log("Darkness!");
    }
}

class Command {
    constructor(bulb) {
        this._bulb = bulb;
    }

    execute() {
    }

    undo() {
    }
}

class TurnOn extends Command {
    execute() {
        this._bulb.turnOn();
    }

    undo() {
        this._bulb.turnOff();
    }
}

class TurnOff extends Command {
    execute() {
        this._bulb.turnOff();
    }

    undo() {
        this._bulb.turnOn();
    }
}

class RemoteControl {
    submit(command) {
        command.execute();
    }
}

// ----------------------------

const bulb = new Bulb();

const turnOn = new TurnOn(bulb);
const turnOff = new TurnOff(bulb);

const remote = new RemoteControl();
remote.submit(turnOn);  // Bulb has been lit
remote.submit(turnOff); // Darkness!
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


// Receiver
class Bulb
{
  public void TurnOn()
  {
    Console.WriteLine("Bulb has been lit");
  }

  public void TurnOff()
  {
    Console.WriteLine("Darkness!");
  }
}

interface ICommand
{
  void Execute();
  void Undo();
}

// Command
class TurnOn : ICommand
{
  private Bulb mBulb;

  public TurnOn(Bulb bulb)
  {
    mBulb = bulb;
  }

  public void Execute()
  {
    mBulb.TurnOn();
  }

  public void Undo()
  {
    mBulb.TurnOff();
  }
}

class TurnOff : ICommand
{
  private Bulb mBulb;

  public TurnOff(Bulb bulb)
  {
    mBulb = bulb;
  }

  public void Execute()
  {
    mBulb.TurnOff();
  }

  public void Undo()
  {
    mBulb.TurnOn();
  }
}

// Invoker
class RemoteControl
{
  public void Submit(ICommand command)
  {
    command.Execute();
  }
}

// ----------------------------

var bulb = new Bulb();

var turnOn = new TurnOn(bulb);
var turnOff = new TurnOff(bulb);

var remote = new RemoteControl();
remote.Submit(turnOn);  // Bulb has been lit
remote.Submit(turnOff); // Darkness!

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
// Receiver
class Bulb
{
    public function turnOn()
    {
        echo "Bulb has been lit\n";
    }

    public function turnOff()
    {
        echo "Darkness!\n";
    }
}

interface CommandInterface
{
    public function execute();
    public function undo();
}

// Command
class TurnOn implements CommandInterface
{
    public function __construct(private Bulb $bulb)
    {
    }

    public function execute()
    {
        $this->bulb->turnOn();
    }

    public function undo()
    {
        $this->bulb->turnOff();
    }
}

class TurnOff implements CommandInterface
{
    public function __construct(private Bulb $bulb)
    {
    }

    public function execute()
    {
        $this->bulb->turnOff();
    }

    public function undo()
    {
        $this->bulb->turnOn();
    }
}

// Invoker
class RemoteControl
{
    public function submit(CommandInterface $command)
    {
        $command->execute();
    }
}

// Usage
$bulb = new Bulb();

$turnOn = new TurnOn($bulb);
$turnOff = new TurnOff($bulb);

$remote = new RemoteControl();
$remote->submit($turnOn);  // Bulb has been lit
$remote->submit($turnOff); // Darkness!

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

// Receiver
type Bulb struct{}

func (b *Bulb) TurnOn() {
    fmt.Println("Bulb has been lit")
}

func (b *Bulb) TurnOff() {
    fmt.Println("Darkness!")
}

// Command interface
type Command interface {
    Execute()
    Undo()
}

// Command
type TurnOnCommand struct {
    bulb *Bulb
}

func (c *TurnOnCommand) Execute() {
    c.bulb.TurnOn()
}

func (c *TurnOnCommand) Undo() {
    c.bulb.TurnOff()
}

type TurnOffCommand struct {
    bulb *Bulb
}

func (c *TurnOffCommand) Execute() {
    c.bulb.TurnOff()
}

func (c *TurnOffCommand) Undo() {
    c.bulb.TurnOn()
}

// Invoker
type RemoteControl struct{}

func (r *RemoteControl) Submit(command Command) {
    command.Execute()
}

func main() {
    bulb := &Bulb{}

    turnOn := &TurnOnCommand{bulb: bulb}
    turnOff := &TurnOffCommand{bulb: bulb}

    remote := &RemoteControl{}
    remote.Submit(turnOn)  // Bulb has been lit
    remote.Submit(turnOff) // Darkness!
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
// Receiver
class Bulb {
    public void turnOn() {
        System.out.println("Bulb has been lit");
    }

    public void turnOff() {
        System.out.println("Darkness!");
    }
}

interface Command {
    void execute();
    void undo();
}

// Command
class TurnOn implements Command {
    private Bulb bulb;

    public TurnOn(Bulb bulb) {
        this.bulb = bulb;
    }

    @Override
    public void execute() {
        bulb.turnOn();
    }

    @Override
    public void undo() {
        bulb.turnOff();
    }
}

class TurnOff implements Command {
    private Bulb bulb;

    public TurnOff(Bulb bulb) {
        this.bulb = bulb;
    }

    @Override
    public void execute() {
        bulb.turnOff();
    }

    @Override
    public void undo() {
        bulb.turnOn();
    }
}

// Invoker
class RemoteControl {
    public void submit(Command command) {
        command.execute();
    }
}

// ----------------------------

Bulb bulb = new Bulb();
TurnOn turnOnCmd = new TurnOn(bulb);
TurnOff turnOffCmd = new TurnOff(bulb);

RemoteControl remote = new RemoteControl();
remote.submit(turnOnCmd);  // Bulb has been lit
remote.submit(turnOffCmd); // Darkness!
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

// Receiver
class Bulb {
public:
    void turnOn() {
        std::cout << "Bulb has been lit" << std::endl;
    }

    void turnOff() {
        std::cout << "Darkness!" << std::endl;
    }
};

// Command interface
class Command {
public:
    virtual ~Command() = default;
    virtual void execute() = 0;
    virtual void undo() = 0;
};

class TurnOn : public Command {
private:
    Bulb& bulb;

public:
    TurnOn(Bulb& b) : bulb(b) {}

    void execute() override {
        bulb.turnOn();
    }

    void undo() override {
        bulb.turnOff();
    }
};

class TurnOff : public Command {
private:
    Bulb& bulb;

public:
    TurnOff(Bulb& b) : bulb(b) {}

    void execute() override {
        bulb.turnOff();
    }

    void undo() override {
        bulb.turnOn();
    }
};

// Invoker
class RemoteControl {
public:
    void submit(Command& command) {
        command.execute();
    }
};

// ----------------------------

int main() {
    Bulb bulb;

    TurnOn turnOn(bulb);
    TurnOff turnOff(bulb);

    RemoteControl remote;
    remote.submit(turnOn);  // Bulb has been lit
    remote.submit(turnOff); // Darkness!
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
// Receiver
class Bulb {
    fun turnOn() = println("Bulb has been lit")
    fun turnOff() = println("Darkness!")
}

interface Command {
    fun execute()
    fun undo()
}

// Command
class TurnOn(private val bulb: Bulb) : Command {
    override fun execute() = bulb.turnOn()
    override fun undo() = bulb.turnOff()
}

class TurnOff(private val bulb: Bulb) : Command {
    override fun execute() = bulb.turnOff()
    override fun undo() = bulb.turnOn()
}

// Invoker
class RemoteControl {
    fun submit(command: Command) {
        command.execute()
    }
}

// ----------------------------

fun main() {
    val bulb = Bulb()

    val turnOn = TurnOn(bulb)
    val turnOff = TurnOff(bulb)

    val remote = RemoteControl()
    remote.submit(turnOn)   // Bulb has been lit
    remote.submit(turnOff)  // Darkness!
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
// Receiver
class Bulb {
  void turnOn() => print('Bulb has been lit');
  void turnOff() => print('Darkness!');
}

abstract class Command {
  void execute();
  void undo();
}

// Command
class TurnOn implements Command {
  final Bulb _bulb;
  TurnOn(this._bulb);

  @override
  void execute() => _bulb.turnOn();

  @override
  void undo() => _bulb.turnOff();
}

class TurnOff implements Command {
  final Bulb _bulb;
  TurnOff(this._bulb);

  @override
  void execute() => _bulb.turnOff();

  @override
  void undo() => _bulb.turnOn();
}

// Invoker
class RemoteControl {
  void submit(Command command) {
    command.execute();
  }
}

// ----------------------------

void main() {
  var bulb = Bulb();

  var turnOn = TurnOn(bulb);
  var turnOff = TurnOff(bulb);

  var remote = RemoteControl();
  remote.submit(turnOn); // Bulb has been lit
  remote.submit(turnOff); // Darkness!
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی می‌خوای درخواست‌ها رو به آبجکت تبدیل کنی تا بشه صف‌شون کرد، لاگ گرفت یا undo/redo اضافه کرد؛ ❌ وقتی فقط یه متد ساده رو صدا می‌زنی و قرار نیست درخواست رو نگه داری یا برگردونی.
> 🪤 **دام رایج:** برای هر کار کوچیکی یه کلاس Command جدا می‌سازی و کد بی‌دلیل پر از کلاس‌های یه‌خطی می‌شه.


<br>

---

<div align="center">

## پیمایش‌گر (Iterator) ➿

</div>

<div align="center">
📻 <b>مثال دنیای واقعی: رادیو (دکمه بعدی/قبلی)</b>
</div>

تو وقتی رادیو گوش می‌دی، فقط دکمه «بعدی» یا «قبلی» رو می‌زنی و فرکانس عوض می‌شه.
برای تو مهم نیست رادیو فرکانس‌ها رو کجا و چطوری ذخیره کرده (لیست؟ جدول؟ چی؟).
فقط می‌خوای یکی یکی بین گزینه‌ها حرکت کنی. همین! 😄

💡 **به زبون ساده:**
> این پترن می‌گه: **«روی یک مجموعه قدم بزن، بدون اینکه ساختار داخلی اون مجموعه رو لو بدی.»**

ویکی‌پدیا:

<div dir="ltr">

> In object-oriented programming, the iterator pattern is a design pattern in which an iterator is used to traverse a
> container and access the container's elements. The iterator pattern decouples algorithms from containers; in some
> cases,
> algorithms are necessarily container-specific and thus cannot be decoupled.

</div>

خلاصه‌اش این می‌شه: پیمایش‌گر (Iterator) یه ابزاره که باهاش روی عناصر یک مجموعه (Container) قدم می‌زنی و بهشون دسترسی پیدا می‌کنی. این الگو، منطق پیمایش رو از خود مجموعه جدا می‌کنه؛ هرچند گاهی پیمایش اون‌قدر به ساختار مجموعه چسبیده که نمی‌شه کاملاً جداش کرد.

**مثال برنامه‌نویسی**

اینجا یه لیست از ایستگاه‌های رادیو (RadioStation) داریم که هر کدوم یه فرکانس دارن. لیست رو طوری می‌سازیم که قابل پیمایش باشه؛ بعد یکی‌یکی روی ایستگاه‌ها قدم می‌زنیم و فرکانس هر کدوم رو چاپ می‌کنیم.

توی این کد می‌تونی ببینی که چطور بدون اینکه بدونی ایستگاه‌ها داخل چی ذخیره شدن، فقط با یه حلقه ساده روشون حرکت می‌کنی.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
from __future__ import annotations
from collections.abc import Iterable, Iterator
from typing import List


class RadioStation:
    def __init__(self, frequency: float) -> None:
        self._frequency = frequency

    def get_frequency(self) -> float:
        return self._frequency


class StationIterator(Iterator):
    def __init__(self, stations: List[RadioStation]) -> None:
        self._stations = stations
        self._position = 0

    def __next__(self) -> RadioStation:
        if self._position >= len(self._stations):
            raise StopIteration()
        station = self._stations[self._position]
        self._position += 1
        return station


class RadioStationList(Iterable):
    def __init__(self) -> None:
        self._stations: List[RadioStation] = []

    def add(self, station: RadioStation) -> None:
        self._stations.append(station)

    def __iter__(self) -> StationIterator:
        return StationIterator(self._stations)

# ----------------------------

if __name__ == "__main__":
    stations = RadioStationList()
    stations.add(RadioStation(89.0))
    stations.add(RadioStation(101.0))
    stations.add(RadioStation(102.5))

    for station in stations:
        print(f"{station.get_frequency():.1f}")

'''
Output:
89.0
101.0
102.5
'''
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class RadioStation {
    constructor(private frequency: number) {}

    getFrequency(): number {
        return this.frequency;
    }
}

class StationIterator implements Iterator<RadioStation> {
    private position = 0;

    constructor(private stations: RadioStation[]) {}

    next(): IteratorResult<RadioStation> {
        if (this.position < this.stations.length) {
            const value = this.stations[this.position];
            this.position += 1;
            return { value, done: false };
        }
        return { value: undefined as any, done: true };
    }
}

class RadioStationList {
    private stations: RadioStation[] = [];

    add(station: RadioStation): void {
        this.stations.push(station);
    }

    [Symbol.iterator](): Iterator<RadioStation> {
        return new StationIterator(this.stations);
    }
}

// ----------------------------

const stations = new RadioStationList();
stations.add(new RadioStation(89.0));
stations.add(new RadioStation(101.0));
stations.add(new RadioStation(102.5));

for (const station of stations) {
    console.log(station.getFrequency().toFixed(1));
}

// Output:
// 89.0
// 101.0
// 102.5
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class RadioStation {
    constructor(frequency) {
        this.frequency = frequency;
    }

    getFrequency() {
        return this.frequency;
    }
}

class StationIterator {
    constructor(stations) {
        this.stations = stations;
        this.position = 0;
    }

    next() {
        if (this.position < this.stations.length) {
            const value = this.stations[this.position];
            this.position += 1;
            return { value, done: false };
        }
        return { value: undefined, done: true };
    }
}

class RadioStationList {
    constructor() {
        this.stations = [];
    }

    add(station) {
        this.stations.push(station);
    }

    [Symbol.iterator]() {
        return new StationIterator(this.stations);
    }
}

// ----------------------------

const stations = new RadioStationList();
stations.add(new RadioStation(89.0));
stations.add(new RadioStation(101.0));
stations.add(new RadioStation(102.5));

for (const station of stations) {
    console.log(station.getFrequency().toFixed(1));
}

// Output:
// 89.0
// 101.0
// 102.5
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;
using System.Collections.Generic;
using System.Collections;
using System.Globalization;

class RadioStation
{
    private float mFrequency;

    public RadioStation(float frequency)
    {
        mFrequency = frequency;
    }

    public float GetFrequency()
    {
        return mFrequency;
    }
}

class StationList : IEnumerable<RadioStation>
{
    private List<RadioStation> mStations = new List<RadioStation>();

    public void Add(RadioStation station)
    {
        mStations.Add(station);
    }

    public IEnumerator<RadioStation> GetEnumerator()
    {
        foreach (var station in mStations)
        {
            yield return station;
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }
}

// ----------------------------

var stations = new StationList();
stations.Add(new RadioStation(89.0f));
stations.Add(new RadioStation(101.0f));
stations.Add(new RadioStation(102.5f));

foreach (var station in stations)
{
    Console.WriteLine(station.GetFrequency().ToString("F1", CultureInfo.InvariantCulture));
}

// Output:
// 89.0
// 101.0
// 102.5
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
class RadioStation
{
    private $mFrequency;

    public function __construct($frequency)
    {
        $this->mFrequency = $frequency;
    }

    public function getFrequency()
    {
        return $this->mFrequency;
    }
}

class StationList implements IteratorAggregate
{
    private $mStations = [];

    public function add(RadioStation $station)
    {
        array_push($this->mStations, $station);
    }

    public function getIterator(): Iterator
    {
        foreach ($this->mStations as $station) {
            yield $station;
        }
    }
}

$stations = new StationList();
$stations->add(new RadioStation(89.0));
$stations->add(new RadioStation(101.0));
$stations->add(new RadioStation(102.5));

foreach ($stations as $station) {
    echo number_format($station->getFrequency(), 1) . "\n";
}

// Output:
// 89.0
// 101.0
// 102.5
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import (
    "fmt"
)

type RadioStation struct {
    frequency float32
}

func NewRadioStation(frequency float32) *RadioStation {
    return &RadioStation{frequency}
}

func (r *RadioStation) GetFrequency() float32 {
    return r.frequency
}

type StationList struct {
    stations []*RadioStation
}

func NewStationList() *StationList {
    return &StationList{}
}

func (s *StationList) Add(station *RadioStation) {
    s.stations = append(s.stations, station)
}

func (s *StationList) Iterator() <-chan *RadioStation {
    ch := make(chan *RadioStation)
    go func() {
        for _, station := range s.stations {
            ch <- station
        }
        close(ch)
    }()
    return ch
}

func main() {
    stations := NewStationList()
    stations.Add(NewRadioStation(89.0))
    stations.Add(NewRadioStation(101.0))
    stations.Add(NewRadioStation(102.5))

    for station := range stations.Iterator() {
        fmt.Printf("%.1f\n", station.GetFrequency())
    }
}

// Output:
// 89.0
// 101.0
// 102.5
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
import java.util.*;

class RadioStation {
    private float frequency;

    public RadioStation(float frequency) {
        this.frequency = frequency;
    }

    public float getFrequency() {
        return frequency;
    }
}

class StationList implements Iterable<RadioStation> {
    private List<RadioStation> stations;

    public StationList() {
        stations = new ArrayList<>();
    }

    public void add(RadioStation station) {
        stations.add(station);
    }

    @Override
    public Iterator<RadioStation> iterator() {
        return stations.iterator();
    }
}

// ----------------------------

StationList stations = new StationList();
stations.add(new RadioStation(89.0f));
stations.add(new RadioStation(101.0f));
stations.add(new RadioStation(102.5f));

Iterator<RadioStation> stationIterator = stations.iterator();
while (stationIterator.hasNext()) {
    RadioStation radioStation = stationIterator.next();
    System.out.println(radioStation.getFrequency());
}
// Output:
// 89.0
// 101.0
// 102.5
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <vector>
#include <iomanip>

class RadioStation {
private:
    float frequency;

public:
    RadioStation(float freq) : frequency(freq) {}

    float getFrequency() const {
        return frequency;
    }
};

class StationList {
private:
    std::vector<RadioStation> stations;

public:
    void add(const RadioStation& station) {
        stations.push_back(station);
    }

    std::vector<RadioStation>::iterator begin() {
        return stations.begin();
    }

    std::vector<RadioStation>::iterator end() {
        return stations.end();
    }
};

// ----------------------------

int main() {
    StationList stations;
    stations.add(RadioStation(89.0f));
    stations.add(RadioStation(101.0f));
    stations.add(RadioStation(102.5f));

    for (auto& station : stations) {
        std::cout << std::fixed << std::setprecision(1)
                  << station.getFrequency() << std::endl;
    }
    // Output:
    // 89.0
    // 101.0
    // 102.5
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
class RadioStation(private val frequency: Float) {
    fun getFrequency(): Float = frequency
}

class StationList : Iterable<RadioStation> {
    private val stations = mutableListOf<RadioStation>()

    fun add(station: RadioStation) {
        stations.add(station)
    }

    override fun iterator(): Iterator<RadioStation> = stations.iterator()
}

// ----------------------------

fun main() {
    val stations = StationList()
    stations.add(RadioStation(89.0f))
    stations.add(RadioStation(101.0f))
    stations.add(RadioStation(102.5f))

    for (station in stations) {
        println(station.getFrequency())
    }
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
import 'dart:collection';

class RadioStation {
  final double _frequency;

  RadioStation(this._frequency);

  double getFrequency() => _frequency;
}

class StationIterator implements Iterator<RadioStation> {
  final List<RadioStation> _stations;
  int _position = -1;

  StationIterator(this._stations);

  @override
  RadioStation get current => _stations[_position];

  @override
  bool moveNext() {
    _position++;
    return _position < _stations.length;
  }
}

class StationList extends IterableBase<RadioStation> {
  final List<RadioStation> _stations = [];

  void add(RadioStation station) {
    _stations.add(station);
  }

  @override
  Iterator<RadioStation> get iterator => StationIterator(_stations);
}

// ----------------------------

void main() {
  var stations = StationList();
  stations.add(RadioStation(89.0));
  stations.add(RadioStation(101.0));
  stations.add(RadioStation(102.5));

  for (var station in stations) {
    print(station.getFrequency().toStringAsFixed(1));
  }
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی می‌خوای روی یه مجموعه قدم بزنی بدون اینکه ساختار داخلیش (آرایه، درخت، گراف) رو لو بدی»؛ ❌ «وقتی یه آرایه ساده داری و حلقه معمولی زبان خودت کافیه، لازم نیست براش کلاس Iterator بسازی».
> 🪤 **دام رایج:** «وسط پیمایش، خود مجموعه رو تغییر بدی (عنصر اضافه یا حذف کنی) و پیمایش‌گر قاطی کنه».
> 🔗 **فرقش با حلقه‌ی ساده:** پیمایش‌گر منطقِ گشتن رو از خود مجموعه جدا می‌کنه، پس می‌تونی ساختار داخلی رو عوض کنی بدون اینکه کدِ پیمایش بشکنه.


<br>

---

<div align="center">

## میانجی (Mediator) 👽

</div>

<div align="center">
💬 <b>مثال دنیای واقعی: چت‌روم</b>
</div>

فرض کن توی یه گروه/چت‌روم هستی.
وقتی «جان» پیام می‌ده، لازم نیست مستقیم بره با تک‌تک آدم‌ها ارتباط برقرار کنه. پیام رو می‌ده به خودِ چت‌روم، و چت‌روم تصمیم می‌گیره چطوری پیام رو نشون بده.

اینطوری کاربرها (colleagueها) فقط «چت‌روم» رو می‌شناسن، نه همدیگه رو. نتیجه؟ وابستگی‌ها کمتر می‌شه و کد تمیزتر درمیاد. 🧩

💡 **به زبون ساده:**
> این پترن می‌گه: **«ارتباط بین چند آبجکت رو بده به یک مرکز (Mediator)، تا خودشون مستقیم به هم نچسبن.»**

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, the mediator pattern defines an object that encapsulates how a set of objects interact. This
> pattern is considered to be a behavioral pattern due to the way it can alter the program's running behavior.

</div>

خلاصه‌ش این می‌شه که الگوی میانجی (Mediator) یه آبجکت تعریف می‌کنه که چم‌وخمِ گفت‌وگوی یه دسته آبجکت با همدیگه رو توی خودش جمع می‌کنه.
چون این الگو می‌تونه روی رفتار برنامه موقع اجرا اثر بذاره، یه الگوی رفتاری (Behavioral) حساب می‌شه.

**مثال برنامه‌نویسی**

می‌خوایم یه چت‌روم بسازیم! (Mediator)

حالا بریم سراغ خود کاربرها (Colleagues):

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class ChatRoomMediator:
    def show_message(self, user, message):
        raise NotImplementedError


class ChatRoom(ChatRoomMediator):
    def show_message(self, user, message):
        print(user.get_name() + ': ' + message)


class User:
    def __init__(self, name, chat_room):
        self._name = name
        self._chat_room = chat_room

    def get_name(self):
        return self._name

    def send(self, message):
        self._chat_room.show_message(self, message)


# ----------------------------

mediator = ChatRoom()

john = User('John', mediator)
jane = User('Jane', mediator)

john.send('Hi there!')
jane.send('Hey!')

# Output:
# John: Hi there!
# Jane: Hey!
```

</div>

</details>

<details>
<summary>TypeScript</summary>

<div dir="ltr">

```typescript
interface ChatRoomMediator {
    showMessage(user: User, message: string): void;
}

class ChatRoom implements ChatRoomMediator {
    showMessage(user: User, message: string): void {
        console.log(`${user.getName()}: ${message}`);
    }
}

class User {
    private name: string;
    private chatRoom: ChatRoomMediator;

    constructor(name: string, chatRoom: ChatRoomMediator) {
        this.name = name;
        this.chatRoom = chatRoom;
    }

    getName(): string {
        return this.name;
    }

    send(message: string): void {
        this.chatRoom.showMessage(this, message);
    }
}

// ----------------------------

const mediator = new ChatRoom();

const john = new User("John", mediator);
const jane = new User("Jane", mediator);

john.send("Hi there!");
jane.send("Hey!");

// Output:
// John: Hi there!
// Jane: Hey!
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class ChatRoomMediator {
    showMessage(user, message) {
    }
}

class ChatRoom extends ChatRoomMediator {
    showMessage(user, message) {
        console.log(`${user.getName()}: ${message}`);
    }
}

class User {
    constructor(name, chatRoom) {
        this.name = name;
        this.chatRoom = chatRoom;
    }

    getName() {
        return this.name;
    }

    send(message) {
        this.chatRoom.showMessage(this, message);
    }
}

const mediator = new ChatRoom();

const john = new User("John", mediator);
const jane = new User("Jane", mediator);

john.send("Hi there!");
jane.send("Hey!");

// Output:
// John: Hi there!
// Jane: Hey!
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface IChatRoomMediator
{
  void ShowMessage(User user, string message);
}

// Mediator
class ChatRoom : IChatRoomMediator
{
  public void ShowMessage(User user, string message)
  {
    Console.WriteLine($"{user.GetName()}: {message}");
  }
}


class User
{
  private string mName;
  private IChatRoomMediator mChatRoom;

  public User(string name, IChatRoomMediator chatRoom)
  {
    mChatRoom = chatRoom;
    mName = name;
  }

  public string GetName()
  {
    return mName;
  }

  public void Send(string message)
  {
    mChatRoom.ShowMessage(this, message);
  }
}

// ----------------------------

var mediator = new ChatRoom();

var john = new User("John", mediator);
var jane = new User("Jane", mediator);

john.Send("Hi there!");
jane.Send("Hey!");

// Output:
// John: Hi there!
// Jane: Hey!

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface ChatRoomMediator
{
    public function showMessage(User $user, string $message): void;
}

class ChatRoom implements ChatRoomMediator
{
    public function showMessage(User $user, string $message): void
    {
        echo $user->getName() . ": " . $message . "\n";
    }
}

class User
{
    private $name;
    private $chatRoom;

    public function __construct(string $name, ChatRoomMediator $chatRoom)
    {
        $this->name = $name;
        $this->chatRoom = $chatRoom;
    }

    public function getName(): string
    {
        return $this->name;
    }

    public function send(string $message): void
    {
        $this->chatRoom->showMessage($this, $message);
    }
}

$mediator = new ChatRoom();

$john = new User("John", $mediator);
$jane = new User("Jane", $mediator);

$john->send("Hi there!");
$jane->send("Hey!");

// Output:
// John: Hi there!
// Jane: Hey!

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type ChatRoomMediator interface {
	ShowMessage(user *User, message string)
}

type ChatRoom struct{}

func (cr *ChatRoom) ShowMessage(user *User, message string) {
	fmt.Printf("%s: %s\n", user.GetName(), message)
}

type User struct {
	Name     string
	ChatRoom ChatRoomMediator
}

func (u *User) GetName() string {
	return u.Name
}

func (u *User) Send(message string) {
	u.ChatRoom.ShowMessage(u, message)
}

func main() {
	mediator := &ChatRoom{}

	john := &User{Name: "John", ChatRoom: mediator}
	jane := &User{Name: "Jane", ChatRoom: mediator}

	john.Send("Hi there!")
	jane.Send("Hey!")

	// Output:
	// John: Hi there!
	// Jane: Hey!
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface ChatRoomMediator {
    void showMessage(User user, String message);
}

// Mediator
class ChatRoom implements ChatRoomMediator {

    @Override
    public void showMessage(User user, String message) {
        System.out.println(user.getName() + ": " + message);
    }
}

class User {
    private String name;
    private ChatRoomMediator chatRoom;

    public User(String name, ChatRoomMediator chatRoom) {
        this.chatRoom = chatRoom;
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void send(String message) {
        chatRoom.showMessage(this, message);
    }
}

// ----------------------------

ChatRoom mediator = new ChatRoom();

User john = new User("John", mediator);
User jane = new User("Jane", mediator);

john.send("Hi there!"); // John: Hi there!
jane.send("Hey!");      // Jane: Hey!
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>

class User;

class ChatRoomMediator {
public:
    virtual ~ChatRoomMediator() = default;
    virtual void showMessage(User* user, const std::string& message) = 0;
};

class User {
private:
    std::string name;
    ChatRoomMediator* chatRoom;

public:
    User(const std::string& name, ChatRoomMediator* chatRoom)
        : name(name), chatRoom(chatRoom) {}

    std::string getName() const {
        return name;
    }

    void send(const std::string& message) {
        chatRoom->showMessage(this, message);
    }
};

class ChatRoom : public ChatRoomMediator {
public:
    void showMessage(User* user, const std::string& message) override {
        std::cout << user->getName() << ": " << message << std::endl;
    }
};

// ----------------------------

int main() {
    ChatRoom mediator;

    User john("John", &mediator);
    User jane("Jane", &mediator);

    john.send("Hi there!");
    jane.send("Hey!");
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface ChatRoomMediator {
    fun showMessage(user: User, message: String)
}

class ChatRoom : ChatRoomMediator {
    override fun showMessage(user: User, message: String) {
        println("${user.getName()}: $message")
    }
}

class User(private val name: String, private val chatRoom: ChatRoomMediator) {
    fun getName(): String = name

    fun send(message: String) {
        chatRoom.showMessage(this, message)
    }
}

// ----------------------------

fun main() {
    val mediator = ChatRoom()

    val john = User("John", mediator)
    val jane = User("Jane", mediator)

    john.send("Hi there!")
    jane.send("Hey!")
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class ChatRoomMediator {
  void showMessage(User user, String message);
}

class ChatRoom implements ChatRoomMediator {
  @override
  void showMessage(User user, String message) {
    print('${user.getName()}: $message');
  }
}

class User {
  final String _name;
  final ChatRoomMediator _chatRoom;

  User(this._name, this._chatRoom);

  String getName() => _name;

  void send(String message) {
    _chatRoom.showMessage(this, message);
  }
}

// ----------------------------

void main() {
  var mediator = ChatRoom();

  var john = User('John', mediator);
  var jane = User('Jane', mediator);

  john.send('Hi there!');
  jane.send('Hey!');
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی چند آبجکت جوری تو هم گره خوردن که هرکی با همه بقیه مستقیم حرف می‌زنه و این تار عنکبوتِ وابستگی داره خفه‌ت می‌کنه»؛ ❌ «وقتی فقط دو سه آبجکت ساده داری که ارتباط مستقیمشون اصلاً پیچیده نیست».
> 🪤 **دام رایج:** «خودِ میانجی کم‌کم همه منطق رو می‌بلعه و تبدیل می‌شه به یه «گاد آبجکت (God Object)» که دیگه هیچ‌کس جرئت نمی‌کنه بهش دست بزنه».
> 🔗 **فرقش با [ناظر (Observer)](#ناظر-observer-):** «اونجا یه سوژه به چند ناظری که خودشون اشتراک گرفتن خبر می‌ده؛ اینجا یه مرکز رفت‌وآمدِ دوطرفه پیام‌ها رو بین آبجکت‌ها میزون می‌کنه».


<br>

---

<div align="center">

## نقطه‌ی بازگشت (Memento) 💾

</div>

<div align="center">
↩️ <b>مثال دنیای واقعی: دکمه Undo</b>
</div>

فرض کن داری توی یک ادیتور متن تایپ می‌کنی.
یه دفعه یه چیزی خراب می‌شه و می‌گی: «ای بابا! برگردون به ۲ دقیقه قبل.»

ادیتور برای اینکه بتونه این کار رو بکنه، هر از گاهی از وضعیت خودش یه «عکس» (Snapshot) برمی‌داره و نگه می‌داره.
وقتی تو `Undo` می‌زنی، یکی از همون عکس‌ها رو برمی‌گردونه و همه‌چی برمی‌گرده به حالت قبل. 🧠

💡 **به زبون ساده:**
> این پترن می‌گه: **«از حالتِ فعلی یه snapshot بگیر، نگهش دار، هر وقت لازم شد restore کن.»**

ویکی‌پدیا:

<div dir="ltr">

> The memento pattern is a software design pattern that provides the ability to restore an object to its previous
> state (undo via rollback).

</div>

یعنی این الگو کاری می‌کنه که یه شیء بتونه یه snapshot از حالتش بگیره و بعداً بهش برگرده، بدون اینکه دل‌وروده‌اش لو بره؛ همون کاری که موقع undo می‌کنیم.

**مثال برنامه‌نویسی**

می‌خوایم یک ادیتور متن بسازیم و قابلیت ذخیره کردن و بازگردانی بهش اضافه کنیم!

اول یه کلاس می‌سازیم که نقش حافظه ادیتور رو بازی می‌کنه؛ کارش فقط نگه‌داشتن یه مقداره.

بعد خودِ ادیتور رو می‌سازیم که می‌تونه تایپ کنه، سیو کنه و به حالت قبل برگرده.

یک نقش سوم هم داریم به اسم نگهبان (Caretaker)؛ این همون چیزیه که snapshotها رو نگه می‌داره و ترتیبشون رو حفظ می‌کنه، ولی هیچ‌وقت داخلشون رو دست نمی‌زنه. برای همینه که حالت داخلی ادیتور همچنان پیش خودش می‌مونه. ما اینجا نگهبان رو به شکل یک کلاس `History` می‌سازیم که یه stack از mementoها رو نگه می‌داره.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
# Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor:
    def __init__(self):
        self._content = ""

    def type(self, content):
        self._content = content

    def get_content(self):
        return self._content

    def save(self):
        return EditorMemento(self._content)

    def restore(self, memento):
        self._content = memento.get_content()


# Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento:
    def __init__(self, content):
        self._content = content

    def get_content(self):
        return self._content


# Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History:
    def __init__(self):
        self._mementos = []

    def push(self, memento):
        self._mementos.append(memento)

    def pop(self):
        return self._mementos.pop()


# ----------------------------

editor = Editor()
history = History()

editor.type("a")
history.push(editor.save())

editor.type("ab")
history.push(editor.save())

editor.type("abc")

editor.restore(history.pop())
print(editor.get_content())  # ab

editor.restore(history.pop())
print(editor.get_content())  # a
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento {
    private content: string;

    constructor(content: string) {
        this.content = content;
    }

    getContent(): string {
        return this.content;
    }
}

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor {
    private content = "";

    type(content: string): void {
        this.content = content;
    }

    getContent(): string {
        return this.content;
    }

    save(): EditorMemento {
        return new EditorMemento(this.content);
    }

    restore(memento: EditorMemento): void {
        this.content = memento.getContent();
    }
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History {
    private mementos: EditorMemento[] = [];

    push(memento: EditorMemento): void {
        this.mementos.push(memento);
    }

    pop(): EditorMemento {
        return this.mementos.pop()!;
    }
}

// ----------------------------

const editor = new Editor();
const history = new History();

editor.type("a");
history.push(editor.save());

editor.type("ab");
history.push(editor.save());

editor.type("abc");

editor.restore(history.pop());
console.log(editor.getContent()); // ab

editor.restore(history.pop());
console.log(editor.getContent()); // a
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento {
    constructor(content) {
        this.content = content;
    }

    getContent() {
        return this.content;
    }
}

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor {
    constructor() {
        this.content = "";
    }

    type(content) {
        this.content = content;
    }

    getContent() {
        return this.content;
    }

    save() {
        return new EditorMemento(this.content);
    }

    restore(memento) {
        this.content = memento.getContent();
    }
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History {
    constructor() {
        this.mementos = [];
    }

    push(memento) {
        this.mementos.push(memento);
    }

    pop() {
        return this.mementos.pop();
    }
}

// ----------------------------

const editor = new Editor();
const history = new History();

editor.type("a");
history.push(editor.save());

editor.type("ab");
history.push(editor.save());

editor.type("abc");

editor.restore(history.pop());
console.log(editor.getContent()); // ab

editor.restore(history.pop());
console.log(editor.getContent()); // a
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;
using System.Collections.Generic;

// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento
{
    private readonly string mContent;

    public EditorMemento(string content)
    {
        mContent = content;
    }

    public string Content
    {
        get { return mContent; }
    }
}

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor
{
    private string mContent = string.Empty;

    public void Type(string words)
    {
        mContent = words;
    }

    public string Content
    {
        get { return mContent; }
    }

    public EditorMemento Save()
    {
        return new EditorMemento(mContent);
    }

    public void Restore(EditorMemento memento)
    {
        mContent = memento.Content;
    }
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History
{
    private readonly Stack<EditorMemento> mementos = new Stack<EditorMemento>();

    public void Push(EditorMemento memento)
    {
        mementos.Push(memento);
    }

    public EditorMemento Pop()
    {
        return mementos.Pop();
    }
}

// ----------------------------

var editor = new Editor();
var history = new History();

editor.Type("a");
history.Push(editor.Save());

editor.Type("ab");
history.Push(editor.Save());

editor.Type("abc");

editor.Restore(history.Pop());
Console.WriteLine(editor.Content); // ab

editor.Restore(history.Pop());
Console.WriteLine(editor.Content); // a
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento
{
    private $content;

    public function __construct($content)
    {
        $this->content = $content;
    }

    public function getContent()
    {
        return $this->content;
    }
}

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor
{
    private $content = '';

    public function type($words)
    {
        $this->content = $words;
    }

    public function getContent()
    {
        return $this->content;
    }

    public function save()
    {
        return new EditorMemento($this->content);
    }

    public function restore($memento)
    {
        $this->content = $memento->getContent();
    }
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History
{
    private $mementos = [];

    public function push($memento)
    {
        $this->mementos[] = $memento;
    }

    public function pop()
    {
        return array_pop($this->mementos);
    }
}

// ----------------------------

$editor = new Editor();
$history = new History();

$editor->type("a");
$history->push($editor->save());

$editor->type("ab");
$history->push($editor->save());

$editor->type("abc");

$editor->restore($history->pop());
echo $editor->getContent() . "\n"; // ab

$editor->restore($history->pop());
echo $editor->getContent() . "\n"; // a
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
import java.util.Deque;
import java.util.ArrayDeque;

// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento {
    private final String content;

    public EditorMemento(String content) {
        this.content = content;
    }

    public String getContent() {
        return this.content;
    }
}

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor {
    private String content = "";

    public void type(String words) {
        this.content = words;
    }

    public String getContent() {
        return this.content;
    }

    public EditorMemento save() {
        return new EditorMemento(this.content);
    }

    public void restore(EditorMemento memento) {
        this.content = memento.getContent();
    }
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History {
    private final Deque<EditorMemento> mementos = new ArrayDeque<>();

    public void push(EditorMemento memento) {
        mementos.push(memento);
    }

    public EditorMemento pop() {
        return mementos.pop();
    }
}

public class Main {
    public static void main(String[] args) {
        Editor editor = new Editor();
        History history = new History();

        editor.type("a");
        history.push(editor.save());

        editor.type("ab");
        history.push(editor.save());

        editor.type("abc");

        editor.restore(history.pop());
        System.out.println(editor.getContent()); // ab

        editor.restore(history.pop());
        System.out.println(editor.getContent()); // a
    }
}
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
type EditorMemento struct {
	content string
}

func NewEditorMemento(content string) *EditorMemento {
	return &EditorMemento{content: content}
}

func (m *EditorMemento) GetContent() string {
	return m.content
}

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
type Editor struct {
	content string
}

func (e *Editor) Type(content string) {
	e.content = content
}

func (e *Editor) GetContent() string {
	return e.content
}

func (e *Editor) Save() *EditorMemento {
	return NewEditorMemento(e.content)
}

func (e *Editor) Restore(memento *EditorMemento) {
	e.content = memento.GetContent()
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
type History struct {
	mementos []*EditorMemento
}

func (h *History) Push(memento *EditorMemento) {
	h.mementos = append(h.mementos, memento)
}

func (h *History) Pop() *EditorMemento {
	last := len(h.mementos) - 1
	memento := h.mementos[last]
	h.mementos = h.mementos[:last]
	return memento
}

// ----------------------------

func main() {
	editor := &Editor{}
	history := &History{}

	editor.Type("a")
	history.Push(editor.Save())

	editor.Type("ab")
	history.Push(editor.Save())

	editor.Type("abc")

	editor.Restore(history.Pop())
	fmt.Println(editor.GetContent()) // ab

	editor.Restore(history.Pop())
	fmt.Println(editor.GetContent()) // a
}
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <vector>

// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento {
private:
    std::string content;

public:
    EditorMemento(const std::string& c) : content(c) {}

    std::string getContent() const {
        return content;
    }
};

// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor {
private:
    std::string content;

public:
    void type(const std::string& words) {
        content = words;
    }

    std::string getContent() const {
        return content;
    }

    EditorMemento save() const {
        return EditorMemento(content);
    }

    void restore(const EditorMemento& memento) {
        content = memento.getContent();
    }
};

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History {
private:
    std::vector<EditorMemento> mementos;

public:
    void push(const EditorMemento& memento) {
        mementos.push_back(memento);
    }

    EditorMemento pop() {
        EditorMemento memento = mementos.back();
        mementos.pop_back();
        return memento;
    }
};

// ----------------------------

int main() {
    Editor editor;
    History history;

    editor.type("a");
    history.push(editor.save());

    editor.type("ab");
    history.push(editor.save());

    editor.type("abc");

    editor.restore(history.pop());
    std::cout << editor.getContent() << std::endl; // ab

    editor.restore(history.pop());
    std::cout << editor.getContent() << std::endl; // a
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor {
    private var content: String = ""

    fun type(content: String) {
        this.content = content
    }

    fun getContent(): String = content

    fun save(): EditorMemento = EditorMemento(content)

    fun restore(memento: EditorMemento) {
        content = memento.getContent()
    }
}

// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento(private val content: String) {
    fun getContent(): String = content
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History {
    private val mementos = ArrayDeque<EditorMemento>()

    fun push(memento: EditorMemento) {
        mementos.addLast(memento)
    }

    fun pop(): EditorMemento = mementos.removeLast()
}

// ----------------------------

fun main() {
    val editor = Editor()
    val history = History()

    editor.type("a")
    history.push(editor.save())

    editor.type("ab")
    history.push(editor.save())

    editor.type("abc")

    editor.restore(history.pop())
    println(editor.getContent())

    editor.restore(history.pop())
    println(editor.getContent())
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
// Originator: حالت رو نگه می‌داره و memento می‌سازه/برمی‌گردونه.
class Editor {
  String _content = '';

  void type(String content) {
    _content = content;
  }

  String getContent() => _content;

  EditorMemento save() => EditorMemento(_content);

  void restore(EditorMemento memento) {
    _content = memento.getContent();
  }
}

// Memento: یک snapshot غیرقابل‌تغییر از حالت ادیتور.
class EditorMemento {
  final String _content;

  EditorMemento(this._content);

  String getContent() => _content;
}

// Caretaker: memento ها رو توی یک stack نگه می‌داره، بدون اینکه داخلشون رو ببینه.
class History {
  final List<EditorMemento> _mementos = [];

  void push(EditorMemento memento) {
    _mementos.add(memento);
  }

  EditorMemento pop() => _mementos.removeLast();
}

// ----------------------------

void main() {
  var editor = Editor();
  var history = History();

  editor.type('a');
  history.push(editor.save());

  editor.type('ab');
  history.push(editor.save());

  editor.type('abc');

  editor.restore(history.pop());
  print(editor.getContent());

  editor.restore(history.pop());
  print(editor.getContent());
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی می‌خوای حالت یک شیء رو ذخیره کنی و بعداً بهش برگردی، بدون اینکه کپسوله‌بودنش رو بشکنی»؛ ❌ «وقتی حالت سنگینه یا snapshot ها زیاد می‌شن و حافظه‌ت رو می‌خورن».
> 🪤 **دام رایج:** «نگه‌داشتن بی‌حساب‌وکتاب همه‌ی snapshot ها؛ یک سقف یا سیاست پاک‌سازی براش بذار».



<br>

---

<div align="center">

## ناظر (Observer) 😎

</div>

<div align="center">
📬 <b>مثال دنیای واقعی: اعلان‌های سایت کاریابی</b>
</div>

فرض کن توی یه سایت کاریابی ثبت‌نام کردی و می‌گی: «هر وقت یه شغل جدید اومد، به من خبر بده.»
حالا از اون طرف، سایت هر بار که یه آگهی جدید اضافه می‌شه، به همه‌ی کسایی که عضو شدن ایمیل/نوتیف می‌فرسته.

یعنی تو لازم نیست هر روز بری سایت رو چک کنی. خودِ سیستم با هر تغییر، خبرت می‌کنه. 🔔

💡 **به زبون ساده:**
> این پترن می‌گه: **«یک نفر تغییر می‌کنه (Subject) و بقیه‌ای که دنبالشن (Observerها) خودکار باخبر می‌شن.»**

ویکی‌پدیا:

<div dir="ltr">

> The observer pattern is a software design pattern in which an object, called the subject, maintains a list of its
> dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their
> methods.

</div>

به زبون خودمون: یه شیء به اسم «سوژه (Subject)» یه فهرست از وابسته‌هاش رو نگه می‌داره که بهشون می‌گیم «ناظر (Observer)».
هر وقت وضعیتِ سوژه عوض می‌شه، خودش یکی‌یکی به همه ناظرها خبر می‌ده؛ معمولاً با صدا زدن یکی از متدهاشون.

**مثال برنامه‌نویسی**

اول یه کلاس می‌سازیم برای نگه‌داشتن یه شغل، بعد یه کلاس برای جوینده‌های کار.

و بعد یک کلاس می‌سازیم که آگهی‌ها رو نگه می‌داره و جوینده‌ها می‌تونن توش عضو بشن. هر وقت شغل جدیدی ثبت بشه، خودکار به همه‌ی عضوها خبر می‌ده.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class JobPost:
    def __init__(self, title):
        self.title = title

    def getTitle(self):
        return self.title


class JobSeeker:
    def __init__(self, name):
        self.name = name

    def onJobPosted(self, job):
        print('Hi ' + self.name + '! New job posted: ' + job.getTitle())


class EmploymentAgency:
    def __init__(self):
        self.observers = []

    def notify(self, jobPosting):
        for observer in self.observers:
            observer.onJobPosted(jobPosting)

    def attach(self, observer):
        self.observers.append(observer)

    def addJob(self, jobPosting):
        self.notify(jobPosting)


# ----------------------------

johnDoe = JobSeeker('John Doe')
janeDoe = JobSeeker('Jane Doe')

jobPostings = EmploymentAgency()
jobPostings.attach(johnDoe)
jobPostings.attach(janeDoe)

jobPostings.addJob(JobPost('Software Engineer'))

# Output
# Hi John Doe! New job posted: Software Engineer
# Hi Jane Doe! New job posted: Software Engineer

```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class JobPost {
    private title: string;

    constructor(title: string) {
        this.title = title;
    }

    getTitle(): string {
        return this.title;
    }
}

class JobSeeker {
    private name: string;

    constructor(name: string) {
        this.name = name;
    }

    onJobPosted(job: JobPost): void {
        console.log(`Hi ${this.name}! New job posted: ${job.getTitle()}`);
    }
}

class EmploymentAgency {
    private observers: JobSeeker[] = [];

    notify(jobPosting: JobPost): void {
        for (const observer of this.observers) {
            observer.onJobPosted(jobPosting);
        }
    }

    attach(observer: JobSeeker): void {
        this.observers.push(observer);
    }

    addJob(jobPosting: JobPost): void {
        this.notify(jobPosting);
    }
}

// ----------------------------

const johnDoe = new JobSeeker("John Doe");
const janeDoe = new JobSeeker("Jane Doe");

const jobPostings = new EmploymentAgency();
jobPostings.attach(johnDoe);
jobPostings.attach(janeDoe);

jobPostings.addJob(new JobPost("Software Engineer"));

// Output
// Hi John Doe! New job posted: Software Engineer
// Hi Jane Doe! New job posted: Software Engineer
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class JobPost {
    constructor(title) {
        this.title = title;
    }

    getTitle() {
        return this.title;
    }
}

class JobSeeker {
    constructor(name) {
        this.name = name;
    }

    onJobPosted(job) {
        console.log(`Hi ${this.name}! New job posted: ${job.getTitle()}`);
    }
}

class EmploymentAgency {
    constructor() {
        this.observers = [];
    }

    notify(jobPosting) {
        for (const observer of this.observers) {
            observer.onJobPosted(jobPosting);
        }
    }

    attach(observer) {
        this.observers.push(observer);
    }

    addJob(jobPosting) {
        this.notify(jobPosting);
    }
}


const johnDoe = new JobSeeker("John Doe");
const janeDoe = new JobSeeker("Jane Doe");

const jobPostings = new EmploymentAgency();
jobPostings.attach(johnDoe);
jobPostings.attach(janeDoe);

jobPostings.addJob(new JobPost("Software Engineer"));

// Output
// Hi John Doe! New job posted: Software Engineer
// Hi Jane Doe! New job posted: Software Engineer
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;
using System.Collections.Generic;


class JobPost
{
  public string Title { get; private set; }

  public JobPost(string title)
  {
    Title = title;
  }
}
class JobSeeker : IObserver<JobPost>
{
  public string Name { get; private set; }

  public JobSeeker(string name)
  {
    Name = name;
  }

  //Method is not being called by EmploymentAgency class currently
  public void OnCompleted()
  {
    //No Implementation
  }

  //Method is not being called by EmploymentAgency class currently
  public void OnError(Exception error)
  {
    //No Implementation
  }

  public void OnNext(JobPost value)
  {
    Console.WriteLine($"Hi {Name}! New job posted: {value.Title}");
  }
}


class EmploymentAgency : IObservable<JobPost>
{
  private List<IObserver<JobPost>> mObservers;
  private List<JobPost> mJobPostings;

  public EmploymentAgency()
  {
    mObservers = new List<IObserver<JobPost>>();
    mJobPostings = new List<JobPost>();
  }

  public IDisposable Subscribe(IObserver<JobPost> observer)
  {
    // Check whether observer is already registered. If not, add it
    if (!mObservers.Contains(observer))
    {
      mObservers.Add(observer);
    }
    return new Unsubscriber<JobPost>(mObservers, observer);
  }

  private void Notify(JobPost jobPost)
  {
    foreach(var observer in mObservers)
    {
      observer.OnNext(jobPost);
    }
  }

  public void AddJob(JobPost jobPost)
  {
    mJobPostings.Add(jobPost);
    Notify(jobPost);
  }

}

internal class Unsubscriber<JobPost> : IDisposable
{
  private List<IObserver<JobPost>> mObservers;
  private IObserver<JobPost> mObserver;

  internal Unsubscriber(List<IObserver<JobPost>> observers, IObserver<JobPost> observer)
  {
    this.mObservers = observers;
    this.mObserver = observer;
  }

  public void Dispose()
  {
    if (mObservers.Contains(mObserver))
      mObservers.Remove(mObserver);
  }
}

// ----------------------------

//Create Subscribers
var johnDoe = new JobSeeker("John Doe");
var janeDoe = new JobSeeker("Jane Doe");

//Create publisher and attach subscribers
var jobPostings = new EmploymentAgency();
jobPostings.Subscribe(johnDoe);
jobPostings.Subscribe(janeDoe);

//Add a new job and see if subscribers get notified
jobPostings.AddJob(new JobPost("Software Engineer"));

//Output
// Hi John Doe! New job posted: Software Engineer
// Hi Jane Doe! New job posted: Software Engineer

Console.ReadLine();

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface ObserverInterface
{
    public function onJobPosted(JobPost $job): void;
}

class JobPost
{
    public function __construct(private string $title)
    {
    }

    public function getTitle(): string
    {
        return $this->title;
    }
}

class JobSeeker implements ObserverInterface
{
    public function __construct(private string $name)
    {
    }

    public function onJobPosted(JobPost $job): void
    {
        echo "Hi {$this->name}! New job posted: {$job->getTitle()}
";
    }
}

class EmploymentAgency
{
    private array $observers = [];

    public function attach(ObserverInterface $observer): void
    {
        $this->observers[] = $observer;
    }

    public function notify(JobPost $jobPosting): void
    {
        foreach ($this->observers as $observer) {
            $observer->onJobPosted($jobPosting);
        }
    }

    public function addJob(JobPost $jobPosting): void
    {
        $this->notify($jobPosting);
    }
}

// ----------------------------

$johnDoe = new JobSeeker("John Doe");
$janeDoe = new JobSeeker("Jane Doe");

$jobPostings = new EmploymentAgency();
$jobPostings->attach($johnDoe);
$jobPostings->attach($janeDoe);

$jobPostings->addJob(new JobPost("Software Engineer"));

// Output:
// Hi John Doe! New job posted: Software Engineer
// Hi Jane Doe! New job posted: Software Engineer
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

type JobPost struct {
	title string
}

func NewJobPost(title string) *JobPost {
	return &JobPost{title: title}
}

func (jp *JobPost) GetTitle() string {
	return jp.title
}

type JobSeeker struct {
	name string
}

func NewJobSeeker(name string) *JobSeeker {
	return &JobSeeker{name: name}
}

func (js *JobSeeker) OnJobPosted(job *JobPost) {
	fmt.Printf("Hi %s! New job posted: %s\n", js.name, job.GetTitle())
}

type EmploymentAgency struct {
	observers []*JobSeeker
}

func NewEmploymentAgency() *EmploymentAgency {
	return &EmploymentAgency{}
}

func (ea *EmploymentAgency) Notify(jobPosting *JobPost) {
	for _, observer := range ea.observers {
		observer.OnJobPosted(jobPosting)
	}
}

func (ea *EmploymentAgency) Attach(observer *JobSeeker) {
	ea.observers = append(ea.observers, observer)
}

func (ea *EmploymentAgency) AddJob(jobPosting *JobPost) {
	ea.Notify(jobPosting)
}

func main() {
	johnDoe := NewJobSeeker("John Doe")
	janeDoe := NewJobSeeker("Jane Doe")

	jobPostings := NewEmploymentAgency()
	jobPostings.Attach(johnDoe)
	jobPostings.Attach(janeDoe)

	jobPostings.AddJob(NewJobPost("Software Engineer"))

	// Output
	// Hi John Doe! New job posted: Software Engineer
	// Hi Jane Doe! New job posted: Software Engineer
}


```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
import java.util.*;

class JobPost {
    private String title;

    public JobPost(String title) {
        this.title = title;
    }

    public String getTitle() {
        return this.title;
    }
}

class JobSeeker {
    private String name;

    public JobSeeker(String name) {
        this.name = name;
    }

    public void onJobPosted(JobPost job) {
        System.out.println("Hi " + this.name + "! New job posted: " + job.getTitle());
    }
}

class EmploymentAgency {
    private List<JobSeeker> observers = new ArrayList<>();

    public void notify(JobPost jobPosting) {
        for (JobSeeker observer : this.observers) {
            observer.onJobPosted(jobPosting);
        }
    }

    public void attach(JobSeeker observer) {
        this.observers.add(observer);
    }

    public void addJob(JobPost jobPosting) {
        this.notify(jobPosting);
    }
}

// ----------------------------

JobSeeker johnDoe = new JobSeeker("John Doe");
JobSeeker janeDoe = new JobSeeker("Jane Doe");

EmploymentAgency jobPostings = new EmploymentAgency();
jobPostings.attach(johnDoe);
jobPostings.attach(janeDoe);

jobPostings.addJob(new JobPost("Software Engineer"));
// Hi John Doe! New job posted: Software Engineer
// Hi Jane Doe! New job posted: Software Engineer
```

</div>
</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <memory>
#include <algorithm>

// Job post class
class JobPost {
private:
    std::string title;

public:
    JobPost(const std::string& title) : title(title) {}
    
    std::string getTitle() const {
        return title;
    }
};

// Observer interface
class JobSeeker {
private:
    std::string name;

public:
    JobSeeker(const std::string& name) : name(name) {}
    
    void onJobPosted(const JobPost& job) {
        std::cout << "Hi " << name << "! New job posted: " << job.getTitle() << std::endl;
    }
    
    std::string getName() const {
        return name;
    }
};

// Subject class
class EmploymentAgency {
private:
    std::vector<std::shared_ptr<JobSeeker>> observers;

public:
    void attach(std::shared_ptr<JobSeeker> observer) {
        observers.push_back(observer);
    }
    
    void detach(std::shared_ptr<JobSeeker> observer) {
        observers.erase(
            std::remove(observers.begin(), observers.end(), observer),
            observers.end()
        );
    }
    
    void notify(const JobPost& jobPosting) {
        for (auto& observer : observers) {
            observer->onJobPosted(jobPosting);
        }
    }
    
    void addJob(const JobPost& jobPosting) {
        notify(jobPosting);
    }
};

// Usage
int main() {
    auto johnDoe = std::make_shared<JobSeeker>("John Doe");
    auto janeDoe = std::make_shared<JobSeeker>("Jane Doe");
    
    EmploymentAgency jobPostings;
    jobPostings.attach(johnDoe);
    jobPostings.attach(janeDoe);
    
    jobPostings.addJob(JobPost("Software Engineer"));
    // Hi John Doe! New job posted: Software Engineer
    // Hi Jane Doe! New job posted: Software Engineer
    
    return 0;
}
```
</div>
</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
class JobPost(private val title: String) {
    fun getTitle(): String = title
}

class JobSeeker(private val name: String) {
    fun onJobPosted(job: JobPost) {
        println("Hi $name! New job posted: ${job.getTitle()}")
    }
}

class EmploymentAgency {
    private val observers = mutableListOf<JobSeeker>()

    fun notify(jobPosting: JobPost) {
        for (observer in observers) {
            observer.onJobPosted(jobPosting)
        }
    }

    fun attach(observer: JobSeeker) {
        observers.add(observer)
    }

    fun addJob(jobPosting: JobPost) {
        notify(jobPosting)
    }
}

// ----------------------------

fun main() {
    val johnDoe = JobSeeker("John Doe")
    val janeDoe = JobSeeker("Jane Doe")

    val jobPostings = EmploymentAgency()
    jobPostings.attach(johnDoe)
    jobPostings.attach(janeDoe)

    jobPostings.addJob(JobPost("Software Engineer"))
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
class JobPost {
  final String _title;

  JobPost(this._title);

  String getTitle() => _title;
}

class JobSeeker {
  final String _name;

  JobSeeker(this._name);

  void onJobPosted(JobPost job) {
    print('Hi $_name! New job posted: ${job.getTitle()}');
  }
}

class EmploymentAgency {
  final List<JobSeeker> _observers = [];

  void notify(JobPost jobPosting) {
    for (var observer in _observers) {
      observer.onJobPosted(jobPosting);
    }
  }

  void attach(JobSeeker observer) {
    _observers.add(observer);
  }

  void addJob(JobPost jobPosting) {
    notify(jobPosting);
  }
}

// ----------------------------

void main() {
  var johnDoe = JobSeeker('John Doe');
  var janeDoe = JobSeeker('Jane Doe');

  var jobPostings = EmploymentAgency();
  jobPostings.attach(johnDoe);
  jobPostings.attach(janeDoe);

  jobPostings.addJob(JobPost('Software Engineer'));
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یه تغییر باید چند جای مستقل رو خودکار باخبر کنه و نمی‌خوای فرستنده بدونه گیرنده‌ها کی‌ان»؛ ❌ «وقتی فقط یه شنونده داری یا یه صدا زدن مستقیم کافیه».
> 🪤 **دام رایج:** «یادت بره ناظرها رو detach کنی، نشتی حافظه و خبردادن به شیء مرده می‌گیری».
> 🔗 **فرقش با [میانجی (Mediator)](#میانجی-mediator-):** «ناظر یه‌طرفه از سوژه به ناظرها خبر پخش می‌کنه؛ میانجی رفت‌وبرگشتِ چندتا همکار رو از یه مرکز هماهنگ می‌کنه».


<br>

---

<div align="center">

## بازدیدکننده (Visitor) 🏃

</div>

<div align="center">
🦁 <b>مثال دنیای واقعی: دامپزشک در باغ‌وحش</b>
</div>

فرض کن توی یه باغ‌وحش، کلی حیوان داری: میمون، شیر، دلفین و...
حالا هر چند وقت یک بار می‌خوای یه «عملیات جدید» به همه‌شون اضافه کنی:
*   یک روز «معاینه»
*   یک روز «واکسن»
*   یک روز «گزارش‌گیری از صدا»

اگه هر بار بری توی کلاس تک‌تک حیوان‌ها دست ببری و متد جدید اضافه کنی، کدت خیلی زود شلوغ و شکننده می‌شه.
الگوی Visitor می‌گه: «عملیات‌ها رو جدا کن. بذار حیوان‌ها همون‌قدر ساده بمونن، و بازدیدکننده‌ها (Visitorها) بیان روشون عملیات انجام بدن.»

💡 **به زبون ساده:**
> این پترن می‌گه: **«بدون تغییر کلاس‌های اصلی، قابلیت/عملیات جدید اضافه کن (با Visitor).»**

ویکی‌پدیا:

<div dir="ltr">

> In object-oriented programming and software engineering, the visitor design pattern is a way of separating an
> algorithm from an object structure on which it operates. A practical result of this separation is the ability to add
> new
> operations to existing object structures without modifying those structures. It is one way to follow the open/closed
> principle.

</div>

یعنی الگوی Visitor راهیه برای جدا کردن یه عملیات از ساختار اشیایی که روش کار می‌کنه. سودِ عملی این جداسازی اینه که می‌تونی عملیات جدید رو به اشیای موجود اضافه کنی، بدون اینکه خود اون اشیا رو دست بزنی؛ یعنی همون اصل باز/بسته (Open/Closed) رو رعایت کردی.

این کار رو با «ارجاع دوگانه» (Double Dispatch) انجام می‌دن. حیوون با `accept` خودش رو به بازدیدکننده معرفی می‌کنه و بازدیدکننده هم متد `visit` مخصوص همون نوع رو صدا می‌زنه. این‌طوری کارِ درست هم‌زمان بر اساس «نوع حیوون» و «نوع عملیات» انتخاب می‌شه.

**مثال برنامه‌نویسی**

فرض کن یک باغ وحش مجازی داریم و می‌خوایم یک عالمه امکان رو به حیوون‌های مختلف اضافه کنیم! مثلا صداشون، نحوه پریدنشون و
...

<details>
<summary>Python</summary>

<div dir="ltr">

```python
# Visitee
class Animal:
    def accept(self, operation):
        pass


# Visitor
class AnimalOperation:
    def visitMonkey(self, monkey):
        pass

    def visitLion(self, lion):
        pass

    def visitDolphin(self, dolphin):
        pass


class Monkey(Animal):
    def shout(self):
        print('Ooh oo aa aa!')

    def accept(self, operation):
        operation.visitMonkey(self)


class Lion(Animal):
    def roar(self):
        print('Roaaar!')

    def accept(self, operation):
        operation.visitLion(self)


class Dolphin(Animal):
    def speak(self):
        print('Tuut tuttu tuutt!')

    def accept(self, operation):
        operation.visitDolphin(self)


class Speak(AnimalOperation):
    def visitMonkey(self, monkey):
        monkey.shout()

    def visitLion(self, lion):
        lion.roar()

    def visitDolphin(self, dolphin):
        dolphin.speak()


class Jump(AnimalOperation):
    def visitMonkey(self, monkey):
        print('Jumped 20 feet high! on to the tree!')

    def visitLion(self, lion):
        print('Jumped 7 feet! back on the ground!')

    def visitDolphin(self, dolphin):
        print('Walked on water a little and disappeared')


monkey = Monkey()
lion = Lion()
dolphin = Dolphin()

speak = Speak()
jump = Jump()

monkey.accept(speak)   # Ooh oo aa aa!
lion.accept(speak)     # Roaaar!
dolphin.accept(speak)  # Tuut tuttu tuutt!

monkey.accept(jump)    # Jumped 20 feet high! on to the tree!
lion.accept(jump)      # Jumped 7 feet! back on the ground!
dolphin.accept(jump)   # Walked on water a little and disappeared
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface AnimalOperation {
  visitMonkey(monkey: Monkey): void;
  visitLion(lion: Lion): void;
  visitDolphin(dolphin: Dolphin): void;
}

interface Animal {
  accept(operation: AnimalOperation): void;
}

class Monkey implements Animal {
  shout() {
    console.log("Ooh oo aa aa!");
  }

  accept(operation: AnimalOperation): void {
    operation.visitMonkey(this);
  }
}

class Lion implements Animal {
  roar() {
    console.log("Roaaar!");
  }

  accept(operation: AnimalOperation): void {
    operation.visitLion(this);
  }
}

class Dolphin implements Animal {
  speak() {
    console.log("Tuut tuttu tuutt!");
  }

  accept(operation: AnimalOperation): void {
    operation.visitDolphin(this);
  }
}

class Speak implements AnimalOperation {
  visitMonkey(monkey: Monkey): void {
    monkey.shout();
  }

  visitLion(lion: Lion): void {
    lion.roar();
  }

  visitDolphin(dolphin: Dolphin): void {
    dolphin.speak();
  }
}

class Jump implements AnimalOperation {
  visitMonkey(monkey: Monkey): void {
    console.log("Jumped 20 feet high! on to the tree!");
  }

  visitLion(lion: Lion): void {
    console.log("Jumped 7 feet! back on the ground!");
  }

  visitDolphin(dolphin: Dolphin): void {
    console.log("Walked on water a little and disappeared");
  }
}

const monkey = new Monkey();
const lion = new Lion();
const dolphin = new Dolphin();

const speak = new Speak();
const jump = new Jump();

monkey.accept(speak);   // Ooh oo aa aa!
lion.accept(speak);     // Roaaar!
dolphin.accept(speak);  // Tuut tuttu tuutt!

monkey.accept(jump);    // Jumped 20 feet high! on to the tree!
lion.accept(jump);      // Jumped 7 feet! back on the ground!
dolphin.accept(jump);   // Walked on water a little and disappeared
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Monkey {
    shout() {
        console.log("Ooh oo aa aa!");
    }

    accept(operation) {
        operation.visitMonkey(this);
    }
}

class Lion {
    roar() {
        console.log("Roaaar!");
    }

    accept(operation) {
        operation.visitLion(this);
    }
}

class Dolphin {
    speak() {
        console.log("Tuut tuttu tuutt!");
    }

    accept(operation) {
        operation.visitDolphin(this);
    }
}

class Speak {
    visitMonkey(monkey) {
        monkey.shout();
    }

    visitLion(lion) {
        lion.roar();
    }

    visitDolphin(dolphin) {
        dolphin.speak();
    }
}

class Jump {
    visitMonkey(monkey) {
        console.log("Jumped 20 feet high! on to the tree!");
    }

    visitLion(lion) {
        console.log("Jumped 7 feet! back on the ground!");
    }

    visitDolphin(dolphin) {
        console.log("Walked on water a little and disappeared");
    }
}

const monkey = new Monkey();
const lion = new Lion();
const dolphin = new Dolphin();

const speak = new Speak();
const jump = new Jump();

monkey.accept(speak);   // Ooh oo aa aa!
lion.accept(speak);     // Roaaar!
dolphin.accept(speak);  // Tuut tuttu tuutt!

monkey.accept(jump);    // Jumped 20 feet high! on to the tree!
lion.accept(jump);      // Jumped 7 feet! back on the ground!
dolphin.accept(jump);   // Walked on water a little and disappeared
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;

// Visitee
interface IAnimal
{
  void Accept(IAnimalOperation operation);
}

// Visitor
interface IAnimalOperation
{
  void VisitMonkey(Monkey monkey);
  void VisitLion(Lion lion);
  void VisitDolphin(Dolphin dolphin);
}

class Monkey : IAnimal
{
  public void Shout()
  {
    Console.WriteLine("Ooh oo aa aa!");
  }

  public void Accept(IAnimalOperation operation)
  {
    operation.VisitMonkey(this);
  }
}

class Lion : IAnimal
{
  public void Roar()
  {
    Console.WriteLine("Roaaar!");
  }

  public void Accept(IAnimalOperation operation)
  {
    operation.VisitLion(this);
  }
}

class Dolphin : IAnimal
{
  public void Speak()
  {
    Console.WriteLine("Tuut tuttu tuutt!");
  }

  public void Accept(IAnimalOperation operation)
  {
    operation.VisitDolphin(this);
  }
}

class Speak : IAnimalOperation
{
  public void VisitMonkey(Monkey monkey)
  {
    monkey.Shout();
  }

  public void VisitLion(Lion lion)
  {
    lion.Roar();
  }

  public void VisitDolphin(Dolphin dolphin)
  {
    dolphin.Speak();
  }
}

class Jump : IAnimalOperation
{
  public void VisitMonkey(Monkey monkey)
  {
    Console.WriteLine("Jumped 20 feet high! on to the tree!");
  }

  public void VisitLion(Lion lion)
  {
    Console.WriteLine("Jumped 7 feet! back on the ground!");
  }

  public void VisitDolphin(Dolphin dolphin)
  {
    Console.WriteLine("Walked on water a little and disappeared");
  }
}

// ----------------------------

var monkey = new Monkey();
var lion = new Lion();
var dolphin = new Dolphin();

var speak = new Speak();
var jump = new Jump();

monkey.Accept(speak);    // Ooh oo aa aa!
lion.Accept(speak);      // Roaaar!
dolphin.Accept(speak);   // Tuut tuttu tuutt!

monkey.Accept(jump);     // Jumped 20 feet high! on to the tree!
lion.Accept(jump);       // Jumped 7 feet! back on the ground!
dolphin.Accept(jump);    // Walked on water a little and disappeared
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
// Visitee
interface AnimalInterface
{
  public function accept(AnimalOperationInterface $operation);
}

// Visitor
interface AnimalOperationInterface
{
  public function visitMonkey(Monkey $monkey);
  public function visitLion(Lion $lion);
  public function visitDolphin(Dolphin $dolphin);
}

class Monkey implements AnimalInterface
{
  public function shout()
  {
    echo "Ooh oo aa aa!\n";
  }

  public function accept(AnimalOperationInterface $operation)
  {
    $operation->visitMonkey($this);
  }
}

class Lion implements AnimalInterface
{
  public function roar()
  {
    echo "Roaaar!\n";
  }

  public function accept(AnimalOperationInterface $operation)
  {
    $operation->visitLion($this);
  }
}

class Dolphin implements AnimalInterface
{
  public function speak()
  {
    echo "Tuut tuttu tuutt!\n";
  }

  public function accept(AnimalOperationInterface $operation)
  {
    $operation->visitDolphin($this);
  }
}

class Speak implements AnimalOperationInterface
{
  public function visitMonkey(Monkey $monkey)
  {
    $monkey->shout();
  }

  public function visitLion(Lion $lion)
  {
    $lion->roar();
  }

  public function visitDolphin(Dolphin $dolphin)
  {
    $dolphin->speak();
  }
}

class Jump implements AnimalOperationInterface
{
  public function visitMonkey(Monkey $monkey)
  {
    echo "Jumped 20 feet high! on to the tree!\n";
  }

  public function visitLion(Lion $lion)
  {
    echo "Jumped 7 feet! back on the ground!\n";
  }

  public function visitDolphin(Dolphin $dolphin)
  {
    echo "Walked on water a little and disappeared\n";
  }
}

$monkey = new Monkey();
$lion = new Lion();
$dolphin = new Dolphin();

$speak = new Speak();
$jump = new Jump();

$monkey->accept($speak);    // Ooh oo aa aa!
$lion->accept($speak);      // Roaaar!
$dolphin->accept($speak);   // Tuut tuttu tuutt!

$monkey->accept($jump);     // Jumped 20 feet high! on to the tree!
$lion->accept($jump);       // Jumped 7 feet! back on the ground!
$dolphin->accept($jump);    // Walked on water a little and disappeared
```

</div>

</details>

<details>
  <summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

// Visitee
type Animal interface {
	Accept(operation AnimalOperation)
}

// Visitor
type AnimalOperation interface {
	VisitMonkey(monkey *Monkey)
	VisitLion(lion *Lion)
	VisitDolphin(dolphin *Dolphin)
}

type Monkey struct{}

func (m *Monkey) Shout() {
	fmt.Println("Ooh oo aa aa!")
}

func (m *Monkey) Accept(operation AnimalOperation) {
	operation.VisitMonkey(m)
}

type Lion struct{}

func (l *Lion) Roar() {
	fmt.Println("Roaaar!")
}

func (l *Lion) Accept(operation AnimalOperation) {
	operation.VisitLion(l)
}

type Dolphin struct{}

func (d *Dolphin) Speak() {
	fmt.Println("Tuut tuttu tuutt!")
}

func (d *Dolphin) Accept(operation AnimalOperation) {
	operation.VisitDolphin(d)
}

type Speak struct{}

func (s *Speak) VisitMonkey(monkey *Monkey) {
	monkey.Shout()
}

func (s *Speak) VisitLion(lion *Lion) {
	lion.Roar()
}

func (s *Speak) VisitDolphin(dolphin *Dolphin) {
	dolphin.Speak()
}

type Jump struct{}

func (j *Jump) VisitMonkey(monkey *Monkey) {
	fmt.Println("Jumped 20 feet high! on to the tree!")
}

func (j *Jump) VisitLion(lion *Lion) {
	fmt.Println("Jumped 7 feet! back on the ground!")
}

func (j *Jump) VisitDolphin(dolphin *Dolphin) {
	fmt.Println("Walked on water a little and disappeared")
}

func main() {
	monkey := &Monkey{}
	lion := &Lion{}
	dolphin := &Dolphin{}

	speak := &Speak{}
	jump := &Jump{}

	monkey.Accept(speak)  // Ooh oo aa aa!
	lion.Accept(speak)    // Roaaar!
	dolphin.Accept(speak) // Tuut tuttu tuutt!

	monkey.Accept(jump)  // Jumped 20 feet high! on to the tree!
	lion.Accept(jump)    // Jumped 7 feet! back on the ground!
	dolphin.Accept(jump) // Walked on water a little and disappeared
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface AnimalOperation {
    void visitMonkey(Monkey monkey);
    void visitLion(Lion lion);
    void visitDolphin(Dolphin dolphin);
}

interface Animal {
    void accept(AnimalOperation operation);
}

class Monkey implements Animal {
    public void shout() {
        System.out.println("Ooh oo aa aa!");
    }

    @Override
    public void accept(AnimalOperation operation) {
        operation.visitMonkey(this);
    }
}

class Lion implements Animal {
    public void roar() {
        System.out.println("Roaaar!");
    }

    @Override
    public void accept(AnimalOperation operation) {
        operation.visitLion(this);
    }
}

class Dolphin implements Animal {
    public void speak() {
        System.out.println("Tuut tuttu tuutt!");
    }

    @Override
    public void accept(AnimalOperation operation) {
        operation.visitDolphin(this);
    }
}

class Speak implements AnimalOperation {
    @Override
    public void visitMonkey(Monkey monkey) {
        monkey.shout();
    }

    @Override
    public void visitLion(Lion lion) {
        lion.roar();
    }

    @Override
    public void visitDolphin(Dolphin dolphin) {
        dolphin.speak();
    }
}

class Jump implements AnimalOperation {
    @Override
    public void visitMonkey(Monkey monkey) {
        System.out.println("Jumped 20 feet high! on to the tree!");
    }

    @Override
    public void visitLion(Lion lion) {
        System.out.println("Jumped 7 feet! back on the ground!");
    }

    @Override
    public void visitDolphin(Dolphin dolphin) {
        System.out.println("Walked on water a little and disappeared");
    }
}

// -----------------------

Monkey monkey = new Monkey();
Lion lion = new Lion();
Dolphin dolphin = new Dolphin();

Speak speak = new Speak();
Jump jump = new Jump();

monkey.accept(speak);   // Ooh oo aa aa!
lion.accept(speak);     // Roaaar!
dolphin.accept(speak);  // Tuut tuttu tuutt!

monkey.accept(jump);    // Jumped 20 feet high! on to the tree!
lion.accept(jump);      // Jumped 7 feet! back on the ground!
dolphin.accept(jump);   // Walked on water a little and disappeared
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

// Forward declarations
class Monkey;
class Lion;
class Dolphin;

// Visitor interface
class AnimalOperation {
public:
    virtual ~AnimalOperation() = default;
    virtual void visitMonkey(Monkey& monkey) = 0;
    virtual void visitLion(Lion& lion) = 0;
    virtual void visitDolphin(Dolphin& dolphin) = 0;
};

// Animal interface
class Animal {
public:
    virtual ~Animal() = default;
    virtual void accept(AnimalOperation& operation) = 0;
};

// Concrete animals
class Monkey : public Animal {
public:
    void shout() {
        std::cout << "Ooh oo aa aa!" << std::endl;
    }

    void accept(AnimalOperation& operation) override {
        operation.visitMonkey(*this);
    }
};

class Lion : public Animal {
public:
    void roar() {
        std::cout << "Roaaar!" << std::endl;
    }

    void accept(AnimalOperation& operation) override {
        operation.visitLion(*this);
    }
};

class Dolphin : public Animal {
public:
    void speak() {
        std::cout << "Tuut tuttu tuutt!" << std::endl;
    }

    void accept(AnimalOperation& operation) override {
        operation.visitDolphin(*this);
    }
};

// Concrete visitor: Speak
class Speak : public AnimalOperation {
public:
    void visitMonkey(Monkey& monkey) override {
        monkey.shout();
    }

    void visitLion(Lion& lion) override {
        lion.roar();
    }

    void visitDolphin(Dolphin& dolphin) override {
        dolphin.speak();
    }
};

// Concrete visitor: Jump
class Jump : public AnimalOperation {
public:
    void visitMonkey(Monkey& monkey) override {
        std::cout << "Jumped 20 feet high! on to the tree!" << std::endl;
    }

    void visitLion(Lion& lion) override {
        std::cout << "Jumped 7 feet! back on the ground!" << std::endl;
    }

    void visitDolphin(Dolphin& dolphin) override {
        std::cout << "Walked on water a little and disappeared" << std::endl;
    }
};

// ----------------------------

int main() {
    Monkey monkey;
    Lion lion;
    Dolphin dolphin;

    Speak speak;
    Jump jump;

    monkey.accept(speak);   // Ooh oo aa aa!
    lion.accept(speak);     // Roaaar!
    dolphin.accept(speak);  // Tuut tuttu tuutt!

    monkey.accept(jump);    // Jumped 20 feet high! on to the tree!
    lion.accept(jump);      // Jumped 7 feet! back on the ground!
    dolphin.accept(jump);   // Walked on water a little and disappeared
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
// Visitee
interface Animal {
    fun accept(operation: AnimalOperation)
}

// Visitor
interface AnimalOperation {
    fun visitMonkey(monkey: Monkey)
    fun visitLion(lion: Lion)
    fun visitDolphin(dolphin: Dolphin)
}

class Monkey : Animal {
    fun shout() = println("Ooh oo aa aa!")

    override fun accept(operation: AnimalOperation) {
        operation.visitMonkey(this)
    }
}

class Lion : Animal {
    fun roar() = println("Roaaar!")

    override fun accept(operation: AnimalOperation) {
        operation.visitLion(this)
    }
}

class Dolphin : Animal {
    fun speak() = println("Tuut tuttu tuutt!")

    override fun accept(operation: AnimalOperation) {
        operation.visitDolphin(this)
    }
}

class Speak : AnimalOperation {
    override fun visitMonkey(monkey: Monkey) = monkey.shout()
    override fun visitLion(lion: Lion) = lion.roar()
    override fun visitDolphin(dolphin: Dolphin) = dolphin.speak()
}

class Jump : AnimalOperation {
    override fun visitMonkey(monkey: Monkey) = println("Jumped 20 feet high! on to the tree!")
    override fun visitLion(lion: Lion) = println("Jumped 7 feet! back on the ground!")
    override fun visitDolphin(dolphin: Dolphin) = println("Walked on water a little and disappeared")
}

// ----------------------------

fun main() {
    val monkey = Monkey()
    val lion = Lion()
    val dolphin = Dolphin()

    val speak = Speak()
    val jump = Jump()

    monkey.accept(speak)
    lion.accept(speak)
    dolphin.accept(speak)

    monkey.accept(jump)
    lion.accept(jump)
    dolphin.accept(jump)
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
// Visitor
abstract class AnimalOperation {
  void visitMonkey(Monkey monkey);
  void visitLion(Lion lion);
  void visitDolphin(Dolphin dolphin);
}

// Visitee
abstract class Animal {
  void accept(AnimalOperation operation);
}

class Monkey implements Animal {
  void shout() => print('Ooh oo aa aa!');

  @override
  void accept(AnimalOperation operation) => operation.visitMonkey(this);
}

class Lion implements Animal {
  void roar() => print('Roaaar!');

  @override
  void accept(AnimalOperation operation) => operation.visitLion(this);
}

class Dolphin implements Animal {
  void speak() => print('Tuut tuttu tuutt!');

  @override
  void accept(AnimalOperation operation) => operation.visitDolphin(this);
}

class Speak implements AnimalOperation {
  @override
  void visitMonkey(Monkey monkey) => monkey.shout();

  @override
  void visitLion(Lion lion) => lion.roar();

  @override
  void visitDolphin(Dolphin dolphin) => dolphin.speak();
}

class Jump implements AnimalOperation {
  @override
  void visitMonkey(Monkey monkey) => print('Jumped 20 feet high! on to the tree!');

  @override
  void visitLion(Lion lion) => print('Jumped 7 feet! back on the ground!');

  @override
  void visitDolphin(Dolphin dolphin) => print('Walked on water a little and disappeared');
}

// ----------------------------

void main() {
  var monkey = Monkey();
  var lion = Lion();
  var dolphin = Dolphin();

  var speak = Speak();
  var jump = Jump();

  monkey.accept(speak);
  lion.accept(speak);
  dolphin.accept(speak);

  monkey.accept(jump);
  lion.accept(jump);
  dolphin.accept(jump);
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی یه ساختار از اشیای ثابت داری و مدام می‌خوای عملیات‌های تازه روشون اضافه کنی، مثل گزارش‌گیری، اعتبارسنجی یا خروجی‌گرفتن؛ ❌ وقتی برعکس، خودِ نوع‌های اشیا مدام عوض و زیاد می‌شن ولی عملیات‌ها تقریباً ثابتن.
> 🪤 **دام رایج:** هر بار که یه نوع حیوون جدید اضافه می‌کنی، مجبوری توی تک‌تک Visitorها یه متد `visit` جدید بنویسی؛ پس اضافه کردن «نوع» اینجا گرونه.
> 🔗 **فرقش با الگوهای دیگه:** یک جمله: عملیات‌ها ارزون اضافه می‌شن ولی نوع جدید گرونه.


<br>

---

<div align="center">

## استراتژی (Strategy) 💡

</div>

<div align="center">
🧠 <b>مثال دنیای واقعی: انتخاب روش (بسته به شرایط)</b>
</div>

فرض کن می‌خوای یه کار رو انجام بدی، ولی چند راه مختلف برای انجام دادنش داری.
مثلاً موقع پرداخت توی صندوق فروشگاه:
*   یکی پول نقد می‌ده.
*   یکی کارت می‌کشه.
*   یکی هم از کیف‌پول دیجیتالش (Wallet) پرداخت می‌کنه.

صندوق همیشه یه کار ساده می‌کنه: «این مبلغ رو بگیر». اینکه پول چطوری گرفته می‌شه، به خودِ روشِ پرداخت مربوطه، نه به صندوق.
تو نمی‌خوای کل کد صندوق رو پر کنی از `if/else`‌های طولانی، طوری که هر بار یه روش پرداخت جدید اومد، مجبور شی همه‌جا رو دستکاری کنی.
پس هر روش پرداخت رو جدا می‌کنی و هر لحظه هر کدوم رو خواستی می‌ذاری داخل صندوق. ✅

💡 **به زبون ساده:**
> این پترن می‌گه: **«چند تا الگوریتم قابل تعویض داشته باش و انتخابشون رو بنداز به زمان اجرا.»**

ویکی‌پدیا:

<div dir="ltr">

> In computer programming, the strategy pattern (also known as the policy pattern) is a behavioural software design
> pattern that enables an algorithm's behavior to be selected at runtime.

</div>

خلاصه‌اش این می‌شه: چند تا روش انجام یک کار رو جدا از هم نگه می‌داری و هر کدوم رو که خواستی، همون لحظه‌ی اجرا (Runtime) انتخاب می‌کنی.
این‌طوری بدنه‌ی اصلی برنامه دست‌نخورده می‌مونه و فقط روشی که بهش می‌دی عوض می‌شه.

**مثال برنامه‌نویسی**

می‌خوایم یه صندوق پرداخت بسازیم که موقع تسویه‌حساب، بسته به این که مشتری چه روشی رو انتخاب کرده، از همون روش پرداخت استفاده کنه!

اول یه قرارداد مشترک («پرداخت کن») تعریف می‌کنیم، بعد یه کلاس صندوق می‌سازیم که وظیفه‌اش فقط نگه‌داشتن روش پرداخت و سپردن کار به اونه.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class PaymentStrategy:
    def pay(self, amount):
        pass


class CashPayment(PaymentStrategy):
    def pay(self, amount):
        print(f'Paid {amount} in cash')


class CardPayment(PaymentStrategy):
    def pay(self, amount):
        print(f'Paid {amount} by card')


class WalletPayment(PaymentStrategy):
    def pay(self, amount):
        print(f'Paid {amount} from wallet')


class Checkout:
    def __init__(self, strategy):
        self._strategy = strategy

    def checkout(self, amount):
        self._strategy.pay(amount)


# ----------------------------

checkout = Checkout(CashPayment())
checkout.checkout(100)  # Output: Paid 100 in cash

checkout = Checkout(CardPayment())
checkout.checkout(250)  # Output: Paid 250 by card
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface PaymentStrategy {
    pay(amount: number): void;
}

class CashPayment implements PaymentStrategy {
    pay(amount: number): void {
        console.log(`Paid ${amount} in cash`);
    }
}

class CardPayment implements PaymentStrategy {
    pay(amount: number): void {
        console.log(`Paid ${amount} by card`);
    }
}

class WalletPayment implements PaymentStrategy {
    pay(amount: number): void {
        console.log(`Paid ${amount} from wallet`);
    }
}

class Checkout {
    private strategy: PaymentStrategy;

    constructor(strategy: PaymentStrategy) {
        this.strategy = strategy;
    }

    checkout(amount: number): void {
        this.strategy.pay(amount);
    }
}

// ----------------------------

let checkout = new Checkout(new CashPayment());
checkout.checkout(100); // Output: Paid 100 in cash

checkout = new Checkout(new CardPayment());
checkout.checkout(250); // Output: Paid 250 by card
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class CashPayment {
    pay(amount) {
        console.log(`Paid ${amount} in cash`);
    }
}

class CardPayment {
    pay(amount) {
        console.log(`Paid ${amount} by card`);
    }
}

class WalletPayment {
    pay(amount) {
        console.log(`Paid ${amount} from wallet`);
    }
}

class Checkout {
    constructor(strategy) {
        this.strategy = strategy;
    }

    checkout(amount) {
        this.strategy.pay(amount);
    }
}

let checkout = new Checkout(new CashPayment());
checkout.checkout(100); // Output: Paid 100 in cash

checkout = new Checkout(new CardPayment());
checkout.checkout(250); // Output: Paid 250 by card
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface IPaymentStrategy
{
  void Pay(int amount);
}

class CashPayment : IPaymentStrategy
{
  public void Pay(int amount)
  {
    Console.WriteLine($"Paid {amount} in cash");
  }
}

class CardPayment : IPaymentStrategy
{
  public void Pay(int amount)
  {
    Console.WriteLine($"Paid {amount} by card");
  }
}

class WalletPayment : IPaymentStrategy
{
  public void Pay(int amount)
  {
    Console.WriteLine($"Paid {amount} from wallet");
  }
}

class ShoppingCart
{
  private readonly IPaymentStrategy mStrategy;

  public ShoppingCart(IPaymentStrategy strategy)
  {
    mStrategy = strategy;
  }

  public void Checkout(int amount)
  {
    mStrategy.Pay(amount);
  }
}

// ----------------------------

var checkout = new ShoppingCart(new CashPayment());
checkout.Checkout(100); // Output: Paid 100 in cash

checkout = new ShoppingCart(new CardPayment());
checkout.Checkout(250); // Output: Paid 250 by card

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface PaymentStrategyInterface {
  public function pay($amount);
}

class CashPayment implements PaymentStrategyInterface {
  public function pay($amount) {
    echo "Paid $amount in cash\n";
  }
}

class CardPayment implements PaymentStrategyInterface {
  public function pay($amount) {
    echo "Paid $amount by card\n";
  }
}

class WalletPayment implements PaymentStrategyInterface {
  public function pay($amount) {
    echo "Paid $amount from wallet\n";
  }
}

class Checkout {
  private $mStrategy;

  public function __construct(PaymentStrategyInterface $strategy) {
    $this->mStrategy = $strategy;
  }

  public function checkout($amount) {
    $this->mStrategy->pay($amount);
  }
}

$checkout = new Checkout(new CashPayment());
$checkout->checkout(100); // Output: Paid 100 in cash

$checkout = new Checkout(new CardPayment());
$checkout->checkout(250); // Output: Paid 250 by card

```

</div>

</details>

<details>
  <summary>Go</summary>

<div dir="ltr">

```go
package main

import (
	"fmt"
)

// PaymentStrategy is the interface that defines a payment method
type PaymentStrategy interface {
	Pay(amount int)
}

// CashPayment implements the PaymentStrategy interface
type CashPayment struct{}

func (c *CashPayment) Pay(amount int) {
	fmt.Printf("Paid %d in cash\n", amount)
}

// CardPayment implements the PaymentStrategy interface
type CardPayment struct{}

func (c *CardPayment) Pay(amount int) {
	fmt.Printf("Paid %d by card\n", amount)
}

// WalletPayment implements the PaymentStrategy interface
type WalletPayment struct{}

func (w *WalletPayment) Pay(amount int) {
	fmt.Printf("Paid %d from wallet\n", amount)
}

// Checkout is the context that uses a payment strategy
type Checkout struct {
	strategy PaymentStrategy
}

func NewCheckout(strategy PaymentStrategy) *Checkout {
	return &Checkout{strategy: strategy}
}

func (c *Checkout) Checkout(amount int) {
	c.strategy.Pay(amount)
}

func main() {
	checkout := NewCheckout(&CashPayment{})
	checkout.Checkout(100) // Output: Paid 100 in cash

	checkout = NewCheckout(&CardPayment{})
	checkout.Checkout(250) // Output: Paid 250 by card
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface PaymentStrategy {
    void pay(int amount);
}

class CashPayment implements PaymentStrategy {

    @Override
    public void pay(int amount) {
        System.out.println("Paid " + amount + " in cash");
    }
}

class CardPayment implements PaymentStrategy {

    @Override
    public void pay(int amount) {
        System.out.println("Paid " + amount + " by card");
    }
}

class WalletPayment implements PaymentStrategy {

    @Override
    public void pay(int amount) {
        System.out.println("Paid " + amount + " from wallet");
    }
}

class Checkout {
    private PaymentStrategy strategy;

    public Checkout(PaymentStrategy strategy) {
        this.strategy = strategy;
    }

    public void checkout(int amount) {
        strategy.pay(amount);
    }
}

// ----------------------------

Checkout checkout = new Checkout(new CashPayment());
checkout.checkout(100); // Paid 100 in cash

checkout = new Checkout(new CardPayment());
checkout.checkout(250); // Paid 250 by card
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

class PaymentStrategy {
public:
    virtual ~PaymentStrategy() = default;
    virtual void pay(int amount) = 0;
};

class CashPayment : public PaymentStrategy {
public:
    void pay(int amount) override {
        std::cout << "Paid " << amount << " in cash" << std::endl;
    }
};

class CardPayment : public PaymentStrategy {
public:
    void pay(int amount) override {
        std::cout << "Paid " << amount << " by card" << std::endl;
    }
};

class WalletPayment : public PaymentStrategy {
public:
    void pay(int amount) override {
        std::cout << "Paid " << amount << " from wallet" << std::endl;
    }
};

class Checkout {
private:
    PaymentStrategy* strategy;

public:
    Checkout(PaymentStrategy* s) : strategy(s) {}

    void checkout(int amount) {
        strategy->pay(amount);
    }
};

// ----------------------------

int main() {
    CashPayment cash;
    Checkout checkout(&cash);
    checkout.checkout(100); // Output: Paid 100 in cash

    CardPayment card;
    Checkout checkout2(&card);
    checkout2.checkout(250); // Output: Paid 250 by card
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface PaymentStrategy {
    fun pay(amount: Int)
}

class CashPayment : PaymentStrategy {
    override fun pay(amount: Int) {
        println("Paid $amount in cash")
    }
}

class CardPayment : PaymentStrategy {
    override fun pay(amount: Int) {
        println("Paid $amount by card")
    }
}

class WalletPayment : PaymentStrategy {
    override fun pay(amount: Int) {
        println("Paid $amount from wallet")
    }
}

class Checkout(private val strategy: PaymentStrategy) {
    fun checkout(amount: Int) {
        strategy.pay(amount)
    }
}

// ----------------------------

fun main() {
    var checkout = Checkout(CashPayment())
    checkout.checkout(100)

    checkout = Checkout(CardPayment())
    checkout.checkout(250)
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class PaymentStrategy {
  void pay(int amount);
}

class CashPayment implements PaymentStrategy {
  @override
  void pay(int amount) => print('Paid $amount in cash');
}

class CardPayment implements PaymentStrategy {
  @override
  void pay(int amount) => print('Paid $amount by card');
}

class WalletPayment implements PaymentStrategy {
  @override
  void pay(int amount) => print('Paid $amount from wallet');
}

class Checkout {
  final PaymentStrategy _strategy;

  Checkout(this._strategy);

  void checkout(int amount) => _strategy.pay(amount);
}

// ----------------------------

void main() {
  var checkout = Checkout(CashPayment());
  checkout.checkout(100);

  checkout = Checkout(CardPayment());
  checkout.checkout(250);
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی چند تا روش هم‌خانواده برای یه کار داری و می‌خوای موقع اجرا بینشون سوییچ کنی»؛ ❌ «وقتی فقط یه روش داری و قرار نیست هیچ‌وقت عوض بشه».
> 🪤 **دام رایج:** «جداکردن هر `if` کوچیک به یه کلاس استراتژی جدا؛ این کار رو فقط وقتی بکن که روش‌ها واقعاً مستقل و قابل تعویض‌ان».
> 🔗 **فرقش با [حالت (State)](#حالت-state-):** «استراتژی روشِ انجام یه کار رو از بیرون بهش می‌دی و خودش عوضش نمی‌کنه؛ ولی حالت بر اساس وضعیت داخلی شیء، خودبه‌خود رفتارش رو تغییر می‌ده».


<br>

---

<div align="center">

## حالت (State) 💢

</div>

<div align="center">
🚦 <b>مثال دنیای واقعی: چراغ راهنمایی</b>
</div>

یه چراغ راهنمایی رو در نظر بگیر.
قرمزه؛ بعد سبز می‌شه؛ بعد زرد می‌شه؛ بعد دوباره قرمز. هر رنگ، خودش می‌دونه نوبت بعدی باید بره سراغ کدوم رنگ.

نکته اینه که خود چراغ یه دکمه «برو حالت بعدی» بیشتر نداره؛ ولی **اینکه بعدش چی می‌شه** به حالت فعلیش بستگی داره.
این دقیقاً همون چیزیه که State می‌گه: به جای اینکه توی یک کلاس بزرگ پر از شرط بنویسی، هر حالت رو به شکل یه آبجکت جدا نگه می‌داری و خود حالت تصمیم می‌گیره گذار (Transition) بعدی به کجاست. 🧩

💡 **به زبون ساده:**
> این پترن می‌گه: **«رفتار شیء رو به state فعلیش بسپر؛ با عوض شدن state، رفتار هم عوض می‌شه.»**

ویکی‌پدیا:

<div dir="ltr">

> The state pattern is a behavioral software design pattern that implements a state machine in an object-oriented way.
> With the state pattern, a state machine is implemented by implementing each individual state as a derived class of the
> state pattern interface, and implementing state transitions by invoking methods defined by the pattern's superclass.
> The
> state pattern can be interpreted as a strategy pattern which is able to switch the current strategy through
> invocations
> of methods defined in the pattern's interface.

</div>

خلاصه‌اش این می‌شه که با الگوی State یه ماشین حالت (State Machine) رو شیءگرا می‌سازی؛ هر حالت رو یه کلاس جدا می‌گیری و خود حالت تصمیم می‌گیره بعدیش چی باشه.
خیلی هم شبیه استراتژیه (Strategy)؛ فقط فرقش اینه که اینجا خودِ شیء حالتش رو از تو عوض می‌کنه.

**مثال برنامه‌نویسی**

می‌خوایم یک چراغ راهنمایی بسازیم که سه حالت داشته باشه؛ قرمز، سبز و زرد. هر حالت باید بدونه اسمش چیه و بعدش نوبتِ کدوم حالته؛ یعنی از قرمز به سبز، از سبز به زرد و از زرد دوباره به قرمز.

اول بیا کلاس‌های حالت رو بر پایه الگوی State بسازیم:

بعد خود چراغ رو بسازیم و بهش یاد بدیم حالت فعلیش رو نگه داره و موقع گذار، تصمیم رو به خود حالت بسپره!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
from abc import ABC, abstractmethod


class TrafficLightState(ABC):
    @abstractmethod
    def name(self):
        ...

    @abstractmethod
    def next(self):
        ...


class RedLight(TrafficLightState):
    def name(self):
        return "Red"

    def next(self):
        return GreenLight()


class GreenLight(TrafficLightState):
    def name(self):
        return "Green"

    def next(self):
        return YellowLight()


class YellowLight(TrafficLightState):
    def name(self):
        return "Yellow"

    def next(self):
        return RedLight()


class TrafficLight:
    def __init__(self, state):
        self._state = state

    def name(self):
        return self._state.name()

    def next(self):
        self._state = self._state.next()


# ----------------------------

light = TrafficLight(RedLight())
for _ in range(4):
    print(light.name())
    light.next()

'''
Output:
Red
Green
Yellow
Red
'''

```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
interface TrafficLightState {
    name(): string;
    next(): TrafficLightState;
}

class RedLight implements TrafficLightState {
    name(): string {
        return "Red";
    }

    next(): TrafficLightState {
        return new GreenLight();
    }
}

class GreenLight implements TrafficLightState {
    name(): string {
        return "Green";
    }

    next(): TrafficLightState {
        return new YellowLight();
    }
}

class YellowLight implements TrafficLightState {
    name(): string {
        return "Yellow";
    }

    next(): TrafficLightState {
        return new RedLight();
    }
}

class TrafficLight {
    private state: TrafficLightState;

    constructor(state: TrafficLightState) {
        this.state = state;
    }

    name(): string {
        return this.state.name();
    }

    next(): void {
        this.state = this.state.next();
    }
}

// ----------------------------

const light = new TrafficLight(new RedLight());
for (let i = 0; i < 4; i++) {
    console.log(light.name());
    light.next();
}

// Output:
// Red
// Green
// Yellow
// Red
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class RedLight {
    name() {
        return "Red";
    }

    next() {
        return new GreenLight();
    }
}

class GreenLight {
    name() {
        return "Green";
    }

    next() {
        return new YellowLight();
    }
}

class YellowLight {
    name() {
        return "Yellow";
    }

    next() {
        return new RedLight();
    }
}

class TrafficLight {
    constructor(state) {
        this.state = state;
    }

    name() {
        return this.state.name();
    }

    next() {
        this.state = this.state.next();
    }
}

// ----------------------------

const light = new TrafficLight(new RedLight());
for (let i = 0; i < 4; i++) {
    console.log(light.name());
    light.next();
}

// Output:
// Red
// Green
// Yellow
// Red
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


interface ITrafficLightState {
  string Name();
  ITrafficLightState Next();
}

class RedLight : ITrafficLightState
{
  public string Name() => "Red";
  public ITrafficLightState Next() => new GreenLight();
}

class GreenLight : ITrafficLightState
{
  public string Name() => "Green";
  public ITrafficLightState Next() => new YellowLight();
}

class YellowLight : ITrafficLightState
{
  public string Name() => "Yellow";
  public ITrafficLightState Next() => new RedLight();
}

class TrafficLight {

  private ITrafficLightState mState;

  public TrafficLight(ITrafficLightState state)
  {
    mState = state;
  }

  public string Name() => mState.Name();

  public void Next()
  {
    mState = mState.Next();
  }

}


// ----------------------------

var light = new TrafficLight(new RedLight());

for (int i = 0; i < 4; i++)
{
  Console.WriteLine(light.Name());
  light.Next();
}

// Output:
// Red
// Green
// Yellow
// Red

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface TrafficLightStateInterface {
  public function name(): string;
  public function next(): TrafficLightStateInterface;
}

class RedLight implements TrafficLightStateInterface
{
  public function name(): string
  {
    return "Red";
  }

  public function next(): TrafficLightStateInterface
  {
    return new GreenLight();
  }
}

class GreenLight implements TrafficLightStateInterface
{
  public function name(): string
  {
    return "Green";
  }

  public function next(): TrafficLightStateInterface
  {
    return new YellowLight();
  }
}

class YellowLight implements TrafficLightStateInterface
{
  public function name(): string
  {
    return "Yellow";
  }

  public function next(): TrafficLightStateInterface
  {
    return new RedLight();
  }
}

class TrafficLight {
  private TrafficLightStateInterface $state;

  public function __construct(TrafficLightStateInterface $state)
  {
    $this->state = $state;
  }

  public function name(): string
  {
    return $this->state->name();
  }

  public function next(): void
  {
    $this->state = $this->state->next();
  }
}

$light = new TrafficLight(new RedLight());

for ($i = 0; $i < 4; $i++) {
  echo $light->name() . "\n";
  $light->next();
}

// Output:
// Red
// Green
// Yellow
// Red

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

// TrafficLightState interface
type TrafficLightState interface {
	Name() string
	Next() TrafficLightState
}

// RedLight struct
type RedLight struct{}

func (r *RedLight) Name() string {
	return "Red"
}

func (r *RedLight) Next() TrafficLightState {
	return &GreenLight{}
}

// GreenLight struct
type GreenLight struct{}

func (g *GreenLight) Name() string {
	return "Green"
}

func (g *GreenLight) Next() TrafficLightState {
	return &YellowLight{}
}

// YellowLight struct
type YellowLight struct{}

func (y *YellowLight) Name() string {
	return "Yellow"
}

func (y *YellowLight) Next() TrafficLightState {
	return &RedLight{}
}

// TrafficLight holds the current state
type TrafficLight struct {
	state TrafficLightState
}

// NewTrafficLight constructor
func NewTrafficLight(state TrafficLightState) *TrafficLight {
	return &TrafficLight{state: state}
}

// Name delegates to the current state
func (t *TrafficLight) Name() string {
	return t.state.Name()
}

// Next asks the current state for the next one
func (t *TrafficLight) Next() {
	t.state = t.state.Next()
}

func main() {
	light := NewTrafficLight(&RedLight{})
	for i := 0; i < 4; i++ {
		fmt.Println(light.Name())
		light.Next()
	}
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface TrafficLightState {
    String name();
    TrafficLightState next();
}

class RedLight implements TrafficLightState {
    public String name() {
        return "Red";
    }

    public TrafficLightState next() {
        return new GreenLight();
    }
}

class GreenLight implements TrafficLightState {
    public String name() {
        return "Green";
    }

    public TrafficLightState next() {
        return new YellowLight();
    }
}

class YellowLight implements TrafficLightState {
    public String name() {
        return "Yellow";
    }

    public TrafficLightState next() {
        return new RedLight();
    }
}

class TrafficLight {
    private TrafficLightState state;

    public TrafficLight(TrafficLightState state) {
        this.state = state;
    }

    public String name() {
        return state.name();
    }

    public void next() {
        state = state.next();
    }
}

// ----------------------------

TrafficLight light = new TrafficLight(new RedLight());

for (int i = 0; i < 4; i++) {
    System.out.println(light.name());
    light.next();
}

// Output:
// Red
// Green
// Yellow
// Red
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <memory>
#include <string>

class TrafficLightState {
public:
    virtual ~TrafficLightState() = default;
    virtual std::string name() const = 0;
    virtual std::unique_ptr<TrafficLightState> next() const = 0;
};

class GreenLight;
class YellowLight;

class RedLight : public TrafficLightState {
public:
    std::string name() const override { return "Red"; }
    std::unique_ptr<TrafficLightState> next() const override;
};

class GreenLight : public TrafficLightState {
public:
    std::string name() const override { return "Green"; }
    std::unique_ptr<TrafficLightState> next() const override;
};

class YellowLight : public TrafficLightState {
public:
    std::string name() const override { return "Yellow"; }
    std::unique_ptr<TrafficLightState> next() const override;
};

std::unique_ptr<TrafficLightState> RedLight::next() const {
    return std::make_unique<GreenLight>();
}

std::unique_ptr<TrafficLightState> GreenLight::next() const {
    return std::make_unique<YellowLight>();
}

std::unique_ptr<TrafficLightState> YellowLight::next() const {
    return std::make_unique<RedLight>();
}

class TrafficLight {
private:
    std::unique_ptr<TrafficLightState> state;

public:
    explicit TrafficLight(std::unique_ptr<TrafficLightState> initial)
        : state(std::move(initial)) {}

    std::string name() const { return state->name(); }

    void next() { state = state->next(); }
};

// ----------------------------

int main() {
    TrafficLight light(std::make_unique<RedLight>());
    for (int i = 0; i < 4; ++i) {
        std::cout << light.name() << std::endl;
        light.next();
    }
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
interface TrafficLightState {
    fun name(): String
    fun next(): TrafficLightState
}

class RedLight : TrafficLightState {
    override fun name() = "Red"
    override fun next(): TrafficLightState = GreenLight()
}

class GreenLight : TrafficLightState {
    override fun name() = "Green"
    override fun next(): TrafficLightState = YellowLight()
}

class YellowLight : TrafficLightState {
    override fun name() = "Yellow"
    override fun next(): TrafficLightState = RedLight()
}

class TrafficLight(private var state: TrafficLightState) {
    fun name() = state.name()

    fun next() {
        state = state.next()
    }
}

// ----------------------------

fun main() {
    val light = TrafficLight(RedLight())
    for (i in 0 until 4) {
        println(light.name())
        light.next()
    }
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class TrafficLightState {
  String name();
  TrafficLightState next();
}

class RedLight implements TrafficLightState {
  @override
  String name() => 'Red';

  @override
  TrafficLightState next() => GreenLight();
}

class GreenLight implements TrafficLightState {
  @override
  String name() => 'Green';

  @override
  TrafficLightState next() => YellowLight();
}

class YellowLight implements TrafficLightState {
  @override
  String name() => 'Yellow';

  @override
  TrafficLightState next() => RedLight();
}

class TrafficLight {
  TrafficLightState _state;

  TrafficLight(this._state);

  String name() => _state.name();

  void next() {
    _state = _state.next();
  }
}

// ----------------------------

void main() {
  var light = TrafficLight(RedLight());
  for (var i = 0; i < 4; i++) {
    print(light.name());
    light.next();
  }
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی رفتار یه شیء به یه «حالت» داخلی بستگی داره و خود حالت‌ها هم با شرط مشخص از یکی به اون یکی گذار می‌کنن، مثل چراغ راهنمایی یا چرخه سفارش»؛ ❌ «وقتی فقط می‌خوای یه رفتار رو از بیرون عوض کنی و خبری از گذار خودکار بین حالت‌ها نیست».
> 🪤 **دام رایج:** «اگه گذار بین حالت‌ها رو از بیرون با `setState` دستی انجام بدی، عملاً به استراتژی (Strategy) رسیدی؛ جذابیت State اینه که خود حالت، حالت بعدی رو انتخاب کنه».
> 🔗 **فرقش با [استراتژی (Strategy)](#استراتژی-strategy-):** «توی Strategy تو از بیرون الگوریتم رو دستی می‌چینی؛ توی State خود شیء با عوض شدن حالتش، رفتارش رو خودکار عوض می‌کنه».


<br>

---

<div align="center">

## متد قالب (Template Method) 📒

</div>

<div align="center">
🏗️ <b>مثال دنیای واقعی: خط تولید با مراحل ثابت</b>
</div>

فرض کن توی یک کارخونه/خط تولید، یه کار همیشه با همین ترتیب جلو می‌ره:
۱. اول تست
۲. بعد بررسی کیفیت
۳. بعد بسته‌بندی
۴. آخرش ارسال

ترتیبش ثابت و غیرقابل چونه‌زدنه. ولی بعضی مرحله‌ها بسته به محصول فرق می‌کنه.
مثلاً «تست کردن محصول A» با «تست کردن محصول B» یکی نیست، ولی هر دو باید توی همون جای مشخص از روند اجرا بشن.

💡 **به زبون ساده:**
> این پترن می‌گه: **«اسکلت الگوریتم ثابته؛ فقط بعضی قدم‌هاش رو فرزندها پر می‌کنن یا عوض می‌کنن.»**

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, the template method pattern is a behavioral design pattern that defines the program skeleton
> of an algorithm in an operation, deferring some steps to subclasses. It lets one redefine certain steps of an
> algorithm
> without changing the algorithm's structure.

</div>

خلاصه‌اش این می‌شه که اسکلت اصلیِ الگوریتم رو کلاس والد می‌چینه و ترتیب قدم‌ها رو مشخص می‌کنه.
بعد چند تا از این قدم‌ها رو توی کلاس‌های فرزند یه‌جور دیگه می‌نویسی، بدون اینکه به ساختار کلی دست بزنی.

**مثال برنامه‌نویسی**

حالا همون خط تولید رو ببر توی نرم‌افزار: می‌خوایم یه زیرساخت برای ساختِ اپلیکیشن‌های گوشی بسازیم که روند ساختش (build) همیشه ثابته.

متدِ `build` ترتیب کارها رو نگه می‌داره و خودش قدم‌های `test`، `lint`، `assemble` و `deploy` رو پشت‌سرهم صدا می‌زنه؛ ما فقط همین چهار قدم رو برای هر پلتفرم جور دیگه پیاده‌سازی می‌کنیم.

بعد باید پیاده‌سازی برای اندروید و iOS رو بسازیم.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Builder:
    def build(self):
        self.test()
        self.lint()
        self.assemble()
        self.deploy()

    def test(self):
        pass

    def lint(self):
        pass

    def assemble(self):
        pass

    def deploy(self):
        pass


class AndroidBuilder(Builder):
    def test(self):
        print('Running android tests')

    def lint(self):
        print('Linting the android code')

    def assemble(self):
        print('Assembling the android build')

    def deploy(self):
        print('Deploying android build to server')


class IosBuilder(Builder):
    def test(self):
        print('Running ios tests')

    def lint(self):
        print('Linting the ios code')

    def assemble(self):
        print('Assembling the ios build')

    def deploy(self):
        print('Deploying ios build to server')


# ----------------------------

androidBuilder = AndroidBuilder()
androidBuilder.build()

# Output:
# Running android tests
# Linting the android code
# Assembling the android build
# Deploying android build to server


iosBuilder = IosBuilder()
iosBuilder.build()

# Output:
# Running ios tests
# Linting the ios code
# Assembling the ios build
# Deploying ios build to server
```

</div>

</details>

<details>
<summary>TypeScript</summary>
<div dir="ltr">

```typescript
class Builder {
    build(): void {
        this.test();
        this.lint();
        this.assemble();
        this.deploy();
    }

    test(): void {
    }

    lint(): void {
    }

    assemble(): void {
    }

    deploy(): void {
    }
}

class AndroidBuilder extends Builder {
    test(): void {
        console.log("Running android tests");
    }

    lint(): void {
        console.log("Linting the android code");
    }

    assemble(): void {
        console.log("Assembling the android build");
    }

    deploy(): void {
        console.log("Deploying android build to server");
    }
}

class IosBuilder extends Builder {
    test(): void {
        console.log("Running ios tests");
    }

    lint(): void {
        console.log("Linting the ios code");
    }

    assemble(): void {
        console.log("Assembling the ios build");
    }

    deploy(): void {
        console.log("Deploying ios build to server");
    }
}

// ----------------------------

const androidBuilder = new AndroidBuilder();
androidBuilder.build();

// Output:
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

const iosBuilder = new IosBuilder();
iosBuilder.build();

// Output:
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class Builder {
    build() {
        this.test();
        this.lint();
        this.assemble();
        this.deploy();
    }

    test() {

    }

    lint() {

    }

    assemble() {

    }

    deploy() {

    }
}

class AndroidBuilder extends Builder {
    test() {
        console.log("Running android tests");
    }

    lint() {
        console.log("Linting the android code");
    }

    assemble() {
        console.log("Assembling the android build");
    }

    deploy() {
        console.log("Deploying android build to server");
    }
}

class IosBuilder extends Builder {
    test() {
        console.log("Running ios tests");
    }

    lint() {
        console.log("Linting the ios code");
    }

    assemble() {
        console.log("Assembling the ios build");
    }

    deploy() {
        console.log("Deploying ios build to server");
    }
}


const androidBuilder = new AndroidBuilder();
androidBuilder.build();

// Output:
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

const iosBuilder = new IosBuilder();
iosBuilder.build();

// Output:
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp
using System;


abstract class Builder
{
    // Template method
    public void Build()
    {
      Test();
      Lint();
      Assemble();
      Deploy();
    }

    abstract public void Test();
    abstract public void Lint();
    abstract public void Assemble();
    abstract public void Deploy();
}



class AndroidBuilder : Builder
{
  public override void Assemble()
  {
    Console.WriteLine("Assembling the android build");
  }

  public override void Deploy()
  {
    Console.WriteLine("Deploying android build to server");
  }

  public override void Lint()
  {
    Console.WriteLine("Linting the android code");
  }

  public override void Test()
  {
    Console.WriteLine("Running android tests");
  }
}


class IosBuilder : Builder
{
  public override void Assemble()
  {
    Console.WriteLine("Assembling the ios build");
  }

  public override void Deploy()
  {
    Console.WriteLine("Deploying ios build to server");
  }

  public override void Lint()
  {
    Console.WriteLine("Linting the ios code");
  }

  public override void Test()
  {
    Console.WriteLine("Running ios tests");
  }
}


// ----------------------------

var androidBuilder = new AndroidBuilder();
androidBuilder.Build();

// Output:
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

var iosBuilder = new IosBuilder();
iosBuilder.Build();

// Output:
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
abstract class Builder {
  // Template method
  public function Build() {
    $this->test();
    $this->lint();
    $this->assemble();
    $this->deploy();
  }

  abstract public function test();
  abstract public function lint();
  abstract public function assemble();
  abstract public function deploy();
}

class AndroidBuilder extends Builder {
  public function assemble() {
    echo "Assembling the android build\n";
  }

  public function deploy() {
    echo "Deploying android build to server\n";
  }

  public function lint() {
    echo "Linting the android code\n";
  }

  public function test() {
    echo "Running android tests\n";
  }
}

class IosBuilder extends Builder {
  public function assemble() {
    echo "Assembling the ios build\n";
  }

  public function deploy() {
    echo "Deploying ios build to server\n";
  }

  public function lint() {
    echo "Linting the ios code\n";
  }

  public function test() {
    echo "Running ios tests\n";
  }
}

$androidBuilder = new AndroidBuilder();
$androidBuilder->build();

// Output:
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

$iosBuilder = new IosBuilder();
$iosBuilder->build();

// Output:
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server

```

</div>

</details>

<details>
  <summary>Go</summary>

<div dir="ltr">

```go
package main

import (
	"fmt"
)

// Builder interface
type Builder interface {
	Test()
	Lint()
	Assemble()
	Deploy()
}

// BaseBuilder provides default implementations
type BaseBuilder struct{
    self Builder
}
func (b *BaseBuilder) init(self Builder) {
	b.self = self
}

// Build for BaseBuilder
func (b *BaseBuilder) Build() {
	b.self.Test()
	b.self.Lint()
	b.self.Assemble()
	b.self.Deploy()
}


// AndroidBuilder struct
type AndroidBuilder struct {
	BaseBuilder
}

func NewAndroidBuilder() *AndroidBuilder {
	a := &AndroidBuilder{}
	a.init(a)
	return a
}

// Test for AndroidBuilder
func (a *AndroidBuilder) Test() {
	fmt.Println("Running android tests")
}

// Lint for AndroidBuilder
func (a *AndroidBuilder) Lint() {
	fmt.Println("Linting the android code")
}

// Assemble for AndroidBuilder
func (a *AndroidBuilder) Assemble() {
	fmt.Println("Assembling the android build")
}

// Deploy for AndroidBuilder
func (a *AndroidBuilder) Deploy() {
	fmt.Println("Deploying android build to server")
}

// IosBuilder struct
type IosBuilder struct {
	BaseBuilder
}
func NewIosBuilder() *IosBuilder {
	i := &IosBuilder{}
	i.init(i)
	return i
}
// Test for IosBuilder
func (i *IosBuilder) Test() {
	fmt.Println("Running ios tests")
}

// Lint for IosBuilder
func (i *IosBuilder) Lint() {
	fmt.Println("Linting the ios code")
}

// Assemble for IosBuilder
func (i *IosBuilder) Assemble() {
	fmt.Println("Assembling the ios build")
}

// Deploy for IosBuilder
func (i *IosBuilder) Deploy() {
	fmt.Println("Deploying ios build to server")
}

func main() {
	NewAndroidBuilder().Build()
	NewIosBuilder().Build()
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
abstract class Builder {
    // Template method
    public void build() {
        test();
        lint();
        assemble();
        deploy();
    }

    abstract public void test();
    abstract public void lint();
    abstract public void assemble();
    abstract public void deploy();
}

class AndroidBuilder extends Builder {

    @Override
    public void test() {
        System.out.println("Running android tests");
    }

    @Override
    public void lint() {
        System.out.println("Linting the android code");
    }

    @Override
    public void assemble() {
        System.out.println("Assembling the android build");
    }

    @Override
    public void deploy() {
        System.out.println("Deploying android build to server");
    }
}

class IosBuilder extends Builder {

    @Override
    public void test() {
        System.out.println("Running ios tests");
    }

    @Override
    public void lint() {
        System.out.println("Linting the ios code");
    }

    @Override
    public void assemble() {
        System.out.println("Assembling the ios build");
    }

    @Override
    public void deploy() {
        System.out.println("Deploying ios build to server");
    }
}

// ----------------------------

AndroidBuilder androidBuilder = new AndroidBuilder();
androidBuilder.build();
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

IosBuilder iosBuilder = new IosBuilder();
iosBuilder.build();
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>

class Builder {
public:
    virtual ~Builder() = default;
    
    // Template method
    void build() {
        test();
        lint();
        assemble();
        deploy();
    }

    virtual void test() = 0;
    virtual void lint() = 0;
    virtual void assemble() = 0;
    virtual void deploy() = 0;
};

class AndroidBuilder : public Builder {
public:
    void test() override {
        std::cout << "Running android tests" << std::endl;
    }

    void lint() override {
        std::cout << "Linting the android code" << std::endl;
    }

    void assemble() override {
        std::cout << "Assembling the android build" << std::endl;
    }

    void deploy() override {
        std::cout << "Deploying android build to server" << std::endl;
    }
};

class IosBuilder : public Builder {
public:
    void test() override {
        std::cout << "Running ios tests" << std::endl;
    }

    void lint() override {
        std::cout << "Linting the ios code" << std::endl;
    }

    void assemble() override {
        std::cout << "Assembling the ios build" << std::endl;
    }

    void deploy() override {
        std::cout << "Deploying ios build to server" << std::endl;
    }
};

// ----------------------------

int main() {
    AndroidBuilder androidBuilder;
    androidBuilder.build();
    // Running android tests
    // Linting the android code
    // Assembling the android build
    // Deploying android build to server

    IosBuilder iosBuilder;
    iosBuilder.build();
    // Running ios tests
    // Linting the ios code
    // Assembling the ios build
    // Deploying ios build to server
    return 0;
}
```

</div>

</details>

<details>
<summary>Kotlin</summary>

<div dir="ltr">

```kotlin
abstract class Builder {
    // Template method
    fun build() {
        test()
        lint()
        assemble()
        deploy()
    }

    abstract fun test()
    abstract fun lint()
    abstract fun assemble()
    abstract fun deploy()
}

class AndroidBuilder : Builder() {
    override fun test() {
        println("Running android tests")
    }

    override fun lint() {
        println("Linting the android code")
    }

    override fun assemble() {
        println("Assembling the android build")
    }

    override fun deploy() {
        println("Deploying android build to server")
    }
}

class IosBuilder : Builder() {
    override fun test() {
        println("Running ios tests")
    }

    override fun lint() {
        println("Linting the ios code")
    }

    override fun assemble() {
        println("Assembling the ios build")
    }

    override fun deploy() {
        println("Deploying ios build to server")
    }
}

// ----------------------------

fun main() {
    val androidBuilder = AndroidBuilder()
    androidBuilder.build()

    val iosBuilder = IosBuilder()
    iosBuilder.build()
}
```

</div>
</details>

<details>
<summary>Dart</summary>

<div dir="ltr">

```dart
abstract class Builder {
  // Template method
  void build() {
    test();
    lint();
    assemble();
    deploy();
  }

  void test();
  void lint();
  void assemble();
  void deploy();
}

class AndroidBuilder extends Builder {
  @override
  void test() => print('Running android tests');

  @override
  void lint() => print('Linting the android code');

  @override
  void assemble() => print('Assembling the android build');

  @override
  void deploy() => print('Deploying android build to server');
}

class IosBuilder extends Builder {
  @override
  void test() => print('Running ios tests');

  @override
  void lint() => print('Linting the ios code');

  @override
  void assemble() => print('Assembling the ios build');

  @override
  void deploy() => print('Deploying ios build to server');
}

// ----------------------------

void main() {
  var androidBuilder = AndroidBuilder();
  androidBuilder.build();

  var iosBuilder = IosBuilder();
  iosBuilder.build();
}
```

</div>
</details>

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی چند تا کار، ترتیب و اسکلت یکسانی دارن و فقط چند قدمشون فرق می‌کنه»؛ ❌ «وقتی کل روند کار از این‌رو به اون‌رو فرق می‌کنه و قدم مشترکی بینشون نیست».
> 🪤 **دام رایج:** «این‌قدر قدم‌ها رو قابل‌بازنویسی می‌کنی که دیگه اسکلت ثابتی نمی‌مونه و کنترل از دستت در می‌ره».
> 🔗 **فرقش با [استراتژی (Strategy)](#استراتژی-strategy-):** «اینجا با ارث‌بری فقط چند قدمِ یه روندِ ثابت رو عوض می‌کنی؛ توی استراتژی کلِ الگوریتم رو به‌صورت یه شیء جدا تزریق و تعویض می‌کنی».


<br>

---

<br>

<div align="center">

# کمک کردن به این پروژه! 🤝

</div>

<div align="right">

- این پروژه رو fork کنی و به زبون‌های برنامه‌نویسی دیگه توسعه بدی!
- این ریپو رو برای دوستات بفرستی!
- اشتباهاتی که وجود داره رو با issue و یا pull request فیکس کنی!
- مثال‌ها رو بهتر کنی و با issue یا pull request به اشتراک بذاری.
- اگه تجربه عملی‌ای با هر الگو داری، اون رو به مثال‌ها اضافه کن.
- با یه ⭐ از من و این ریپو حمایت کنی و کمک کنی بیشتر دیده بشه!

</div>

<div align="center">

## مشارکت‌کنندگان

</div>

<div align="right">

- امیر عزیز که زحمت مثال‌های TypeScript رو کشید. ([amirmalekian](https://github.com/amirmalekian))
- رضا عزیز که زحمت مثال‌های C# رو کشید. ([RezaMansouri70](https://github.com/RezaMansouri70))
- صالح عزیز که زحمت مثال‌های PHP رو کشید. ([salehhashemi1992](https://github.com/salehhashemi1992))
- عاطفه عزیز که زحمت مثال‌های Golang رو کشید. ([atefeh-komeyli](https://github.com/atefeh-komeyli))
- محمد عزیز که زحمت مثال‌های Java رو کشید. ([Mohammad-Masoomi-Homayoun](https://github.com/Mohammad-Masoomi-Homayoun))
- سما عزیز که زحمت مثال‌های JavaScript رو کشید. ([samazzz](https://github.com/samazzz))
- حمیدرضا عزیز که زحمت مثال‌های C++ رو کشید. ([hamiikalhor](https://github.com/hamiikalhor))
- آریا عزیز که زحمت مثال‌های Kotlin رو کشید. ([ariaramin](https://github.com/ariaramin))
- مجید عزیز که زحمت مثال‌های Dart رو کشید. ([majidrigizadeh](https://github.com/majidrigizadeh))
- مهسا، محمد، سجاد و محسن عزیز که زحمت بهبود کدها رو کشیدند. ([MahsaMahdavian](https://github.com/MahsaMahdavian) / [MohammadMMoniri](https://github.com/MohammadMMoniri) / [ssmns](https://github.com/ssmns) / [Serajian](https://github.com/Serajian))

</div>

</div>
