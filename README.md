# easy_fast_localization_i18n_example

Use the `easy_localization` package to implement Flutter i18n, where the `easy_localization_generator` package is responsible for obtaining Google sheets and generating string files and translation files, and then accessing the translation files through the `easy_localization_loader` package, and finally displaying the corresponding language strings according to the set region.

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
Initially, when the official kit translate multilingual strings, it added `tr()` at the end, which was a bit unnecessary. Of course, it is inevitable if the string contains parameters to update the text or other operations. Here I have optimized the `easy_localization_generator` package. The current version has been merged, which greatly improves the way of use. It can generate functions with named parameters so that developers no longer need to think about what Key needs to be set, and can directly set Value easily. In addition, The usage of the plural has also been adjusted. If you want to improve development efficiency, use it!

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

## Contribute
- You can star and share with other developers if you feel good and learn something from this repository.
- If you have some ideas, please discuss them with me or commit PR.

## More of me
[![Medium](https://img.shields.io/badge/medium-fff?style=for-the-badge&logo=medium&logoColor=black)](https://yiichenhi.medium.com)
[![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yiichenhi/) 
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/yiichenhi)
[![instagram](https://img.shields.io/badge/instagram-C6317F?style=for-the-badge&logo=instagram&logoColor=white)](http://instagram.com/flutterluvr.yii/)

## Donate and encourage me
[![BuyMeACoffee][buy_me_a_coffee_badge]][buy_me_a_coffee]

<!-- Links -->
[buy_me_a_coffee]: https://www.buymeacoffee.com/yiichenhi
[buy_me_a_coffee_badge]: https://img.buymeacoffee.com/button-api/?text=Sponsor&emoji=&slug=yiichenhi&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff&size=64
