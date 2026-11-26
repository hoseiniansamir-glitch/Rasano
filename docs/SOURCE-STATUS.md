# وضعیت سورس در مخزن

این مخزن نقش «مرکز مستندات و پیگیری نقشهٔ راه» را دارد و سورس متنی پروژه در آن نگهداری می‌شود. تحویل کامل و قابل ساخت همیشه بستهٔ **`Rasano-A29.0-DEV3-source.zip`** است.

## در مخزن موجود است

- `README.md` — معرفی پروژه، وضعیت نسخه‌ها و نقشهٔ راه
- `docs/ROADMAP.md` — نقشهٔ راه سه‌فازی (۱۷ تسک RM-*)
- `docs/SOURCE-STATUS.md` — همین فایل
- فایل‌های Gradle ریشه و app، `AndroidManifest.xml`، `assets/messengers.json`
- تمام منابع XML متنی (drawable، mipmap-anydpi، values با ۴ زبان، xml/)
- سورس Kotlin همهٔ ماژول‌ها به‌جز فایل بزرگ جدول زیر

## در مخزن نیست (و چرا)

| مورد | دلیل | جایگزین |
|---|---|---|
| `app/src/main/java/com/example/socialshare/editor/video/VideoEditorScreen.kt` (~۳۷۵KB) | محدودیت حجم انتقال از طریق رابط افزونهٔ GitHub | بستهٔ DEV3 zip؛ یا آپلود مستقیم از وب |
| ۲۵ فایل PNG — آیکون لانچر در ۵ چگالی (۱۰ فایل)، `ic_launcher_fg.png`، `watermark_rasano.png` و ۱۳ آیکون پیام‌رسان در `drawable-nodpi` | رابط افزونه فقط محتوای متنی را منتقل می‌کند و فایل دودویی را خراب می‌کند | بستهٔ DEV3 zip؛ یا آپلود مستقیم |
| `signing/socialshare.keystore` | عمداً — کلید امضا نباید در مخزن عمومی باشد | نگهداری محلی + پشتیبان امن |
| `local.properties` | وابسته به ماشین ساخت؛ Android Studio خودش می‌سازد | تولید خودکار |

## تکمیل مخزن با آپلود وب

فایل‌های جدول بالا را می‌توان مستقیم در GitHub آپلود کرد (**Add file → Upload files**) و در همان مسیرهای ذکرشده قرار داد. پس از آن مخزن قابل ساخت کامل خواهد بود:

```bash
gradle assembleRelease   # پیش‌نیاز: JDK 17، Android SDK (platform 35، build-tools 35)
# خروجی: app/build/outputs/apk/release/app-release.apk
```
