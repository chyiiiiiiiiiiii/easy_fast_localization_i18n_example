# easy_fast_localization_i18n_example

使用 `easy_localization` 套件實作 Flutter i18n，其中 `easy_localization_generator` 套件負責取得Google sheet並生成字串檔與翻譯檔，接著透過 `easy_localization_loader` 套件存取翻譯檔，最後就能依據設置地區顯示對應語言字串

## Demo
![Google Sheet](demo/google_sheet.png)
![csv](demo/csv.png)
![entry class](demo/entry.png)
![generated code](demo/gen_code.png)
![final](demo/final.gif)

## Package
- [easy_localization](https://pub.dev/packages/easy_localization)
- [easy_localization_loader](https://pub.dev/packages/easy_localization_loader)
- [easy_localization_generator](https://pub.dev/packages/easy_localization_generator)

## Optimization
``` dart
// Original: Official package
I18n.title.tr()

// New: My version
I18n.title

```
官方套件在使用多語系字串時都需要在後方額外加上`tr()`，覺得有點多餘，當然如果字串裡面要帶參數更新文字或是其他操作當然不可避免。而這邊我優化了 `easy_localization_generator` 套件，目前版本已Merged，大大改善使用方式，可生成自帶命名參數的函式，讓開發者不用再想需要設置什麼Key，直接輕鬆帶入Value即可，另外plural使用方式也有調整。大家如果想提升開發效率的話就使用它吧！

## Usage
### Simple text
``` dart
I18n.title
```
### Text with args
``` dart
Text(
  Strings.msg(
    name: 'Jack',
    type: 'Hot',
  ),
),
```
### Text with plural
1. no named arg version
<img src="./demo/plural_1.png" />

``` dart
Text(Strings.amount(counter))
```

2. named arg version (recommend)
<img src="./demo/plural_2.png" />

``` dart
Text(
  Strings.clicked(
    counter,
    count: counter.toString(),
  ),
),
```
