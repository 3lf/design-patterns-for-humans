<div dir="rtl">

![Design Patterns For Humans](images/poster.png)

---

<h3 dir="rtl" align="center">
🎉 توضیح ساده دیزاین پترن‌ها ! 🎉
</h3>

<p dir="rtl" align="center">
فهمیدن دیزاین پترن‌ها از اون موضوع‌هاست که ذهن رو به چالش می‌کشه.
 اینجا سعی می‌کنم با مثال‌های ساده از دنیای واقعی و دنیای کد ، اونو راحت وارد ذهنت کنم.
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
| 🧱 **اصول SOLID** | [🧱 اصول SOLID (SOLID Principles)](#اصول-solid-solid-principles-)<br>[تک‌وظیفگی (SRP)](#۱-اصل-تک‌وظیفگی-single-responsibility-principle---srp-)<br>[باز/بسته (OCP)](#۲-اصل-بازبسته-openclosed-principle---ocp-)<br>[جایگزینی لیسکوف (LSP)](#۳-اصل-جایگزینی-لیسکوف-liskov-substitution-principle---lsp-)<br>[جداسازی اینترفیس (ISP)](#۴-اصل-جداسازی-اینترفیس-interface-segregation-principle---isp-)<br>[وارونگی وابستگی (DIP)](#۵-اصل-وارونگی-وابستگی-dependency-inversion-principle---dip-) |
| 🏗️ **سازنده (Creational)** | [🏠 کارخانه ساده (Simple Factory)](#کارخانه-ساده-simple-factory-)<br>[🏭 متد کارخانه (Factory Method)](#متد-کارخانه-factory-method-)<br>[🔨 کارخانه انتزاعی (Abstract Factory)](#کارخانه-انتزاعی-abstract-factory-)<br>[👷 سازنده (Builder)](#سازنده-builder-)<br>[🐑 نمونه اولیه (Prototype)](#نمونه-اولیه-prototype-)<br>[💍 تک‌نمونه (Singleton)](#تک‌نمونه-singleton-) |
| 🧩 **ساختاری (Structural)** | [🔌 مبدل (Adapter)](#مبدل-adapter-)<br>[🌉 پل (Bridge)](#پل-bridge-)<br>[🌿 مرکب (Composite)](#مرکب-composite-)<br>[☕ تزئین‌گر (Decorator)](#تزئین‌گر-decorator-)<br>[📦 نما (Facade)](#نما-facade-)<br>[🍃 وزن‌سبک (Flyweight)](#وزن‌سبک-flyweight-)<br>[🎱 پراکسی (Proxy)](#پراکسی-proxy-) |
| 🎭 **رفتاری (Behavioral)** | [🔗 زنجیره مسئولیت (Chain of Responsibility)](#زنجیره-مسئولیت-chain-of-responsibility-)<br>[👮 فرمان (Command)](#فرمان-command-)<br>[➿ پیمایش‌گر (Iterator)](#پیمایش‌گر-iterator-)<br>[👽 میانجی (Mediator)](#میانجی-mediator-)<br>[💾 یادبود (Memento)](#یادبود-memento-)<br>[😎 ناظر (Observer)](#ناظر-observer-)<br>[🏃 بازدیدکننده (Visitor)](#بازدیدکننده-visitor-)<br>[💡 استراتژی (Strategy)](#استراتژی-strategy-)<br>[💢 حالت (State)](#حالت-state-)<br>[📒 متد قالب (Template Method)](#متد-قالب-template-method-) |

</details>

<!-- TOC -->

</div>

---

<div dir="rtl" align="center">

# مقدمه 🚀

</div>

<div dir="rtl">

دیزاین پترن‌ها یک سری دستور العمل برای مقابله با یک سری مشکلات رایج هستند.

اونا یک سری کلاس، پکیج یا کتابخونه نیستند که با اضافه کردنشون به پروژه‌ت جادو کنن. در عوض یک سری راه حل بهت می‌دن که
در شرایط خاص به مشکل نخوری.

<br>

> پس دیزاین پترن‌ها راه حلی برای مشکلات رایج هستن.

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

## هشدار ⚠

</div>

- الگوهای طراحی برای همه مشکلات راه‌حل ندارن.
- سعی نکن حتماً توی پروژه‌هات از اونا استفاده کنی؛ یادت باشه دیزاین پترن‌ها راه‌حلی برای مشکلاتن، نه راهی برای پیدا کردن مشکل. پس خیلی درگیرِ پیدا کردن دلیل برای استفاده ازشون نشو.
- اگه سرِ جای درست از اونا استفاده کنی، پروژه رو از مشکلات نجات می‌دی؛ در غیر این صورت قراره فاجعه به بار بیاد.

<br>
<br>

---

<div align="center">

## اصول SOLID (SOLID Principles) 🧱

</div>

<div dir="rtl">

قبل از اینکه بریم سراغ دیزاین پترن‌ها، باید الفبای کدنویسی تمیز رو یاد بگیریم. این ۵ تا اصل (SOLID) بهت کمک می‌کنن کدی بنویسی که راحت تغییر کنه و مثل ماکارونی درهم‌پیچیده نشه! 🍝

### ۱. اصل تک‌وظیفگی (Single Responsibility Principle - SRP) 🧙‍♂️
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

### ۲. اصل باز/بسته (Open/Closed Principle - OCP) 🚪
> **قانون طلایی:** نرم‌افزار باید برای **توسعه باز** (Open)، اما برای **تغییر بسته** (Closed) باشه.

<div align="center">
🎮 <b>مثال دنیای واقعی: کنسول بازی</b>
</div>

تو یک پلی‌استیشن داری. وقتی بازی جدیدی (مثل GTA VI) میاد، لازم نیست کل دستگاه رو باز کنی و سیم‌کشی‌شو عوض کنی تا بازی جدید رو بخونه!
کنسول **بسته** است (سخت‌افزارش ثابت می‌مونه) اما برای **توسعه** بازه (فقط دیسک بازی جدید رو می‌ذاری توش).

💻 **توی کد یعنی چی؟**
اگه فردا مشتری گفت «حالا می‌خوام پرداخت با بیت‌کوین هم داشته باشیم»، نباید برید توی کلاس `PaymentService` و کد `if (type == 'bitcoin')` اضافه کنی (این یعنی تغییر کد قبلی ❌).
باید طوری کد زده باشی که فقط یه کلاس جدید `BitcoinPayment` بسازی و سیستم خودکار بشناستش (این یعنی توسعه ✅).

---

### ۳. اصل جایگزینی لیسکوف (Liskov Substitution Principle - LSP) 🧩
> **قانون طلایی:** کلاس فرزند باید بتونه جای کلاس پدر بشینه، بدون اینکه رفتار برنامه عوض بشه یا ارور بده.

<div align="center">
☕️ <b>مثال دنیای واقعی: دستگاه قهوه‌ساز</b>
</div>

فرض کن یه کلاس کلی داریم به اسم **«دستگاه قهوه‌ساز»** که یه دستور داره به اسم: `addMilk()` (شیر اضافه کن).
حالا میایم یه کلاس فرزند می‌سازیم به اسم **«دستگاه اسپرسوساز خالص»** (که فقط قهوه سیاه می‌ده و اصلاً مخزن شیر نداره).

اگه توی کد برنامه، هر جا که «دستگاه قهوه‌ساز» لازم داشتیم، بیایم این «اسپرسوساز» رو بذاریم، چی می‌شه؟
وقتی برنامه دستورِ `addMilk()` رو صدا بزنه، اسپرسوساز قاطی می‌کنه یا ارور می‌ده! 💥

چرا؟ چون این فرزند (اسپرسوساز) نتونست به عهد و پیمان پدرش (که قول داده بود شیر اضافه کنه) وفادار بمونه. پس **اصل جایگزینی** رو نقض کرده.

💻 **توی کد یعنی چی؟**
اگه یه کلاس `Bird` (پدر) داری که متد `fly()` داره، نباید کلاسی مثل `Penguin` (فرزند) بسازی که ازش ارث ببره ولی موقع پرواز ارور `I can't fly` بده!
چون هر جا تو کد از `Bird` استفاده کردی، باید بتونی `Penguin` هم بذاری. اگه پنگوئن پرواز نمی‌کنه، پس نباید از `Bird` (که پرواز می‌کنه) ارث ببره.

---

### ۴. اصل جداسازی اینترفیس (Interface Segregation Principle - ISP) ✂️
> **قانون طلایی:** نباید کلاس‌ها رو مجبور کنیم متد‌هایی رو پیاده‌سازی کنن که بهشون نیاز ندارن.

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

### ۵. اصل وارونگی وابستگی (Dependency Inversion Principle - DIP) 🔌
> **قانون طلایی:** به چیزهای واقعی و ملموس (Concrete) وابسته نباش، به مفاهیم کلی (Abstractions) وابسته باش.

<div align="center">
🔌 <b>مثال دنیای واقعی: دوشاخه و پریز برق</b>
</div>

لامپ اتاق تو که مستقیم به سیم‌های توی دیوار لحیم نشده، شده؟ معلومه که نه!
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

> الگوهای طراحی سازنده، به مشکلات مربوط به ساخت آبجکت‌ها می‌پردازن.

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, creational design patterns are design patterns that deal with object creation mechanisms,
> trying to create objects in a manner

</div>

<br>

---

<div align="center">

## کارخانه ساده (Simple Factory) 🏠

</div>

<div align="center">
🚪 <b>مثال دنیای واقعی: کارگاه نجاری</b>
</div>

فرض کن داری یه خونه می‌سازی. برای هر اتاقی یه در لازم داری.
آیا منطقیه که برای هر در، خودت اره و تیشه برداری و شروع کنی به بریدن چوب؟ 🪚 نه! اینطوری که تو گل می‌مونی.

راه حل چیه؟ زنگ می‌زنی به «کارگاه نجاری» (Factory) و می‌گید: «آقا یه در چوبی با عرض ۹۰ و ارتفاع ۲۱۰ می‌خوام».
دیگه برات مهم نیست نجار چجوری چوب رو می‌بره یا از چه چسبی استفاده می‌کنه. تو فقط محصول نهایی رو تحویل می‌گیری.

💡 **به زبون ساده:**
> این پترن می‌گه: **«بی‌خیالِ `new` کردنِ مستقیم شو! ساختن آبجکت رو بسپار به یه متد مخصوص.»**
> اینطوری کدت تمیز می‌مونه و اگه فردا خواستی روش ساخت در رو عوض کنی، فقط همون کارگاه رو تغییر می‌دید، نه کل خونه رو.

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
<summary>Typescript</summary>

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

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی ساختن یه آبجکت چند خط مقدمه‌چینی داره و نمی‌خوای این شلوغی همه‌جای کدت پخش شه، بسپارش به یه متد کارخانه؛ ❌ اگه فقط یه `new` ساده‌ست، الکی پیچیده‌ش نکن.
> 🪤 **دام رایج:** کم‌کم همه‌چی رو می‌ریزی توی یه `makeDoor` غول‌پیکر پر از `if`/`else`؛ همون‌جاست که باید بری سراغ الگوهای جدی‌تر.
> 🔗 **فرقش با [متد کارخانه](#متد-کارخانه-factory-method-):** اینجا یه متد ساده‌ی (معمولاً static) خودش تصمیم می‌گیره چی بسازه؛ توی متد کارخانه، تصمیمِ ساخت رو به زیرکلاس‌ها واگذار می‌کنی.


<br>

---

<div align="center">

## متد کارخانه (Factory Method) 🏭

</div>

<div align="center">
👔 <b>مثال دنیای واقعی: مدیر استخدام</b>
</div>

فرض کن یه مدیر استخدام (`HiringManager`) داریم. فرآیند استخدام توی این شرکت یه قانون کلی داره:
۱. مصاحبه‌کننده رو انتخاب کن.
۲. ازش بخواه سوال بپرسه.

اما نکته اینجاست: مدیر استخدامِ کل، خودش نمی‌دونه برای هر پوزیشن چه سوالای تخصصی‌ای باید پرسیده بشه یا چه کسی صلاحیت داره. پس چی‌کار می‌کنه؟ ساختن «مصاحبه‌کننده» رو می‌سپاره به مدیرهای هر بخش.

*   اگه استخدام برای بخش **فنی** باشه، مدیر فنی (`DevelopmentManager`) میاد و یه **برنامه‌نویس** (`Developer`) رو می‌سازه تا سوالای فنی بپرسه.
*   اگه استخدام برای بخش **مارکتینگ** باشه، مدیر مارکتینگ (`MarketingManager`) میاد و یه **بازاریاب** (`CommunityExecutive`) رو می‌سازه.

پس «فرآیند کلی مصاحبه» ثابته، اما اینکه «کی قراره سوال بپرسه» (یا همون ساختن آبجکت مصاحبه‌کننده) رو می‌سپاریم به زیرکلاس‌ها.

💡 **به زبون ساده:**
> این پترن می‌گه: **«من (کلاس پدر) منطق کلی کار رو می‌دونم، اما ساختن ابزار دقیقش (آبجکت) رو می‌سپارم به بچه‌هام (کلاس‌های فرزند).»**

ویکی‌پدیا:

<div dir="ltr">

> In class-based programming, the factory method pattern is a creational pattern that uses factory methods to deal with
> the problem of creating objects without having to specify the exact class of the object that will be created. This is
> done by creating objects by calling a factory method—either specified in an interface and implemented by child
> classes,
> or implemented in a base class and optionally overridden by derived classes—rather than by calling a constructor.

</div>

خلاصه‌ش این می‌شه: به‌جای اینکه مستقیم با `new` یه آبجکت بسازی، یه متد مخصوص ساخت (همون متد کارخانه) صداش می‌زنی. این متد یا توی یه اینترفیس تعریف شده و فرزندها پیاده‌سازیش می‌کنن، یا توی کلاس پدر یه نسخه پیش‌فرض داره و فرزندها در صورت نیاز بازنویسیش می‌کنن. این‌جوری کدِ پدر لازم نیست بدونه دقیقاً داره کدوم کلاس رو می‌سازه.

**مثال برنامه‌نویسی**

بیا از مثال مدیر استخدام برای درک بهتر استفاده کنیم.

پس اول یک اینترفیس برای مصاحبه کننده‌ها می‌سازیم و چند پیاده‌سازی هم برای اون ایجاد می‌کنیم.

بعد از اون `HiringManager` رو پیاده‌سازی می‌کنیم

در نهایت هر فرزند می‌تونه ازش ارث بری کنه و متد `makeInterviewer` خودش رو داشته باشه:

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
<summary>Typescript</summary>

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
        echo "Asking about design patterns!";
    }
}

class CommunityExecutive implements InterviewerInterface
{
    public function askQuestions()
    {
        echo "Asking about community building";
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
// تنها چیزی که توی هر مدیر فرق می‌کنه، متد کارخانه‌ی makeInterviewer هست.
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

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی کلاس پدر منطق کلی کار رو می‌دونه ولی نوع دقیقِ آبجکتی که باید ساخته بشه به زیرکلاس بستگی داره، اون تصمیم رو می‌سپاری به فرزندها؛ ❌ ولی اگه فقط یه‌جا و بر اساس یه شرط ساده آبجکت می‌سازی، یه if کوچیک یا «کارخانه ساده» کافیه و این الگو زیادی‌ست.
> 🪤 **دام رایج:** برای یه حالتِ ساده کلی زیرکلاس می‌سازی و کد رو بی‌خودی شلوغ می‌کنی؛ این الگو وقتی می‌ارزه که واقعاً چند نوع سازنده داشته باشی.
> 🔗 **فرقش با [کارخانه ساده](#کارخانه-ساده-simple-factory-):** کارخانه ساده همه‌چی رو توی یه متد با شرط جمع می‌کنه، اما اینجا ساختِ آبجکت رو به ارث‌بری و زیرکلاس‌ها می‌سپاری، پس هر نوع جدید یعنی یه زیرکلاس جدید نه دست‌کاری متدِ موجود.


<br>

**چه موقع باید ازش استفاده کنیم؟**

اساساً زمانی ازین الگو استفاده می‌شه که چندین کلاس با ریشه مشترک داریم (یعنی چندین کلاس یک کلاس parent رو پیاده‌سازی
می‌کنند) و با توجه به شرایط تصمیم می‌گیریم از یکی از اون‌ها استفاده کنیم.

<br>

---

<div align="center">

## کارخانه انتزاعی (Abstract Factory) 🔨

</div>

<div align="center">
🛠 <b>مثال دنیای واقعی: سرویس کامل نصب در</b>
</div>

بیاید مثال قبلی رو کامل‌تر کنیم. فرض کن تو فقط «در» نمی‌خوای، بلکه «نصاب» هم می‌خوای.
نکته مهم اینه که اینا باید با هم **ست** باشن:
*   اگه در **چوبی** خریدی، باید **نجار** بیاد نصبش کنه.
*   اگه در **آهنی** خریدی، باید **جوشکار** بیاد.

فاجعه اونجاست که در چوبی بخری ولی جوشکار بیاد دم خونه! 🔥

اینجاست که **Abstract Factory** میاد وسط. ما به جای اینکه در و نصاب رو جدا جدا سفارش بدیم، زنگ می‌زنیم به «کارخونه محصولات چوبی». اونا هم در چوبی می‌دن، هم نجار رو می‌فرستن. اینطوری خیالمون راحته که همه چی با هم جوره.

💡 **به زبون ساده:**
> این پترن کارخونه‌ای از کارخونه‌هاست! یعنی یه کارخونه که بسته‌های کامل و هماهنگ (Products Family) رو تحویل می‌ده تا مبادا قطعات ناسازگار کنار هم قرار بگیرن.

ویکی‌پدیا:

<div dir="ltr">

> The abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme
> without specifying their concrete classes

</div>

یعنی الگوی کارخانه انتزاعی بهت یه راه می‌ده که یه گروه از کارخونه‌های هم‌خانواده رو زیر یه چتر جمع کنی؛ بدون اینکه کد مصرف‌کننده بدونه پشت پرده دقیقاً کدوم کلاس واقعی داره ساخته می‌شه. کارش اینه که خانواده‌ای از محصولات سازگار رو با هم بسازه، نه تک‌تک قطعه‌ها رو جدا.

<br>

**مثال برنامه‌نویسی**

خب همون مثال ساخت خونه و نیاز به درب‌های مختلف رو ترجمه می‌کنیم.

اول باید اینترفیس درب رو بسازیم و چند پیاده‌سازی ازش ایجاد کنیم.

در مرحله بعد برای هر درب متخصص مربوطه رو ایجاد می‌کنیم.

و در مرحله آخر سراغ پیاده‌سازی دیزاین پترن‌مون می‌ریم.

برای مثال کلاس `WoodenDoorFactory` زمانی استفاده می‌شه که نیاز به درب چوبی داریم و کارش اینه که برای ایجاد آبجکت درب (که
اینجا
درب چوبی هست) از کلاس `WoodenDoor` و برای ایجاد آبجکت متخصص (که اینجا نجار هست) از `Carpenter` استفاده کنه.

این موضوع برای درب آهنی و ... هم بطور مشابه پیاده‌سازی می‌شه.

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

**همونطور که می‌بیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

</details>

<details>
<summary>Typescript</summary>

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

**همونطور که می‌بیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

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

**همونطور که می‌بیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

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

**همونطور که می‌بیند، می‌تونیم به‌طور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

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

**همونطور که می‌بیند، می‌تونیم به‌طور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

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

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی محصولاتت یه **خانواده هماهنگ** می‌سازن و باید با هم ست بمونن (مثل در چوبی + نجار)، تا یه دفعه قطعه ناجور قاطی نشه؛ ❌ وقتی فقط یه نوع محصول داری یا قرار نیست چند خانواده کنار هم زندگی کنن.
> 🪤 **دام رایج:** خانواده‌ها رو زیادی ریز می‌کنی و کلی کلاس کارخونه می‌سازی که فقط یه محصول می‌ده؛ اونجا داری بی‌خودی پیچیده‌اش می‌کنی.
> 🔗 **فرقش با [متد کارخانه](#متد-کارخانه-factory-method-):** متد کارخانه یه محصول رو می‌سازه، ولی کارخانه انتزاعی یه **خانواده کامل از محصولات مرتبط** رو با هم تحویل می‌ده.


**همونطور که می‌بیند، می‌تونیم به‌طور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

<br>

**چه موقع باید ازش استفاده کنیم؟**

زمانی که وابستگی‌های منطقی نه چندان ساده برای ایجاد وجود داره، می‌تونیم ازین دیزاین پترن استفاده کنیم.

<br>

---

<div align="center">

## سازنده (Builder) 👷

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

برای همه ما پیش اومده که یک تابع سازنده ترسناک به این شکل ببینیم که آدم رو فراری می‌ده:


<details>
<summary>Python</summary>
<div dir="ltr">

```python
def __init__(self, size, cheese=True, mushrooms=True, tomato=False)
```

</div>
</details>

<details>
<summary>Typescript</summary>
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

در این شرایط معمولا Builder می‌تونه به دادمون برسه.

<br>

ویکی‌پدیا:

<div dir="ltr">

> The builder pattern is an object creation software design pattern with the intentions of finding a solution to the
> telescoping constructor anti-pattern.

</div>

خلاصه‌اش این می‌شه که الگوی Builder یه الگوی ساخت آبجکته که اومده تا جواب مشکل «تابع سازنده تلسکوپی (Telescoping Constructor)» رو بده؛ یعنی همون تابع سازنده‌ای که هی ورودی‌های اختیاری بهش اضافه می‌شه و قاطی‌پاتی می‌شه. به جاش، آبجکت رو قدم‌به‌قدم و خوانا می‌سازیم.

<br>

**مثال برنامه‌نویسی**

در این بخش هم می‌خوام مثال برگر رو برات ترجمه کنم.

اولین مرحله اینه که یک کلاس برگر معمولی داشته باشیم

در ادامه کلاس Builder رو براش ایجاد می‌کنیم.

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
<summary>Typescript</summary>
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

echo $burger->getDescription();
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی ساختن یه آبجکت کلی گزینه اختیاری داره و می‌خوای قدم‌به‌قدم و خوانا بسازیش»؛ ❌ «وقتی آبجکتت دو سه تا فیلد ساده داره و یه تابع سازنده معمولی کافیه».
> 🪤 **دام رایج:** «build() رو صدا نزنی و با خود Builder کار کنی، یا فیلدهای اجباری رو نگیری و آبجکت نصفه‌نیمه بسازی».
> 🔗 **فرقش با الگوهای دیگه:** «Builder یه آبجکت رو مرحله‌به‌مرحله می‌سازه، نه اینکه بین چند نوع آبجکت آماده انتخاب کنه».


<br>

**چه موقع باید ازش استفاده کنیم؟**

همونطور که قبل تر اشاره کردم این دیزاین پترن رو معمولا برای ساخت آبجکت‌های پیچیده یا آبجکت‌هایی که نیاز به شخصی سازی
زیادی دارن استفاده می‌کنیم.

<br>

---

<div align="center">

## نمونه اولیه (Prototype) 🐑

</div>

<div align="center">
🧬 <b>مثال دنیای واقعی: کپی گرفتن از یه سند آماده</b>
</div>

فرض کن یه فایل ورد داری که کلی روش وقت گذاشتی؛ حاشیه، فونت، استایل، همه چی تنظیم شده. حالا برای یه سند جدید، از صفر شروع نمی‌کنی. همون فایل رو **Copy/Paste** می‌کنی و فقط متنش رو عوض می‌کنی. این دقیقاً کاری‌ه که این پترن می‌کنه؛ به جای ساختن از صفر، از روی یه نمونه آماده یه **کپی** (Clone) می‌گیری.

توی دنیای کامپیوتر هم خیلی وقتا پیش میاد که ساختن یه آبجکت از صفر خیلی هزینه داره (مثلاً باید کلی دیتابیس رو کوئری بزنه تا ساخته بشه).
به جای اینکه هر دفعه این مسیر سخت رو بریم، میایم از روی یه نمونه آماده (Prototype) یه کپی می‌گیریم. مثل دستور **Copy/Paste**.

💡 **به زبون ساده:**
> این پترن می‌گه: **«به جای اینکه بگی `new` و همه چیز رو از اول بسازی، از روی یکی که داری یه `clone` بگیر.»**
> (مخصوصاً وقتی ساختن آبجکت خیلی زمان‌بر یا پیچیده باشه).

ویکی‌پدیا:

<div dir="ltr">

> The prototype pattern is a creational design pattern in software development. It is used when the type of objects to
> create is determined by a prototypical instance, which is cloned to produce new objects.

</div>

به زبون خودمون: پترن نمونه اولیه (Prototype) یه پترن سازنده (Creational) هست. وقتی به دردت می‌خوره که نوع آبجکتی که می‌خوای بسازی رو یه نمونه آماده مشخص می‌کنه؛ پس به جای ساختن از صفر، از روی همون نمونه یه کپی (Clone) می‌گیری و آبجکت جدیدت آماده‌ست.

**مثال برنامه‌نویسی**

فرض کن یه کلاس Person داریم که یه اسم داره و یه آبجکت تو در توی Address، که توش شهر طرف نگه‌داری می‌شه.

می‌خوایم دو جور کپی ازش بگیریم؛ یه کپی سطحی (Shallow Copy) و یه کپی عمیق (Deep Copy)، تا فرقشون رو زنده ببینی.

<details>
<summary>Python</summary>

پایتون magic method‌هایی برای این مساله در نظر گرفته که ماهم از همون دو تابع معروف copy و deep copy استفاده می‌کنیم:

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
<summary>Typescript</summary>
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

<?php

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
> دیزاین پترن Singleton یه جورایی «آنتی پترن» (ضد الگو) هم حساب می‌شه! چون مثل «متغیر عمومی» (Global Variable) عمل می‌کنه و اگه زیاده‌روی کنی، تست نوشتن و دیباگ کردن پروژه رو تبدیل به کابوس می‌کنه. پس با احتیاط مصرف کنی! 💊

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a
> class to one object. This is useful when exactly one object is needed to coordinate actions across the system.

</div>

خلاصه‌اش این می‌شه که الگوی تک‌نمونه (Singleton) ساختن آبجکت از یه کلاس رو به فقط یه دونه محدود می‌کنه. این وقتی به درد می‌خوره که دقیقاً یه آبجکت لازم داری تا کارهای کل سیستم رو هماهنگ کنه.

<br>

**مثال برنامه‌نویسی**

بطور کلی برای ساخت singleton باید تابع سازنده private بشه، cloning و متود‌های copy بسته بشن و تابع استاتیکی برای ساخت
آبجکت تعریف بشه.

ولی توی پایتون راه حل ساده تری وجود داره که اون استفاده از metaclass هاست:

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
این روش Thread Safe نیست. برای اطلاعات بیشتر سرچ کنی :)

</details>

<details>
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی واقعاً باید توی کل برنامه فقط یه نمونه از یه چیز وجود داشته باشه، مثل تنظیمات سراسری یا یه استخر کانکشن (Connection Pool)»؛ ❌ «وقتی فقط برای راحتیِ دسترسی می‌خوای همه‌جا بهش برسی، که اون‌وقت داری متغیر عمومی (Global Variable) می‌سازی».
> 🪤 **دام رایج:** «حالت مشترک و قابل‌تغییرِ تک‌نمونه، تست‌ها رو به هم وابسته می‌کنه و توی برنامه‌های چندنخی (Multithreaded) دردسر می‌سازه».


<br>
<br>

---

<br>

<div align="center">

# الگوهای ساختاری (Structural Design Patterns) 🧰

</div>

به زبون ساده:

> بطور کلی الگوهای طراحی ساختاری با روابط بین موجودیت‌ها و ترکیب کردن اونا کار دارن.

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, structural design patterns are design patterns that ease the design by identifying a simple
> way to realize relationships between entities.

</div>

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
اینجا چیکار می‌کنی؟ سیم شارژر رو می‌بری؟ دیوار رو خراب می‌کنی؟ نه!
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

برای حلش به این صورت می‌تونیم براش آداپتور تعریف کنیم:

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
در واقع مثال واقعی و قابل حس نیست ولی مفهوم رو به خوبی منتقل می‌کنه.

</details>

<details>
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یه کلاس کارِتو راه می‌اندازه ولی امضای متدهاش با چیزی که کدت انتظار داره جور نیست»؛ ❌ «وقتی خودت کنترل هر دو طرف رو داری و می‌تونی همون اول اینترفیس رو درست طراحی کنی».
> 🪤 **دام رایج:** «آداپتور رو کم‌کم پر از منطق اضافه می‌کنی تا جایی که از یه واسطه ساده تبدیل می‌شه به یه لایه‌ی شلوغ که فهمیدنش سخته».
> 🔗 **فرقش با [پل (Bridge)](#پل-bridge-):** «پل رو از اول طراحی می‌کنی تا انتزاع و پیاده‌سازی مستقل از هم رشد کنن؛ آداپتور بعد از ماجرا میاد که دو تا چیزِ ناسازگارِ موجود رو به هم برسونه. (نزدیک به [پراکسی (Proxy)](#پراکسی-proxy-) و [تزئین‌گر (Decorator)](#تزئین‌گر-decorator-) هم هست؛ ولی اون‌ها اینترفیس رو عوض نمی‌کنن)».


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

اگه از روش معمولی (ارث‌بری) برید، باید برای هر صفحه، ۳ تا حالت بسازی:
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

خلاصه‌اش این می‌شه: «انتزاع» (Abstraction) رو، یعنی همون چیزی که داری باهاش کار می‌کنی، از «پیاده‌سازی» (Implementation) جدا نگه دار؛ اونوقت هر کدوم می‌تونن مستقل از اون یکی تغییر کنن و رشد کنن، بدون اینکه به هم گره بخورن.

**مثال برنامه‌نویسی**

بیاید همون مثال سایت و قالب که بالاتر درموردش صحبت کردیم رو پیاده‌سازی کنیم.

در مرحله اول کلاس `WebPage` و پیاده‌سازی‌هایی از اون رو داریم.

برای قالب هم، باید کلاس و پیاده‌سازی‌های مختلفی بنویسیم:

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
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی دوتا بُعد مستقل داری که جدا جدا زیاد می‌شن، مثل صفحه × تم، و نمی‌خوای ضربشون کنی در هم»؛ ❌ «وقتی فقط یه بُعد داری یا حالت‌ها هیچ‌وقت قرار نیست زیاد بشن».
> 🪤 **دام رایج:** «از همون اول همه‌چی رو با پل می‌سازی و کد رو الکی پیچیده می‌کنی، در حالی که هنوز انفجار کلاس‌ها اتفاق نیفتاده».
> 🔗 **فرقش با [مبدل (Adapter)](#مبدل-adapter-):** «مبدل بعد از ساخته‌شدن کد، دوتا چیز ناسازگار رو به هم می‌چسبونه؛ پل از اول طراحی می‌شه تا دو بُعد جدا بمونن».


<br>

---

<div align="center">

## مرکب (Composite) 🌿

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
یعنی وقتی می‌گیم `GetPrice()`، خودش بره ته توش رو دراره و قیمت همه زیرمجموعه‌هاش رو جمع بزنه و برگردونه.

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

خلاصه‌اش این می‌شه که الگوی مرکب بهت اجازه می‌ده آبجکت‌ها رو توی یه ساختار درختی بچینی و بعد کل اون درخت رو درست مثل یه آبجکت تکی صدا بزنی.
فرقی نمی‌کنه طرفت یه «برگ» تنهاست یا یه «شاخه» پر از زیرمجموعه؛ با هردوشون عین هم رفتار می‌کنی و خود ساختار، ته‌توش رو در میاره.

**مثال برنامه‌نویسی**

بطور کلی توی دیزاین پترن composite ما دو مدل دیتا داریم:

یک: اینکه Composite که می‌تونه برای خودش زیرمجموعه داشته باشه. (هرچند خودش هم وظایفی داشته باشه)

دو: Leaf که در واقع زیر مجموعه نداره و فقط یک سری وظیفه داره.

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

<summary>Typescript</summary>

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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی داده‌هات یه ساختار درختی دارن (بخش‌ها و کل‌ها) و می‌خوای با تک‌آبجکت و گروه یه‌جور رفتار کنی»؛ ❌ «وقتی آبجکت‌هات سلسله‌مراتب ندارن و صاف کنار هم‌ان؛ اون‌جا مرکب فقط پیچیدگی الکی اضافه می‌کنه».
> 🪤 **دام رایج:** «این‌قدر هوس می‌کنی همه‌چی رو یکدست کنی که متدهای بی‌معنی مثل add روی «برگ» هم می‌ذاری و در زمان اجرا می‌ترکه».


<br>

---

<div align="center">

## تزئین‌گر (Decorator) ☕

</div>

<div align="center">
☕ <b>مثال دنیای واقعی: کافی‌شاپ</b>
</div>

فرض کن رفتی کافی‌شاپ و سفارش قهوه می‌دید.
اول یه «قهوه ساده» سفارش می‌دید. ☕
بعد می‌گید «شیر هم اضافه کن». 🥛 (الآن شد قهوه با شیر)
بعد می‌گید «خامه هم روش بریز». 🧁 (الآن شد قهوه با شیر و خامه)

آیا برای هر کدوم از این ترکیب‌ها باید یه کلاس جدید بسازیم؟
*   `SimpleCoffee`
*   `CoffeeWithMilk`
*   `CoffeeWithMilkAndWhip`
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

به زبون خودمون: الگوی تزئین‌گر می‌گه که می‌تونی بدون دست زدن به خود کلاس، رفتار و قابلیت‌های تازه رو به یه آبجکت مشخص اضافه کنی؛ اونم به‌صورت لایه‌لایه و حتی همون لحظه که برنامه داره اجرا می‌شه. اینطوری هر کلاس مسئول یه کار می‌مونه و آبجکت‌های دیگه از همون کلاس دست‌نخورده باقی می‌مونن.

**مثال برنامه‌نویسی**

برای مثال قهوه را در نظر بگیر. اول از همه ما یک قهوه ساده داریم که رابط قهوه را پیاده‌سازی می کند.

ما می‌خوایم کد رو توسعه‌پذیر کنیم تا در صورت نیاز، گزینه‌ها بتونند اون رو تغییر بدند.

پس بیاید چند دکوریتور براش بسازیم.

همونطور که می‌بینی خیلی ساده می‌تونیم هر آبجکت رو به عنوان ورودی تابع بعدی بدیم و اینطوری چندین مرحله افزودنی رو خیلی
راحت به آبجکتمون اضافه کردیم!

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
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی می‌خوای قابلیت‌ها رو لایه‌لایه و موقع اجرا به یه آبجکت اضافه کنی، بدون اینکه کلاسش رو دست بزنی»؛ ❌ «وقتی فقط یکی دو حالت ثابت داری و یه ساب‌کلاس ساده کافیه».
> 🪤 **دام رایج:** «وقتی ده‌ها لایه روی هم می‌پیچی، دنبال کردن مسیر و دیباگ کردنش سخت و گیج‌کننده می‌شه».
> 🔗 **فرقش با [پراکسی (Proxy)](#پراکسی-proxy-):** «تزئین‌گر قابلیت تازه به آبجکت اضافه می‌کنه؛ پراکسی همون رفتار رو نگه می‌داره ولی دسترسی بهش رو کنترل می‌کنه».


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

کلاس Facade به این صورت پیاده‌سازی می‌شه که یک آبجکت رو به عنوان ورودی دریافت می‌کنه و با هر تابع خودش یک سری عملیات رو
روی اون آبجکت اعمال می‌کنه.

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

<summary>Typescript</summary>

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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یه زیرسیستم شلوغ و چندمرحله‌ای داری و می‌خوای یه ورودی ساده و خوش‌دست جلوش بذاری»؛ ❌ «وقتی فقط یه کلاس ساده داری که اصلاً پیچیدگی‌ای برای قایم کردن نداره».
> 🪤 **دام رایج:** «نما رو نکن یه کلاس خدا (God Object) که خودش همه‌کاره‌ست؛ نما فقط هماهنگ‌کننده‌ست، نه انجام‌دهنده همه‌چی».


<br>

---

<div align="center">

## وزن‌سبک (Flyweight) 🍃

</div>

<div align="center">
🍵 <b>مثال دنیای واقعی: غرفه چای</b>
</div>

توی غرفه چای معمولاً یه دیگ چای آماده هست و فروشنده فقط برای هر نفر یه لیوان می‌ریزه.
یعنی برای ۱۰۰ تا مشتری، قرار نیست ۱۰۰ بار «چای رو از صفر درست کنه»؛ بخش اصلی و مشترک (خودِ چای) رو نگه می‌داره و فقط چیزهای متفاوت رو برای هر نفر جدا حساب می‌کنه (مثلاً «کم‌شکر»، «با شیر»، «لیوانِ میز ۵»).

💡 **به زبون ساده:**
> این پترن می‌گه: **«بخش‌های مشترکِ آبجکت‌ها رو share کن؛ تفاوت‌ها رو از بیرون بهش بده.»**
> نتیجه؟ وقتی تعداد آبجکت‌ها خیلی زیاد می‌شه، حافظه و هزینه ساختن‌شون کمتر می‌شه.

ویکی‌پدیا:

<div dir="ltr">

> In computer programming, flyweight is a software design pattern. A flyweight is an object that minimizes memory use by
> sharing as much data as possible with other similar objects; it is a way to use objects in large numbers when a simple
> repeated representation would use an unacceptable amount of memory.

</div>

به زبون خودمون: وزن‌سبک یه آبجکته که با share کردنِ بیشترین داده ممکن با آبجکت‌های مشابه، مصرف حافظه رو کم می‌کنه.
وقتی قراره تعداد خیلی زیادی آبجکت بسازی و حالت تکراری و ساده‌شون کلی حافظه می‌بلعه، این پترن به دادت می‌رسه.

**مثال برنامه‌نویسی**

بیا مثال غرفه چای رو پیاده‌سازی کنیم. اول باید انواع چای و چای‌ساز رو پیاده‌سازی کنیم.

توی مرحله بعد ما یک کلاس `TeaShop` داریم که وظیفه ثبت سفارش و آماده کردن اون‌هارو به عهده داره.

برای اینکه حواس‌مون پیشِ خودِ پترن بمونه، اینجا کلاس چای رو خالی گذاشتیم؛ توی دنیای واقعی همین آبجکتِ مشترک می‌تونه داده‌های سنگینِ مشترک رو نگه داره. نکته اصلی اینه که چای‌ساز برای هر «نوع» چای فقط یه بار آبجکت می‌سازه و دفعه‌های بعد همون رو پس می‌ده؛ شماره میز هم از بیرون به سفارش وصل می‌شه، نه داخل خودِ چای.

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
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی قراره تعداد خیلی زیادی آبجکت بسازی که بخش بزرگی از داده‌شون مشترکه و حافظه داره می‌ترکه»؛ ❌ «وقتی آبجکت‌هات کم‌اند یا حالت مشترکی ندارن که بشه share کرد».
> 🪤 **دام رایج:** «به جای حالتِ مشترک و ثابت، روی حالتِ متغیر و بیرونی کش بگیری؛ اون‌وقت دیگه چیزی share نمی‌شه و کل ماجرا بی‌اثر می‌شه».


<br>

---

<div align="center">

## پراکسی (Proxy) 🎱

</div>

<div align="center">
🔐 <b>مثال دنیای واقعی: درِ رمزدار</b>
</div>

فرض کن یه درِ مهم داری (مثلاً درِ آزمایشگاه).
تو مستقیم نمی‌ری با خودِ در کلنجار برید؛ اول رمز می‌زنی یا کارت می‌کشید.

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

خب بیاید مثال درب رو پیاده‌سازی کنیم.

اول اینترفیس درب رو می‌سازیم و بعدش یک مدل درب پیاده‌سازی می‌کنیم.
در مرحله بعد هم یک پروکسی برای اضافه کردن امنیت به درب می‌سازیم.

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
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ وقتی می‌خوای دسترسی به یه شیء رو کنترل کنی یا قبل و بعدش یه کار اضافه (امنیت، کش، لاگ) بچسبونی، بی‌اینکه خودِ شیء اصلی عوض بشه؛ ❌ وقتی فقط می‌خوای رفتارش رو گسترش بدی نه کنترلش، که اون‌وقت کار تزئین‌گره.
> 🪤 **دام رایج:** پراکسی رو این‌قدر چاق نکن که کم‌کم منطق اصلی بره توش و دیگه معلوم نباشه شیء واقعی کیه.
> 🔗 **فرقش با [تزئین‌گر (Decorator)](#تزئین‌گر-decorator-):** تزئین‌گر قابلیت اضافه می‌کنه و شفافه، پراکسی دسترسی رو واسطه‌گری و کنترل می‌کنه؛ و فرقش با [مبدل (Adapter)](#مبدل-adapter-) اینه که مبدل اینترفیس رو عوض می‌کنه، ولی پراکسی همون اینترفیس رو نگه می‌داره.


<br>
<br>

---

<br>

<div align="center">

# الگوهای رفتاری (Behavioral Design Patterns) 🎭

</div>

به زبون ساده:

> این الگوها بهت اجازه می‌دن که رفتار کلاس‌ها رو تغییر بدی، یا این رفتار رو به کلاس‌های دیگه اضافه کنی.

ویکی‌پدیا:

<div dir="ltr">

> In software engineering, behavioral design patterns are design patterns that identify common communication patterns
> among objects. By doing so, these patterns increase flexibility in carrying out communication.

</div>

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

به زبون خودمون: یک منبعِ درخواست داریم و یک رشته پردازنده که پشت سر هم چیده شدن. هر پردازنده می‌دونه چه نوع درخواستی رو خودش می‌تونه جواب بده؛ هرچی از پسش برنمیاد رو دست‌نخورده پاس می‌ده به پردازنده بعدیِ توی زنجیره.

**مثال برنامه‌نویسی**

می‌خوایم همون مثال پرداخت رو باهم پیاده‌سازی کنیم.

خب توی کد بالا یک کلاس مرجع ساختیم که اسمش Account هست. این کلاس یک متد داره که اسمش pay هست. این متد یک مقدار رو می‌گیره
و سعی می‌کنه اون مقدار رو از حساب خود پرداخت کنه. اگر موفق نشد، اون مقدار رو به حساب بعدی انتقال می‌ده.

نکته:
متد getName هر حساب با کمک type(self).__name__ اسم کلاس خودش رو برمی‌گردونه؛ یعنی Bank یا Paypal یا Bitcoin. این‌جوری توی پیام پرداخت دقیقاً معلوم می‌شه کدوم حساب جواب داده.

خب حالا می‌خوایم یک حساب بانکی، یک حساب پی پال و یک حساب بیت کوین بسازیم.

همونطور که می‌بینی اومدیم و بعد از ساختن این حساب‌ها اونارو به هم متصل کردیم!

سیستم اول سعی کرده با حساب بانکی پرداخت کنه ولی موجودی کافی نداشت، برای همین درخواست رو پاس داده به حساب پی پال و این بار پرداخت با موفقیت انجام شده!

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
<summary>Typescript</summary>
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

> 🤔 **کی به کارش ببریم؟**
> ✅ «وقتی یک درخواست چند تا handler احتمالی داره و نمی‌دونی کدوم بالاخره جوابش رو می‌ده، بسپارش به زنجیره»؛ ❌ «وقتی همیشه دقیقاً یک نفر مسئوله و مقصد از اول معلومه، زنجیره فقط شلوغش می‌کنه».
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

**مثال برنامه‌نویسی**

می‌خوایم یک کنترل برای لامپ درست کنیم (Receiver).

اول باید یک ساختار برای دستورات درست کنیم (Command).

و در نهایت باید کنترل رو بسازیم که می‌تونه دستورات رو اجرا کنه! (Invoker)

توی این کد هم اول یک لامپ می‌سازیم و بعدش کامند‌های روشن کردن و خاموش کردن رو ایجاد می‌کنیم!

در نهایت وقتی نیاز به خاموش کردن یا روشن کردن داشته باشیم این کامند‌هارو به کنترلمون می‌فرستیم و اون اجراشون می‌کنه!

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
    _bulb = None

    def __init__(self, bulb):
        self._bulb = bulb

    def execute(self):
        pass


class TurnOn(Command):
    def execute(self):
        self._bulb.turnOn()


class TurnOff(Command):
    def execute(self):
        self._bulb.turnOff()


class RemoteControl:
    def submit(self, command):
        command.execute()


# ----------------------------

bulb = Bulb()

turnOn = TurnOn(bulb)
turnOff = TurnOff(bulb)

remote = RemoteControl()
remote.submit(turnOn)  # Bulb has been lit!
remote.submit(turnOff)  # Darkness!

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Bulb {
    turnOn() {
        console.log("Bulb has been lit");
    }

    turnOff() {
        console.log("Darkness!");
    }
}

class Command {
    protected _bulb: Bulb | null = null;

    constructor(bulb: Bulb) {
        this._bulb = bulb;
    }

    execute(): void {
    }
}

class TurnOn extends Command {
    execute() {
        this._bulb!.turnOn();
    }
}

class TurnOff extends Command {
    execute() {
        this._bulb!.turnOff();
    }
}

class RemoteControl {
    submit(command: { execute: () => void }) {
        command.execute();
    }
}

// ----------------------------

const bulb = new Bulb();

const turnOn = new TurnOn(bulb);
const turnOff = new TurnOff(bulb);

const remote = new RemoteControl();
remote.submit(turnOn); // Bulb has been lit!
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
}

class TurnOn extends Command {
    execute() {
        this._bulb.turnOn();
    }
}

class TurnOff extends Command {
    execute() {
        this._bulb.turnOff();
    }
}

class RemoteControl {
    submit(command) {
        command.execute();
    }
}


const bulb = new Bulb();

const turnOn = new TurnOn(bulb);
const turnOff = new TurnOff(bulb);

const remote = new RemoteControl();
remote.submit(turnOn);
remote.submit(turnOff);
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

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
  void Redo();
}

// Command
class TurnOn : ICommand
{
  private Bulb mBulb;

  public TurnOn(Bulb bulb)
  {
    mBulb = bulb ?? throw new ArgumentNullException("Bulb", "Bulb cannot be null");
  }

  public void Execute()
  {
    mBulb.TurnOn();
  }

  public void Undo()
  {
    mBulb.TurnOff();
  }

  public void Redo()
  {
    Execute();
  }
}

class TurnOff : ICommand
{
  private Bulb mBulb;

  public TurnOff(Bulb bulb)
  {
    mBulb = bulb ?? throw new ArgumentNullException("Bulb", "Bulb cannot be null");
  }

  public void Execute()
  {
    mBulb.TurnOff();
  }

  public void Undo()
  {
    mBulb.TurnOn();
  }

  public void Redo()
  {
    Execute();
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
  remote.Submit(turnOn); // Bulb has been lit!
  remote.Submit(turnOff); // Darkness!

  Console.ReadLine();

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
    public function redo();
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

    public function redo()
    {
        $this->execute();
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

    public function redo()
    {
        $this->execute();
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
$remote->submit($turnOn); // Bulb has been lit!
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

// ICommand interface
type ICommand interface {
    Execute()
    Undo()
    Redo()
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

func (c *TurnOnCommand) Redo() {
    c.Execute()
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

func (c *TurnOffCommand) Redo() {
    c.Execute()
}

// Invoker
type RemoteControl struct{}

func (r *RemoteControl) Submit(command ICommand) {
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
        System.out.println("Bulb is turned ON");
    }

    public void turnOff() {
        System.out.println("Bulb is turned OFF");
    }
}

interface Command {
    void execute();
    void undo();
    void redo();
}

// Command
class TurnOn implements Command {
    private Bulb bulb;

    public TurnOn(Bulb bulb) {
        if (bulb == null)
            throw new IllegalArgumentException("Bulb cannot be null");
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

    @Override
    public void redo() {
        execute();
    }
}

class TurnOff implements Command {
    private Bulb bulb;

    public TurnOff(Bulb bulb) {
        if (bulb == null)
            throw new IllegalArgumentException("Bulb cannot be null");
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

    @Override
    public void redo() {
        execute();
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
remote.submit(turnOnCmd);       // Bulb is turned ON
remote.submit(turnOffCmd);      // Bulb is turned OFF
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
        std::cout << "Bulb has been lit!" << std::endl;
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
    virtual void redo() = 0;
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

    void redo() override {
        execute();
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

    void redo() override {
        execute();
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
    remote.submit(turnOn);   // Bulb has been lit!
    remote.submit(turnOff);  // Darkness!
    return 0;
}
```

</div>

</details>

<br>

---

<div align="center">

## پیمایش‌گر (Iterator) ➿

</div>

<div align="center">
📻 <b>مثال دنیای واقعی: رادیو (دکمه بعدی/قبلی)</b>
</div>

تو وقتی رادیو گوش می‌دید، فقط دکمه «بعدی» یا «قبلی» رو می‌زنی و فرکانس عوض می‌شه.
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

**مثال برنامه‌نویسی**

این مثال رو می‌خوایم یکم پایتونیک پیش بریم! می‌دونی که توی پایتون دو تا مفهوم Iterable و Iterator رو داریم پس می‌ریم ازشون
استفاده کنیم!

این کلاس یک Iterator هستش که می‌تونه توی یک WordsCollection جابجا بشه و عناصرش رو برگردونه!

توی این کد هم می‌تونی ببین که چطوری می‌تونیم از Iterator‌ها استفاده کنیم!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
from __future__ import annotations
from collections.abc import Iterable, Iterator
from typing import Any, List


class AlphabeticalOrderIterator(Iterator):
    _position: int = None

    def __init__(self, collection: WordsCollection, reverse: bool = False) -> None:
        self._collection = collection
        self._reverse = reverse
        self._position = -1 if reverse else 0

    def __next__(self):
        try:
            value = self._collection[self._position]
            self._position += -1 if self._reverse else 1
        except IndexError:
            raise StopIteration()

        return value


class WordsCollection(Iterable):
    def __init__(self, collection: List[Any] = []) -> None:
        self._collection = collection

    def __iter__(self) -> AlphabeticalOrderIterator:
        return AlphabeticalOrderIterator(self._collection)

    def get_reverse_iterator(self) -> AlphabeticalOrderIterator:
        return AlphabeticalOrderIterator(self._collection, True)

    def add_item(self, item: Any) -> None:
        self._collection.append(item)

#----------------------------

if __name__ == "__main__":
    collection = WordsCollection()
    collection.add_item("First")
    collection.add_item("Second")
    collection.add_item("Third")

    print("Straight traversal:")
    print("\n".join(collection))

    print("\n")
    print("Reverse traversal:")
    print("\n".join(collection.get_reverse_iterator()), end="")




'''
Output will be
==============
Straight traversal:
First
Second
Third


Reverse traversal:
Third
Second
First%
'''
```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface Iterator<T> {
    next(): { value: T; done: boolean };
}

class AlphabeticalOrderIterator implements Iterator<string> {
    private position: number;

    constructor(private collection: WordsCollection, private reverse = false) {
        this.position = this.reverse ? -1 : 0;
    }

    next() {
        try {
            const value = this.collection.collection[this.position];
            this.position += this.reverse ? -1 : 1;
            return {value, done: false};
        } catch (error) {
            return {value: undefined, done: true};
        }
    }
}

class WordsCollection {
    collection: string[];

    constructor(collection: string[] = []) {
        this.collection = collection;
    }

    [Symbol.iterator]() {
        return new AlphabeticalOrderIterator(this);
    }

    getReverseIterator() {
        return new AlphabeticalOrderIterator(this, true);
    }

    addItem(item: string) {
        this.collection.push(item);
    }
}

// ----------------------------

const collection = new WordsCollection();
collection.addItem("First");
collection.addItem("Second");
collection.addItem("Third");

console.log("Straight traversal:");
for (const item of collection) {
    console.log(item);
}

console.log("\nReverse traversal:");
for (const item of collection.getReverseIterator()) {
    console.log(item);
}
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class AlphabeticalOrderIterator {
    constructor(collection, reverse = false) {
        this.collection = collection;
        this.reverse = reverse;
        this.position = this.reverse ? collection.collection.length - 1 : 0;
    }

    next() {
        if (this.position >= 0 && this.position < this.collection.collection.length) {
            const value = this.collection.collection[this.position];
            this.position += this.reverse ? -1 : 1;
            return { value, done: false };
        } else {
            return { value: undefined, done: true };
        }
    }
}

class WordsCollection {
    constructor(collection = []) {
        this.collection = collection;
    }

    [Symbol.iterator]() {
        return new AlphabeticalOrderIterator(this);
    }

    getReverseIterator() {
        return new AlphabeticalOrderIterator(this, true);
    }

    addItem(item) {
        this.collection.push(item);
    }
}


const collection = new WordsCollection();
collection.addItem("First");
collection.addItem("Second");
collection.addItem("Third");

console.log("Straight traversal:");
for (const item of collection) {
    console.log(item);
}

console.log("\nReverse traversal:");
const reverseIterator = collection.getReverseIterator();
let result = reverseIterator.next();
while (!result.done) {
    console.log(result.value);
    result = reverseIterator.next();
}
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

class RadioStation
{
  private float mFrequency;

  public RadioStation(float frequency)
  {
    mFrequency = frequency;
  }

  public float GetFrequecy()
  {
    return mFrequency;
  }

}


class StationList : IEnumerable<RadioStation>
{
  List<RadioStation> mStations = new List<RadioStation>();

  public RadioStation this[int index]
  {
    get { return mStations[index]; }
    set { mStations.Insert(index, value); }
  }

  public void Add(RadioStation station)
  {
    mStations.Add(station);
  }

  public void Remove(RadioStation station)
  {
    mStations.Remove(station);
  }

  public IEnumerator<RadioStation> GetEnumerator()
  {
    return this.GetEnumerator();
  }

  IEnumerator IEnumerable.GetEnumerator()
  {
    //Use can switch to this internal collection if you do not want to transform
    //return mStations.GetEnumerator();

    //use this if you want to transform the object before rendering
    foreach (var x in mStations)
    {
      yield return x;
    }
  }
}



// ----------------------------

var stations = new StationList();
var station1 = new RadioStation(89);
stations.Add(station1);

var station2 = new RadioStation(101);
stations.Add(station2);

var station3 = new RadioStation(102);
stations.Add(station3);

foreach(var x in stations)
{
  Console.Write(x.GetFrequecy());
}

var q = stations.Where(x => x.GetFrequecy() == 89).FirstOrDefault();
Console.WriteLine(q.GetFrequecy());

Console.ReadLine();

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

    public function remove(RadioStation $station)
    {
        $index = array_search($station, $this->mStations, true);
        if ($index !== false) {
            array_splice($this->mStations, $index, 1);
        }
    }

    public function getIterator()
    {
        // Use can switch to this internal collection if you do not want to transform
        // return new ArrayIterator($this->mStations);

        // Use this if you want to transform the object before rendering
        foreach ($this->mStations as $x) {
            yield $x;
        }
    }
}

$stations = new StationList();
$station1 = new RadioStation(89);
$stations->add($station1);

$station2 = new RadioStation(101);
$stations->add($station2);

$station3 = new RadioStation(102);
$stations->add($station3);

foreach ($stations as $x) {
    echo $x->getFrequency() . ' ';
}

$q = array_filter($stations, function ($x) {
    return $x->getFrequency() == 89;
});
echo reset($q)->getFrequency();

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

func (s *StationList) Remove(station *RadioStation) {
    for i, v := range s.stations {
        if v == station {
            s.stations = append(s.stations[:i], s.stations[i+1:]...)
            break
        }
    }
}

func (s *StationList) GetStation(index int) *RadioStation {
    return s.stations[index]
}

func (s *StationList) Len() int {
    return len(s.stations)
}

func (s *StationList) Less(i, j int) bool {
    return s.stations[i].GetFrequency() < s.stations[j].GetFrequency()
}

func (s *StationList) Swap(i, j int) {
    s.stations[i], s.stations[j] = s.stations[j], s.stations[i]
}

func (s *StationList) Sort() {
    sort.Sort(s)
}

func (s *StationList) Search(station *RadioStation) int {
    return sort.Search(len(s.stations), func(i int) bool {
        return s.stations[i].GetFrequency() >= station.GetFrequency()
    })
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
    station1 := NewRadioStation(89)
    stations.Add(station1)

    station2 := NewRadioStation(101)
    stations.Add(station2)

    station3 := NewRadioStation(102)
    stations.Add(station3)

    for station := range stations.Iterator() {
        fmt.Println(station.GetFrequency())
    }

    q := sort.Search(stations.Len(), func(i int) bool {
        return stations.GetStation(i).GetFrequency() >= 89
    })
    fmt.Println(stations.GetStation(q).GetFrequency())
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
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

    public List<RadioStation> getStations() {
        return stations;
    }

    public void add(RadioStation station) {
        stations.add(station);
    }

    public void remove(RadioStation station) {
        stations.remove(station);
    }

    @Override
    public Iterator<RadioStation> iterator() {
        return this.getStations().iterator();
    }
}

// ----------------------------

StationList stations = new StationList();
RadioStation station1 = new RadioStation(89);
stations.add(station1);

RadioStation station2 = new RadioStation(101);
stations.add(station2);

RadioStation station3 = new RadioStation(102);
stations.add(station3);

Iterator<RadioStation> stationIterator = stations.iterator();
while (stationIterator.hasNext()) {
RadioStation radioStation = stationIterator.next();
System.out.println(radioStation.getFrequency());
}
// 89.0
// 101.0
// 102.0
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <vector>

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

    void remove(const RadioStation& station) {
        for (auto it = stations.begin(); it != stations.end(); ++it) {
            if (it->getFrequency() == station.getFrequency()) {
                stations.erase(it);
                break;
            }
        }
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
    stations.add(RadioStation(89));
    stations.add(RadioStation(101));
    stations.add(RadioStation(102));

    for (auto& station : stations) {
        std::cout << station.getFrequency() << std::endl;
    }
    // 89
    // 101
    // 102
    return 0;
}
```

</div>

</details>

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

**مثال برنامه‌نویسی**

می‌خوایم یک ساختار چت روم بسازیم! (Mediator)

خب حالا بخش یوزر‌ها: (Colleagues)

<details>
<summary>Python</summary>

<div dir="ltr">

```python
import datetime


class ChatRoomMediator:
    def showMessage(self, user, message):
        pass


class ChatRoom(ChatRoomMediator):
    def showMessage(self, user, message):
        time = datetime.datetime.now()
        sender = user.getName()

        print(str(time) + '[' + sender + ']: ' + message)


class User:
    _name = None
    _chatMediator = None

    def __init__(self, name, chatMediator):
        self.name = name
        self._chatMediator = chatMediator

    def getName(self):
        return self.name

    def send(self, message):
        self._chatMediator.showMessage(self, message)


#----------------------------

mediator = ChatRoom()

john = User('John', mediator)
jane = User('Jane', mediator)

john.send('Hi There!')
jane.send('Hey!')


'''
Output will be
==============
2024-09-23 21:20:17.284000[John]: Hi There!
2024-09-23 21:20:17.284023[Jane]: Hey!

'''
```

</div>

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
class ChatRoomMediator {
    showMessage(user: User, message: string): void {
    }
}

class ChatRoom extends ChatRoomMediator {
    showMessage(user: User, message: string): void {
        let time = new Date();
        let sender = user.getName();

        console.log(`${time.toLocaleString()} [${sender}]: ${message}`);
    }
}

class User {
    private name: string;
    private chatMediator: ChatRoomMediator;

    constructor(name: string, chatMediator: ChatRoomMediator) {
        this.name = name;
        this.chatMediator = chatMediator;
    }

    getName(): string {
        return this.name;
    }

    send(message: string): void {
        this.chatMediator.showMessage(this, message);
    }
}

// ----------------------------

const mediator = new ChatRoom();

const john = new User("John", mediator);
const jane = new User("Jane", mediator);

john.send("Hi there!");
jane.send("Hey!");

// Output will be:
// Feb 14, 10:58 [John]: Hi there!
// Feb 14, 10:58 [Jane]: Hey!
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
        const time = new Date();
        const sender = user.getName();

        console.log(`${time.toLocaleString()} [${sender}]: ${message}`);
    }
}

class User {
    constructor(name, chatMediator) {
        this.name = name;
        this.chatMediator = chatMediator;
    }

    getName() {
        return this.name;
    }

    send(message) {
        this.chatMediator.showMessage(this, message);
    }
}


const mediator = new ChatRoom();

const john = new User("John", mediator);
const jane = new User("Jane", mediator);

john.send("Hi there!");
jane.send("Hey!");
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

interface IChatRoomMediator
{
  void ShowMessage(User user, string message);
}

//Mediator
class ChatRoom : IChatRoomMediator
{
  public void ShowMessage(User user, string message)
  {
    Console.WriteLine($"{DateTime.Now.ToString("MMMM dd, H:mm")} [{user.GetName()}]:{message}");
  }
}


class User
{
  private string mName;
  private IChatRoomMediator mChatRoom;

  public User(string name, IChatRoomMediator chatroom)
  {
    mChatRoom = chatroom;
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

//April 14, 20:05[John]:Hi there!
//April 14, 20:05[Jane]:Hey!

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
        echo date('F d, H:i') . " [" . $user->getName() . "]: " . $message . "\n";
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
// February 15, 14:44 [John]: Hi there!
// February 15, 14:44 [Jane]: Hey!

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
	"time"
)

type ChatRoomMediator interface {
	ShowMessage(user *User, message string)
}

type ChatRoom struct{}

func (cr *ChatRoom) ShowMessage(user *User, message string) {
	fmt.Printf("%s [%s]: %s\n", time.Now().Format("January 02, 15:04"), user.GetName(), message)
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

//Mediator
class ChatRoom implements ChatRoomMediator {

    SimpleDateFormat sdf = new SimpleDateFormat("MMMM dd, HH:mm");

    @Override
    public void showMessage(User user, String message) {
        System.out.println(sdf.format(new Date())+ " [" + user.getName() + "]: " + message);
    }
}

class User {
    private String name;
    private ChatRoomMediator chatRoom;

    public User(String name, ChatRoomMediator chatroom) {
        chatRoom = chatroom;
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

john.send("Hi there!"); // March 01, 21:38 [John]: Hi there!
jane.send("Hey!");      // March 01, 21:38 [Jane]: Hey!
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <ctime>

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
    User(const std::string& n, ChatRoomMediator* room) 
        : name(n), chatRoom(room) {}

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
        time_t now = time(0);
        char* dt = ctime(&now);
        std::cout << dt << " [" << user->getName() << "]: " << message << std::endl;
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

<br>

---

<div align="center">

## یادبود (Memento) 💾

</div>

<div align="center">
↩️ <b>مثال دنیای واقعی: دکمه Undo</b>
</div>

فرض کن داری توی یک ادیتور متن تایپ می‌کنی.
یه دفعه یه چیزی خراب می‌شه و می‌گید: «ای بابا! برگردون به ۲ دقیقه قبل.»

ادیتور برای اینکه بتونه این کار رو بکنه، هر از گاهی از وضعیت خودش یه «عکس» (Snapshot) برمی‌داره و نگه می‌داره.
وقتی تو `Undo` می‌زنی، یکی از همون عکس‌ها رو برمی‌گردونه و همه‌چی برمی‌گرده به حالت قبل. 🧠

💡 **به زبون ساده:**
> این پترن می‌گه: **«از حالتِ فعلی یه snapshot بگیر، نگهش دار، هر وقت لازم شد restore کن.»**

ویکی‌پدیا:

<div dir="ltr">

> The memento pattern is a software design pattern that provides the ability to restore an object to its previous
> state (undo via rollback).

</div>

**مثال برنامه‌نویسی**

می‌خوایم یک ادیتور متن بسازیم و قابلیت ذخیره کردن و بازگردانی بهش اضافه کنیم!

خب اول یک کلاس به عنوان حافظه ادیتور می‌سازیم! مشخصه که وظیفه‌اش فقط نگهداری یک مقدار هست!

در ادامه یک کلاس ادیتور می‌سازیم که قابلیت تایپ کردن، خالی کردن، سیو و برگشت حافظه داره!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class EditorMemento:
    _content = None

    def __init__(self, content):
        self._content = content

    def getContent(self):
        return self._content


class Editor:
    _content = ''

    def type(self, words):
        self._content = self._content + ' ' + words

    def getContent(self):
        return self._content

    def save(self):
        return EditorMemento(self._content)

    def restore(self, memento):
        self._content = memento.getContent()


# ----------------------------

editor = Editor()
editor.type('This is the first sentence')
editor.type('This is the second.')

saved = editor.save()
editor.type('And this is the third')

print(editor.getContent())

editor.restore(saved)
print(editor.getContent())

'''
Output will be
==============
 This is the first sentence This is the second. And this is the third
 This is the first sentence This is the second.
'''

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class EditorMemento {
    private content: string | null = null;

    constructor(content: string) {
        this.content = content;
    }

    getContent(): string {
        return this.content;
    }
}

class Editor {
    private content = "";

    type(words: string): void {
        this.content = this.content + " " + words;
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

// ----------------------------

const editor = new Editor();
editor.type("This is the first sentence");
editor.type("This is the second.");

const saved = editor.save();
editor.type("And this is the third");

console.log(editor.getContent()); // This is the first sentence. This is second. And this is third.

editor.restore(saved);
console.log(editor.getContent()); // This is the first sentence. This is second.
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class EditorMemento {
    constructor(content) {
        this.content = content;
    }

    getContent() {
        return this.content;
    }
}

class Editor {
    constructor() {
        this.content = "";
    }

    type(words) {
        this.content = this.content + " " + words;
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


const editor = new Editor();
editor.type("This is the first sentence");
editor.type("This is the second.");

const saved = editor.save();
editor.type("And this is the third");

console.log(editor.getContent());

editor.restore(saved);
console.log(editor.getContent());
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

class EditorMemento
{
  private string mContent;

  public EditorMemento(string content)
  {
    mContent = content;
  }

  public string Content
  {
    get
    {
      return mContent;
    }
  }
}


class Editor {

  private string mContent = string.Empty;
  private EditorMemento memento;

  public Editor()
  {
    memento = new EditorMemento(string.Empty);
  }

  public void Type(string words)
  {
    mContent = String.Concat(mContent," ", words);
  }

  public string Content
  {
    get
    {
      return mContent;
    }
  }

  public void Save()
  {
    memento = new EditorMemento(mContent);
  }

  public void Restore()
  {
    mContent = memento.Content;
  }
}

// ----------------------------

var editor = new Editor();

//Type some stuff
editor.Type("This is the first sentence.");
editor.Type("This is second.");

// Save the state to restore to : This is the first sentence. This is second.
editor.Save();

//Type some more
editor.Type("This is third.");

//Output the content
Console.WriteLine(editor.Content); // This is the first sentence. This is second. This is third.

//Restoring to last saved state
editor.Restore();

Console.Write(editor.Content); // This is the first sentence. This is second


```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
class EditorMemento
{
  private $mContent;

  public function __construct($content)
  {
    $this->mContent = $content;
  }

  public function getContent()
  {
    return $this->mContent;
  }
}

class Editor
{
  private $mContent = '';
  private $memento;

  public function __construct()
  {
    $this->memento = new EditorMemento('');
  }

  public function type($words)
  {
    $this->mContent .= ' ' . $words;
  }

  public function getContent()
  {
    return $this->mContent;
  }

  public function save()
  {
    $this->memento = new EditorMemento($this->mContent);
  }

  public function restore()
  {
    $this->mContent = $this->memento->getContent();
  }
}

$editor = new Editor();

//Type some stuff
$editor->type("This is the first sentence.");
$editor->type("This is second.");

// Save the state to restore to : This is the first sentence. This is second.
$editor->save();

//Type some more
$editor->type("This is third.");

//Output the content
echo $editor->getContent(); // This is the first sentence. This is second. This is third.

//Restoring to last saved state
$editor->restore();

echo $editor->getContent(); // This is the first sentence. This is second
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class EditorMemento {
    private String content;

    public EditorMemento(String content) {
        this.content = content;
    }

    public String getContent() {
        return this.content;
    }
}

class Editor {
    private String content = "";
    private EditorMemento memento;

    public Editor() {
        this.memento = new EditorMemento("");
    }

    public void type(String words) {
        if(!this.content.isEmpty())
            this.content += " ";
        this.content += words;
    }

    public String getContent() {
        return this.content;
    }

    public void save() {
        memento = new EditorMemento(content);
    }

    public void restore() {
        content = memento.getContent();
    }
}

// ----------------------------

editor.type("This is the first sentence.");
editor.type("This is second.");
// Save the state
editor.save();
// Type more
editor.type("This is third.");
// Print all contents
System.out.println(editor.getContent()); // This is the first sentence. This is second. This is third.
// Restoring to last saved state
editor.restore();
// Print content
System.out.println(editor.getContent()); // This is the first sentence. This is second.
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

type EditorMemento struct {
	content string
}

func NewEditorMemento(content string) *EditorMemento {
	return &EditorMemento{content: content}
}

func (e *EditorMemento) GetContent() string {
	return e.content
}

type Editor struct {
	content string
}

func (e *Editor) Type(words string) {
	e.content = e.content + " " + words
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

func main() {
	editor := &Editor{}
	editor.Type("This is the first sentence")
	editor.Type("This is the second.")

	saved := editor.Save()
	editor.Type("And this is the third")

	fmt.Println(editor.GetContent())

	editor.Restore(saved)
	fmt.Println(editor.GetContent())
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

class EditorMemento {
private:
    std::string content;

public:
    EditorMemento(const std::string& c) : content(c) {}

    std::string getContent() const {
        return content;
    }
};

class Editor {
private:
    std::string content;

public:
    void type(const std::string& words) {
        content = content + " " + words;
    }

    std::string getContent() const {
        return content;
    }

    EditorMemento save() {
        return EditorMemento(content);
    }

    void restore(const EditorMemento& memento) {
        content = memento.getContent();
    }
};

// ----------------------------

int main() {
    Editor editor;
    editor.type("This is the first sentence");
    editor.type("This is the second.");

    EditorMemento saved = editor.save();
    editor.type("And this is the third");

    std::cout << editor.getContent() << std::endl;

    editor.restore(saved);
    std::cout << editor.getContent() << std::endl;
    return 0;
}
```

</div>

</details>

<br>

---

<div align="center">

## ناظر (Observer) 😎

</div>

<div align="center">
📬 <b>مثال دنیای واقعی: اعلان‌های سایت کاریابی</b>
</div>

فرض کن توی یه سایت کاریابی ثبت‌نام کردی و می‌گید: «هر وقت توی دسته برنامه‌نویسی، یه شغل جدید اومد، به من خبر بده.»
حالا از اون طرف، سایت هر بار که یه آگهی جدید اضافه می‌شه، میاد به همه آدم‌هایی که اون دسته رو دنبال می‌کنن ایمیل/نوتیف می‌فرسته.

یعنی تو لازم نیست هر روز برید سایت رو چک کنی. خودِ سیستم با هر تغییر، خبرت می‌کنه. 🔔

💡 **به زبون ساده:**
> این پترن می‌گه: **«یک نفر تغییر می‌کنه (Subject) و بقیه‌ای که دنبالشن (Observerها) خودکار باخبر می‌شن.»**

ویکی‌پدیا:

<div dir="ltr">

> The observer pattern is a software design pattern in which an object, called the subject, maintains a list of its
> dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their
> methods.

</div>

**مثال برنامه‌نویسی**

در بخش اول یک کلاس برای ذخیره کردن یک شغل می‌سازیم و در بخش بعدی یک کلاس برای جویندگان کار می‌سازیم!

و بعد باید یک کلاس برای دسته بندی‌های مختلف کار ایجاد کنیم و جویندگان کار می‌تونن بهش اضافه بشن و اگه شغلی توی اون دسته
بندی ارسال بشه به اونا اطلاع رسانی می‌شه!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class JobPost:
    _title = None

    def __init__(self, title):
        self.title = title

    def getTitle(self):
        return self.title


class JobSeeker:
    _name = None

    def __init__(self, name):
        self.name = name

    def onJobPosted(self, job):
        print('Hi ' + self.name + '! New job posted: ' + job.getTitle())


class JobCategory:
    _observers = []

    def notify(self, jobPosting):
        for observer in self._observers:
            observer.onJobPosted(jobPosting)

    def attach(self, observer):
        self._observers.append(observer)

    def addJob(self, jobPosting):
        self.notify(jobPosting)


# ----------------------------

johnDoe = JobSeeker('John Doe')
janeDoe = JobSeeker('Jane Doe')

jobPostings = JobCategory()
jobPostings.attach(janeDoe)
jobPostings.attach(johnDoe)

jobPostings.addJob(JobPost('Software Engineer at XXX'))

# Output
# Hi John Doe! New job posted: Software Engineer
# Hi Jane Doe! New job posted: Software Engineer

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class JobPost {
    private title: string | null = null;

    constructor(title: string) {
        this.title = title;
    }

    getTitle(): string {
        return this.title;
    }
}

class JobSeeker {
    private name: string | null = null;

    constructor(name: string) {
        this.name = name;
    }

    onJobPosted(job: JobPost): void {
        console.log(`Hi ${this.name}! New job posted: ${job.getTitle()}`);
    }
}

class JobCategory {
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

const jobPostings = new JobCategory();
jobPostings.attach(janeDoe);
jobPostings.attach(johnDoe);

jobPostings.addJob(new JobPost("Software Engineer at XXX"));

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

class JobCategory {
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

const jobPostings = new JobCategory();
jobPostings.attach(janeDoe);
jobPostings.attach(johnDoe);

jobPostings.addJob(new JobPost("Software Engineer at XXX"));
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

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

  //Method is not being called by JobPostings class currently
  public void OnCompleted()
  {
    //No Implementation
  }

  //Method is not being called by JobPostings class currently
  public void OnError(Exception error)
  {
    //No Implementation
  }

  public void OnNext(JobPost value)
  {
    Console.WriteLine($"Hi {Name} ! New job posted: {value.Title}");
  }
}


class JobPostings : IObservable<JobPost>
{
  private List<IObserver<JobPost>> mObservers;
  private List<JobPost> mJobPostings;

  public JobPostings()
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

//Create publisher and attch subscribers
var jobPostings = new JobPostings();
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
class JobPost
{
    public function __construct(private string $title)
    {
    }

    public function getTitle()
    {
        return $this->title;
    }
}

class JobSeeker implements SplObserver
{
    public function __construct(private string $name)
    {
    }

    public function update(SplSubject $subject)
    {
        if ($subject instanceof JobPostings) {
            $jobPost = $subject->getJobPost();
            echo "Hi {$this->name} ! New job posted: {$jobPost->getTitle()}\n";
        }
    }
}

class JobPostings implements SplSubject
{
    private $observers;
    private $jobPostings;

    public function __construct()
    {
        $this->observers = new SplObjectStorage();
        $this->jobPostings = [];
    }

    public function attach(SplObserver $observer)
    {
        $this->observers->attach($observer);
    }

    public function detach(SplObserver $observer)
    {
        $this->observers->detach($observer);
    }

    public function notify()
    {
        foreach ($this->observers as $observer) {
            $observer->update($this);
        }
    }

    public function addJob(JobPost $jobPost)
    {
        $this->jobPostings[] = $jobPost;
        $this->notify();
    }

    public function getJobPost()
    {
        return end($this->jobPostings);
    }
}

//Create Subscribers
$johnDoe = new JobSeeker("John Doe");
$janeDoe = new JobSeeker("Jane Doe");

//Create publisher and attach subscribers
$jobPostings = new JobPostings();
$jobPostings->attach($johnDoe);
$jobPostings->attach($janeDoe);

//Add a new job and see if subscribers get notified
$jobPostings->addJob(new JobPost("Software Engineer"));

//Output
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

type JobCategory struct {
	observers []*JobSeeker
}

func NewJobCategory() *JobCategory {
	return &JobCategory{}
}

func (jc *JobCategory) Notify(jobPosting *JobPost) {
	for _, observer := range jc.observers {
		observer.OnJobPosted(jobPosting)
	}
}

func (jc *JobCategory) Attach(observer *JobSeeker) {
	jc.observers = append(jc.observers, observer)
}

func (jc *JobCategory) AddJob(jobPosting *JobPost) {
	jc.Notify(jobPosting)
}

func main() {
	johnDoe := NewJobSeeker("John Doe")
	janeDoe := NewJobSeeker("Jane Doe")

	jobPostings := NewJobCategory()
	jobPostings.Attach(janeDoe)
	jobPostings.Attach(johnDoe)

	jobPostings.AddJob(NewJobPost("Software Engineer at XXX"))

	// Output
	// Hi Jane Doe! New job posted: Software Engineer at XXX
	// Hi John Doe! New job posted: Software Engineer at XXX
}


```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
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

class JobCategory {
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

JobCategory jobPostings = new JobCategory();
jobPostings.attach(janeDoe);
jobPostings.attach(johnDoe);

jobPostings.addJob(new JobPost("Software Engineer at IBM"));
// Hi Jane Doe! New job posted: Software Engineer at IBM
// Hi John Doe! New job posted: Software Engineer at IBM
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
class JobCategory {
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
    
    JobCategory jobPostings;
    jobPostings.attach(janeDoe);
    jobPostings.attach(johnDoe);
    
    jobPostings.addJob(JobPost("Software Engineer at IBM"));
    // Hi Jane Doe! New job posted: Software Engineer at IBM
    // Hi John Doe! New job posted: Software Engineer at IBM
    
    return 0;
}
```
</div>
</details>

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

اگه هر بار برید توی کلاس تک‌تک حیوان‌ها دست ببری و متد جدید اضافه کنی، کدت خیلی زود شلوغ و شکننده می‌شه.
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


monkey = Monkey()
lion = Lion()
dolphin = Dolphin()

speak = Speak()
monkey.accept(speak)  # Ooh oo aa aa!
lion.accept(speak)  # Roaaar!
dolphin.accept(speak)  # Tuut tutt tuttt!
```

</div>

حالا اگه بخوایم قابلیت پریدن رو به حیوونا اضافه کنیم، کار خیلی راحته ببین:

<div dir="ltr">

```python
class Jump(AnimalOperation):
    def visitMonkey(self, monkey):
        print('Jumped 20 feet high! on to the tree!')

    def visitLion(self, lion):
        print('Jumped 7 feet! back on the ground!')

    def visitDolphin(self, dolphin):
        print('Walked on water a little and disappeared')
```

</div>

حالا نحوه فراخوانیش رو در کنار صدای حیوونا ببین:

<div dir="ltr">

```python
jump = Jump()

monkey.accept(speak)  # Ooh oo aa aa!
monkey.accept(jump)  # Jumped 20 feet high! on to the tree!

lion.accept(speak)  # Roaaar!
lion.accept(jump)  # Jumped 7 feet! Back on the ground!

dolphin.accept(speak)  # Tuut tutt tuutt!
dolphin.accept(jump)  # Walked on water a little and disappeared
```

</div>

</details>

<details>
<summary>Typescript</summary>
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
  visitMonkey(monkey: Monkey) {
    monkey.shout();
  }

  visitLion(lion: Lion) {
    lion.roar();
  }

  visitDolphin(dolphin: Dolphin) {
    dolphin.speak();
  }
}

const monkey = new Monkey();
const lion = new Lion();
const dolphin = new Dolphin();
const speak = new Speak();

monkey.accept(speak); // Ooh oo aa aa!
lion.accept(speak); // Roaaar!
dolphin.accept(speak); //Tuut tutt tuttt!

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

const jump = new Jump();

monkey.accept(speak); // Ooh oo aa aa!
monkey.accept(jump); // Jumped 20 feet high! on to the tree!

lion.accept(speak); // Roaaar!
lion.accept(jump); // Jumped 7 feet! Back on the ground!

dolphin.accept(speak); // Tuut tutt tuutt!
dolphin.accept(jump); // Walked on water a little and disappeared
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

monkey.accept(speak);
lion.accept(speak);
dolphin.accept(speak);

monkey.accept(jump);
lion.accept(jump);
dolphin.accept(jump);
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

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
    Console.WriteLine("Oooh o aa aa!");
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
    Console.WriteLine("Roaar!");
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
    Console.WriteLine("Tuut tittu tuutt!");
  }

  public void Accept(IAnimalOperation operation)
  {
      operation.VisitDolphin(this);
  }
}


class Speak : IAnimalOperation
{
  public void VisitDolphin(Dolphin dolphin)
  {
    dolphin.Speak();
  }

  public void VisitLion(Lion lion)
  {
    lion.Roar();
  }

  public void VisitMonkey(Monkey monkey)
  {
    monkey.Shout();
  }
}

// ----------------------------

var monkey = new Monkey();
var lion = new Lion();
var dolphin = new Dolphin();

var speak = new Speak();

monkey.Accept(speak);    // Ooh oo aa aa!
lion.Accept(speak);      // Roaaar!
dolphin.Accept(speak);   // Tuut tutt tuutt!

// -----------------------------

class Jump : IAnimalOperation
{
  public void VisitDolphin(Dolphin dolphin)
  {
    Console.WriteLine("Walked on water a little and disappeared!");
  }

  public void VisitLion(Lion lion)
  {
    Console.WriteLine("Jumped 7 feet! Back on the ground!");
  }

  public void VisitMonkey(Monkey monkey)
  {
    Console.WriteLine("Jumped 20 feet high! on to the tree!");
  }
}

// ------------------------------

var jump = new Jump();

monkey.Accept(speak);   // Ooh oo aa aa!
monkey.Accept(jump);    // Jumped 20 feet high! on to the tree!

lion.Accept(speak);     // Roaaar!
lion.Accept(jump);      // Jumped 7 feet! Back on the ground!

dolphin.Accept(speak);  // Tuut tutt tuutt!
dolphin.Accept(jump);   // Walked on water a little and disappeared


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
    echo "Oooh o aa aa!";
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
    echo "Roaar!";
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
    echo "Tuut tittu tuutt!";
  }

  public function accept(AnimalOperationInterface $operation)
  {
    $operation->visitDolphin($this);
  }
}

class Speak implements AnimalOperationInterface
{
  public function visitDolphin(Dolphin $dolphin)
  {
    $dolphin->speak();
  }

  public function visitLion(Lion $lion)
  {
    $lion->roar();
  }

  public function visitMonkey(Monkey $monkey)
  {
    $monkey->shout();
  }
}

$monkey = new Monkey();
$lion = new Lion();
$dolphin = new Dolphin();

$speak = new Speak();

$monkey->accept($speak);    // Ooh oo aa aa!
$lion->accept($speak);      // Roaaar!
$dolphin->accept($speak);   // Tuut tutt tuutt!

class Jump implements AnimalOperationInterface
{
  public function visitDolphin(Dolphin $dolphin)
  {
    echo "Walked on water a little and disappeared!";
  }

  public function visitLion(Lion $lion)
  {
    echo "Jumped 7 feet! Back on the ground!";
  }

  public function visitMonkey(Monkey $monkey)
  {
    echo "Jumped 20 feet high! on to the tree!";
  }
}

$jump = new Jump();

$monkey->accept($speak);   // Ooh oo aa aa!
$monkey->accept($jump);    // Jumped 20 feet high! on to the tree!

$lion->accept($speak);     // Roaaar!
$lion->accept($jump);      // Jumped 7 feet! Back on the ground!

$dolphin->accept($speak);  // Tuut tutt tuutt!
$dolphin->accept($jump);   // Walked on water a little and disappeared

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

func main() {
	monkey := &Monkey{}
	lion := &Lion{}
	dolphin := &Dolphin{}

	speak := &Speak{}
	monkey.Accept(speak)  // Ooh oo aa aa!
	lion.Accept(speak)    // Roaaar!
	dolphin.Accept(speak) // Tuut tuttu tuutt!
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

    void shout() {
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

// -----------------------

Monkey monkey = new Monkey();
Lion lion = new Lion();
Dolphin dolphin = new Dolphin();

Speak speak = new Speak();

monkey.accept(speak);   // Ooh oo aa aa!
lion.accept(speak);     // Roaaar!
dolphin.accept(speak);  // Tuut tutt tuttt!

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

Jump jump = new Jump();

monkey.accept(speak);   // Ooh oo aa aa!
monkey.accept(jump);    // Jumped 20 feet high! on to the tree!

lion.accept(speak);     // Roaaar!
lion.accept(jump);      // Jumped 7 feet! Back on the ground!

dolphin.accept(speak);  // Tuut tutt tuutt!
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
        std::cout << "Tuut tutt tuttt!" << std::endl;
    }

    void accept(AnimalOperation& operation) override {
        operation.visitDolphin(*this);
    }
};

// Concrete visitor
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

// ----------------------------

int main() {
    Monkey monkey;
    Lion lion;
    Dolphin dolphin;

    Speak speak;

    monkey.accept(speak);   // Ooh oo aa aa!
    lion.accept(speak);     // Roaaar!
    dolphin.accept(speak);  // Tuut tutt tuttt!
    return 0;
}
```

</div>

</details>

<br>

---

<div align="center">

## استراتژی (Strategy) 💡

</div>

<div align="center">
🧠 <b>مثال دنیای واقعی: انتخاب روش (بسته به شرایط)</b>
</div>

فرض کن می‌خوای یه کار رو انجام بدی، ولی چند راه مختلف برای انجام دادنش داری.
مثلاً توی مرتب‌سازی داده‌ها:
*   وقتی دیتاست کوچیکه، یه روش ساده مثل `Bubble Sort` شاید کافی باشه.
*   وقتی دیتاست بزرگه، یه روش سریع‌تر مثل `Quick Sort` بهتره.

تو نمی‌خوای کل برنامه‌ت رو به `if/else`‌های طولانی تبدیل کنی که هر بار یکی گفت «روش جدید هم اضافه کن»، همه‌جا رو دستکاری کنی.
پس الگوریتم‌ها رو جدا می‌کنی و هر لحظه هر کدوم رو خواستی می‌ذاری داخل سیستم. ✅

💡 **به زبون ساده:**
> این پترن می‌گه: **«چند تا الگوریتم قابل تعویض داشته باش و انتخابشون رو بنداز به زمان اجرا.»**

ویکی‌پدیا:

<div dir="ltr">

> In computer programming, the strategy pattern (also known as the policy pattern) is a behavioural software design
> pattern that enables an algorithm's behavior to be selected at runtime.

</div>

**مثال برنامه‌نویسی**

می‌خوایم یک سرویس پیاده‌سازی کنیم که با توجه به داده‌هامون تصمیم بگیریم از یک نوع از مرتب سازی استفاده کنیم!

یک کلاس بسازیم که وظیفه‌اش مدیریت این استراتژی‌ها باشه.

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class SortStrategy:
    def sort(self, dataset):
        pass


class BubbleSortStrategy(SortStrategy):
    def sort(self, dataset):
        print('Sorting using bubble sort')

        return dataset


class QuickSortStrategy(SortStrategy):
    def sort(self, dataset):
        print('Sorting using quick sort')
        return dataset


class Sorter:
    _sorter = None

    def __init__(self, sorter):
        self._sorter = sorter

    def sort(self, dataset):
        return self._sorter.sort(dataset)


# ----------------------------

dataset = [1, 5, 4, 3, 2, 8]

sorter = Sorter(BubbleSortStrategy())
sorter.sort(dataset)

sorter = Sorter(QuickSortStrategy())
sorter.sort(dataset)
```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface SortStrategy {
    sort(dataset: any[]): any[];
}

class BubbleSortStrategy implements SortStrategy {
    sort(dataset: any[]): any[] {
        console.log("Sorting using bubble sort");
        return dataset;
    }
}

class QuickSortStrategy implements SortStrategy {
    sort(dataset: any[]): any[] {
        console.log("Sorting using quick sort");
        return dataset;
    }
}

class Sorter {
    private sorter: SortStrategy;

    constructor(sorter: SortStrategy) {
        this.sorter = sorter;
    }

    sort(dataset: any[]): any[] {
        return this.sorter.sort(dataset);
    }
}

// ----------------------------

const dataset = [1, 5, 4, 3, 2, 8];

const sorter = new Sorter(new BubbleSortStrategy());
sorter.sort(dataset);

const sorter2 = new Sorter(new QuickSortStrategy());
sorter2.sort(dataset);
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class BubbleSortStrategy {
    sort(dataset) {
        console.log("Sorting using bubble sort");
        return dataset;
    }
}

class QuickSortStrategy {
    sort(dataset) {
        console.log("Sorting using quick sort");
        return dataset;
    }
}

class Sorter {
    constructor(sorter) {
        this.sorter = sorter;
    }

    sort(dataset) {
        return this.sorter.sort(dataset);
    }
}

const dataset = [1, 5, 4, 3, 2, 8];

const sorter = new Sorter(new BubbleSortStrategy());
sorter.sort(dataset);

const sorter2 = new Sorter(new QuickSortStrategy());
sorter2.sort(dataset);
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

interface ISortStrategy
{
  List<int> Sort(List<int> dataset);
}

class BubbleSortStrategy : ISortStrategy
{
  public List<int> Sort(List<int> dataset)
  {
    Console.WriteLine("Sorting using Bubble Sort !");
    return dataset;
  }
}

class QuickSortStrategy : ISortStrategy
{
  public List<int> Sort(List<int> dataset)
  {
    Console.WriteLine("Sorting using Quick Sort !");
    return dataset;
  }
}

class Sorter
{
  private readonly ISortStrategy mSorter;

  public Sorter(ISortStrategy sorter)
  {
    mSorter = sorter;
  }

  public List<int> Sort(List<int> unSortedList)
  {
    return mSorter.Sort(unSortedList);
  }
}

// ----------------------------

var unSortedList = new List<int> { 1, 10, 2, 16, 19 };

var sorter = new Sorter(new BubbleSortStrategy());
sorter.Sort(unSortedList); // // Output : Sorting using Bubble Sort !

sorter = new Sorter(new QuickSortStrategy());
sorter.Sort(unSortedList); // // Output : Sorting using Quick Sort !

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface SortStrategyInterface {
  public function sort($dataset);
}

class BubbleSortStrategy implements SortStrategyInterface {
  public function sort($dataset) {
    echo "Sorting using Bubble Sort !\n";
    return $dataset;
  }
}

class QuickSortStrategy implements SortStrategyInterface {
  public function sort($dataset) {
    echo "Sorting using Quick Sort !\n";
    return $dataset;
  }
}

class Sorter {
  private $mSorter;

  public function __construct(SortStrategyInterface $sorter) {
    $this->mSorter = $sorter;
  }

  public function sort($unSortedList) {
    return $this->mSorter->sort($unSortedList);
  }
}

$unSortedList = [1, 10, 2, 16, 19];

$sorter = new Sorter(new BubbleSortStrategy());
$sorter->sort($unSortedList); // Output : Sorting using Bubble Sort !

$sorter = new Sorter(new QuickSortStrategy());
$sorter->sort($unSortedList); // Output : Sorting using Quick Sort !

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

// SortStrategy is the interface that defines the sorting strategy
type SortStrategy interface {
	Sort(dataset []int) []int
}

// BubbleSortStrategy implements the SortStrategy interface
type BubbleSortStrategy struct{}

func (b *BubbleSortStrategy) Sort(dataset []int) []int {
	fmt.Println("Sorting using bubble sort")
	// Implement bubble sort logic here (omitted for brevity)
	return dataset
}

// QuickSortStrategy implements the SortStrategy interface
type QuickSortStrategy struct{}

func (q *QuickSortStrategy) Sort(dataset []int) []int {
	fmt.Println("Sorting using quick sort")
	// Implement quick sort logic here (omitted for brevity)
	return dataset
}

// Sorter is the context that uses a sorting strategy
type Sorter struct {
	sorter SortStrategy
}

func NewSorter(sorter SortStrategy) *Sorter {
	return &Sorter{sorter: sorter}
}

func (s *Sorter) Sort(dataset []int) []int {
	return s.sorter.Sort(dataset)
}

func main() {
	dataset := []int{1, 5, 4, 3, 2, 8}

	sorter := NewSorter(&BubbleSortStrategy{})
	sorter.Sort(dataset)

	sorter = NewSorter(&QuickSortStrategy{})
	sorter.Sort(dataset)
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface SortStrategy {
    List<Integer> sort(List<Integer> dataset);
}

class BubbleSortStrategy implements SortStrategy {

    @Override
    public List<Integer> sort(List<Integer> dataset) {
        System.out.println("Sorting by Bubble sort!");
        return dataset;
    }
}

class QuickSortStrategy implements SortStrategy {

    @Override
    public List<Integer> sort(List<Integer> dataset) {
        System.out.println("Sorting by Quick sort!");
        return dataset;
    }
}

class Sorter {
    private SortStrategy sorter;

    public Sorter(SortStrategy sorter) {
        this.sorter = sorter;
    }

    public List<Integer> sort(List<Integer> unSortedList) {
        return sorter.sort(unSortedList);
    }
}

// ----------------------------

List<Integer> unSortedList = List.of(1, 10, 2, 16, 19);

Sorter sorter = new Sorter(new BubbleSortStrategy());
sorter.sort(unSortedList); // Sorting by Bubble sort!

sorter = new Sorter(new QuickSortStrategy());
sorter.sort(unSortedList); // Sorting by Quick sort!
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <vector>

class SortStrategy {
public:
    virtual ~SortStrategy() = default;
    virtual std::vector<int> sort(std::vector<int>& dataset) = 0;
};

class BubbleSortStrategy : public SortStrategy {
public:
    std::vector<int> sort(std::vector<int>& dataset) override {
        std::cout << "Sorting using bubble sort" << std::endl;
        return dataset;
    }
};

class QuickSortStrategy : public SortStrategy {
public:
    std::vector<int> sort(std::vector<int>& dataset) override {
        std::cout << "Sorting using quick sort" << std::endl;
        return dataset;
    }
};

class Sorter {
private:
    SortStrategy* strategy;

public:
    Sorter(SortStrategy* s) : strategy(s) {}

    std::vector<int> sort(std::vector<int>& dataset) {
        return strategy->sort(dataset);
    }
};

// ----------------------------

int main() {
    std::vector<int> dataset = {1, 5, 4, 3, 2, 8};

    BubbleSortStrategy bubbleSort;
    Sorter sorter(&bubbleSort);
    sorter.sort(dataset);

    QuickSortStrategy quickSort;
    Sorter sorter2(&quickSort);
    sorter2.sort(dataset);
    return 0;
}
```

</div>

</details>

<br>

---

<div align="center">

## حالت (State) 💢

</div>

<div align="center">
⌨️ <b>مثال دنیای واقعی: حالت تایپ (عادی/حروف بزرگ/حروف کوچک)</b>
</div>

فرض کن داری تایپ می‌کنی.
یه وقت می‌خوای همه‌چی حروف بزرگ باشه (مثل وقتی `Caps Lock` رو روشن می‌کنی)، یه وقت می‌خوای همه‌چی حروف کوچک باشه، یه وقت هم حالت معمولی.

نکته اینه که «کاری که انجام می‌دید» یکیه (داری متن می‌نویسی) ولی **رفتار خروجی** با توجه به حالت فعلی عوض می‌شه.
این دقیقاً همون چیزیه که State می‌گه: به جای اینکه توی یک کلاس بزرگ پر از شرط بنویسی، حالت‌ها رو به شکل آبجکت‌های جدا نگه داری و هر وقت لازم شد state رو عوض کنی. 🧩

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

**مثال برنامه‌نویسی**

می‌خوایم یک ادیتور بسازیم که قابلیت‌هایی مثل این داشته باشه که متنی که تایپ می‌شه حروف کوچیک باشه یا همش حروف بزرگ باشه یا
معمولی باشه!

اول بیاید کلاس‌هامون بر پایه الگوی State رو بسازیم:

بعد ادیتور رو بسازیم و بهش یاد بدیم این کلاس‌ها رو توی خودش نگه داره و ازشون استفاده کنه!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class WritingState:
    def write(self, words):
        pass


class UpperCase(WritingState):
    def write(self, words):
        print(words.upper())


class LowerCase(WritingState):
    def write(self, words):
        print(words.lower())


class DefaultText(WritingState):
    def write(self, words):
        print(words)


class TextEditor():
    _state = None

    def __init__(self, state):
        self._state = state

    def setState(self, state):
        self._state = state

    def write(self, words):
        self._state.write(words)


# ----------------------------

editor = TextEditor(DefaultText())
editor.write('First Line')

editor.setState(UpperCase())

editor.write('Second Line')
editor.write('Third Line')

editor.setState(LowerCase())

editor.write('Fourth Line')
editor.write('Fifth Line')


'''
Output will be
==============
First Line
SECOND LINE
THIRD LINE
fourth line
fifth line
'''

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface WritingState {
    write(words: string): void;
}

class UpperCase implements WritingState {
    write(words: string): void {
        console.log(words.toUpperCase());
    }
}

class LowerCase implements WritingState {
    write(words: string): void {
        console.log(words.toLowerCase());
    }
}

class DefaultText implements WritingState {
    write(words: string): void {
        console.log(words);
    }
}

class TextEditor {
    private state: WritingState;

    constructor(state: WritingState) {
        this.state = state;
    }

    setState(state: WritingState) {
        this.state = state;
    }

    type(words: string) {
        this.state.write(words);
    }
}

// ----------------------------

const editor = new TextEditor(new DefaultText());
editor.type("First Line"); // First Line

editor.setState(new UpperCase());

editor.type("Second Line"); // SECOND LINE
editor.type("Third Line"); // THIRD LINE

editor.setState(new LowerCase());

editor.type("Fourth Line"); // fourth line
editor.type("Fifth Line"); // fifth line
```

</div>
</details>

<details>
<summary>JavaScript</summary>
<div dir="ltr">

```javascript
class UpperCase {
    write(words) {
        console.log(words.toUpperCase());
    }
}

class LowerCase {
    write(words) {
        console.log(words.toLowerCase());
    }
}

class DefaultText {
    write(words) {
        console.log(words);
    }
}

class TextEditor {
    constructor(state) {
        this.state = state;
    }

    setState(state) {
        this.state = state;
    }

    type(words) {
        this.state.write(words);
    }
}


const editor = new TextEditor(new DefaultText());
editor.type("First Line");

editor.setState(new UpperCase());
editor.type("Second Line");
editor.type("Third Line");

editor.setState(new LowerCase());
editor.type("Fourth Line");
editor.type("Fifth Line")
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

interface IWritingState {

  void Write(string words);

}

class UpperCase : IWritingState
{
  public void Write(string words)
  {
    Console.WriteLine(words.ToUpper());
  }
}

class LowerCase : IWritingState
{
  public void Write(string words)
  {
    Console.WriteLine(words.ToLower());
  }
}

class DefaultText : IWritingState
{
  public void Write(string words)
  {
    Console.WriteLine(words);
  }
}


class TextEditor {

  private IWritingState mState;

  public TextEditor()
  {
    mState = new DefaultText();
  }

  public void SetState(IWritingState state)
  {
    mState = state;
  }

  public void Type(string words)
  {
    mState.Write(words);
  }

}


// ----------------------------

var editor = new TextEditor();

editor.Type("First line");

editor.SetState(new UpperCase());

editor.Type("Second Line");
editor.Type("Third Line");

editor.SetState(new LowerCase());

editor.Type("Fourth Line");
editor.Type("Fifthe Line");

// Output:
// First line
// SECOND LINE
// THIRD LINE
// fourth line
// fifth line

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```php
interface WritingStateInterface {
  public function write(string $words);
}

class UpperCase implements WritingStateInterface
{
  public function write(string $words)
  {
    echo strtoupper($words) . "\n";
  }
}

class LowerCase implements WritingStateInterface
{
  public function write(string $words)
  {
    echo strtolower($words) . "\n";
  }
}

class DefaultText implements WritingStateInterface
{
  public function write(string $words)
  {
    echo $words . "\n";
  }
}

class TextEditor {
  private WritingStateInterface $state;

  public function __construct()
  {
    $this->state = new DefaultText();
  }

  public function setState(WritingStateInterface $state)
  {
    $this->state = $state;
  }

  public function type(string $words)
  {
    $this->state->write($words);
  }
}

$editor = new TextEditor();

$editor->type("First line");

$editor->setState(new UpperCase());

$editor->type("Second Line");
$editor->type("Third Line");

$editor->setState(new LowerCase());

$editor->type("Fourth Line");
$editor->type("Fifth Line");

// Output:
// First line
// SECOND LINE
// THIRD LINE
// fourth line
// fifth line

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
	"strings"
)

// WritingState interface
type WritingState interface {
	Write(words string)
}

// UpperCase struct
type UpperCase struct{}

// Write for UpperCase
func (u *UpperCase) Write(words string) {
	fmt.Println(strings.ToUpper(words))
}

// LowerCase struct
type LowerCase struct{}

// Write for LowerCase
func (l *LowerCase) Write(words string) {
	fmt.Println(strings.ToLower(words))
}

// DefaultText struct
type DefaultText struct{}

// Write for DefaultText
func (d *DefaultText) Write(words string) {
	fmt.Println(words)
}

// TextEditor struct
type TextEditor struct {
	state WritingState
}

// NewTextEditor constructor
func NewTextEditor(state WritingState) *TextEditor {
	return &TextEditor{state: state}
}

// SetState method for TextEditor
func (te *TextEditor) SetState(state WritingState) {
	te.state = state
}

// Type method for TextEditor
func (te *TextEditor) Type(words string) {
	te.state.Write(words)
}

func main() {
	editor := NewTextEditor(&DefaultText{})
	editor.Type("First Line") // First line

	editor.SetState(&UpperCase{})
	editor.Type("Second Line") // SECOND LINE
	editor.Type("Third Line")  // THIRD LINE

	editor.SetState(&LowerCase{})
	editor.Type("Fourth Line") // fourth line
	editor.Type("Fifth Line")  // fifth line
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface WritingState {
    void write(String words);
}

class UpperCase implements WritingState {
    public void write(String words) {
        System.out.println(words.toUpperCase());
    }
}

class LowerCase implements WritingState {
    public void write(String words) {
        System.out.println(words.toLowerCase());
    }
}

class DefaultText implements WritingState {
    public void write(String words) {
        System.out.println(words);
    }
}

class TextEditor {
    private WritingState state;

    public TextEditor() {
        state = new DefaultText();
    }

    public void setState(WritingState state) {
        this.state = state;
    }

    public void type(String words) {
        state.write(words);
    }
}

// ----------------------------

TextEditor editor = new TextEditor();

editor.type("First line"); // First line

editor.setState(new UpperCase());
editor.type("Second line"); // SECOND LINE
editor.type("Third Line");  // THIRD LINE

editor.setState(new LowerCase());
editor.type("Fourth line"); // fourth line
editor.type("FIFTH Line");  // fifth line
```

</div>

</details>

<details>
<summary>C++</summary>

<div dir="ltr">

```cpp
#include <iostream>
#include <string>
#include <algorithm>

class WritingState {
public:
    virtual ~WritingState() = default;
    virtual void write(const std::string& words) = 0;
};

class UpperCase : public WritingState {
public:
    void write(const std::string& words) override {
        std::string upper = words;
        std::transform(upper.begin(), upper.end(), upper.begin(), ::toupper);
        std::cout << upper << std::endl;
    }
};

class LowerCase : public WritingState {
public:
    void write(const std::string& words) override {
        std::string lower = words;
        std::transform(lower.begin(), lower.end(), lower.begin(), ::tolower);
        std::cout << lower << std::endl;
    }
};

class DefaultText : public WritingState {
public:
    void write(const std::string& words) override {
        std::cout << words << std::endl;
    }
};

class TextEditor {
private:
    WritingState* state;

public:
    TextEditor() : state(new DefaultText()) {}
    ~TextEditor() { delete state; }

    void setState(WritingState* newState) {
        delete state;
        state = newState;
    }

    void type(const std::string& words) {
        state->write(words);
    }
};

// ----------------------------

int main() {
    TextEditor editor;

    editor.type("First line");  // First line

    editor.setState(new UpperCase());
    editor.type("Second line"); // SECOND LINE
    editor.type("Third line");  // THIRD LINE

    editor.setState(new LowerCase());
    editor.type("Fourth line"); // fourth line
    editor.type("Fifth line");  // fifth line
    return 0;
}
```

</div>

</details>

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

**مثال برنامه‌نویسی**

فرض کن ما یک زیرساخت برای ساخت اپلیکیشن‌های گوشی نیاز داریم!

خب مراحل تقریبا مشخصه و فقط ما باید مراحل build, lint , test و deploy رو پیاده‌سازی کنیم!

بعد باید پیاده‌سازی برای اندروید و آی او اس رو بسازیم.

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
<summary>Typescript</summary>
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



const iosBuilder = new IosBuilder();
iosBuilder.build();
```

</div>
</details>

<details>
<summary>C#</summary>

<div dir="ltr">

```csharp

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

  public function lnt() {
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
    public void assemble() {
        System.out.println("Assembling android build");
    }

    @Override
    public void deploy() {
        System.out.println("Deploying android build");
    }

    @Override
    public void lint() {
        System.out.println("Linting android code");
    }

    @Override
    public void test() {
        System.out.println("Running android tests");
    }
}

class IOSBuilder extends Builder {

    @Override
    public void assemble() {
        System.out.println("Assembling iOS build");
    }

    @Override
    public void deploy() {
        System.out.println("Deploying iOS build");
    }

    @Override
    public void lint() {
        System.out.println("Linting iOS code");
    }

    @Override
    public void test() {
        System.out.println("Running iOS tests");
    }
}

// ----------------------------

AndroidBuilder androidBuilder = new AndroidBuilder();
androidBuilder.build();
// Running android tests
// Linting android code
// Assembling android build
// Deploying android build

IOSBuilder iOSBuilder = new IOSBuilder();
iOSBuilder.build();
// Running iOS tests
// Linting iOS code
// Assembling iOS build
// Deploying iOS build
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

    std::cout << std::endl;

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
- مثال‌ها رو بهبود ببخشید و با issue و یا pull request به اشتراک بسازی!
- اگه تجربه عملی ای با هر الگو داری اون رو به مثال‌ها اضافه کنی!
- با ⭐ به پروژه از من و این ریپو حمایت کنی و باعث دیده شدنش بشی!

</div>

<div align="center">

## مشارکت کنندگان

</div>

<div align="right">

- امیر عزیز که زحمت مثال‌های TypeScript رو کشید.([amirmalekian](https://github.com/amirmalekian))
- رضا عزیز که زحمت مثال‌های #C رو کشید.([RezaMansouri70](https://github.com/RezaMansouri70))
- صالح عزیز که زحمت مثال‌های PHP رو کشید.([salehhashemi1992](https://github.com/salehhashemi1992))
- عاطفه عزیز که زحمت مثال‌های Golang رو کشید.([atefeh-komeyli](https://github.com/atefeh-komeyli))
- محمد عزیز که زحمت مثال‌های Java رو کشید.([Mohammad-Masoomi-Homayoun](https://github.com/Mohammad-Masoomi-Homayoun))
- سما عزیز که زحمت مثال‌های JavaScript رو کشید.([samazzz](https://github.com/samazzz))
- حمیدرضا عزیز که زحمت مثال‌های C++ رو کشید.([hamiikalhor](https://github.com/hamiikalhor))
- مهسا، محمد، سجاد و محسن عزیز که زحمت بهبود کد هارو کشیدند.([MahsaMahdavian](https://github.com/MahsaMahdavian) / [MohammadMMoniri](https://github.com/MohammadMMoniri) / [ssmns](https://github.com/ssmns) / [Serajian](https://github.com/Serajian))

</div>

</div>
