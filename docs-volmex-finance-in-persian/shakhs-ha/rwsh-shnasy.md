# روش شناسی

در یک زمان معین، شاخص‌های volmex.finance در هشت گزینه که معیارهای زیر را برآورده می‌کنند فاکتور می‌گیرند:                                                                &#x20;

* Out-of-the-money call and put closest to 15 days from expiration
* In-the-money call and put closest to 15 days from expiration&#x20;
* In-the-money call and put closest to 45 days from expiration
* Out-of-the-money call and put closest to 45 days from expiration



داده‌های گزینه‌ها در زمان واقعی از [Deribit](https://www.deribit.com)، صرافی پیشرو گزینه‌های رمزنگاری، منبع می‌شوند. با اجرای داده های مربوطه از طریق [فرمول معکوس بلک شولز](https://en.wikipedia.org/wiki/Black%E2%80%93Scholes\_model)، یک خروجی تولید می شود (مقدار شاخص فعلی)، که هدف آن اندازه گیری نوسانات ضمنی 30 روزه دارایی اساسی (به عنوان مثال ETH، BTC، و غیره) است. خروجی شاخص میانگین IV ها است.                                                                                                                                                      &#x20;

قیمت متوسط ​​گزینه ها در محاسبه استفاده می شود.                                                                                       &#x20;
