---
description: 'Daha fazla bilgi: sayısal değer Işlevlerine dize'
title: Sayısal Değer İşlevleri Dizesi
ms.date: 11/04/2016
api_location:
- msvcr80.dll
- msvcr110.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstoui64
- _tcstoi64
helpviewer_keywords:
- parsing, numeric strings
- string conversion, to numeric values
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
ms.openlocfilehash: f560c83c8ae8d510b70804540e5360982770773c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339572"
---
# <a name="string-to-numeric-value-functions"></a>Sayısal Değer İşlevleri Dizesi

- [strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)

- [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)

- [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)

- [_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)

- [_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)

## <a name="remarks"></a>Açıklamalar

**Strtod** ailesindeki her bir işlev, null ile sonlandırılmış bir dizeyi sayısal bir değere dönüştürür. Kullanılabilir işlevler aşağıdaki tabloda listelenmiştir.

|İşlev|Açıklama|
|--------------|-----------------|
|`strtod`|Dizeyi çift duyarlıklı kayan noktalı değere Dönüştür|
|`strtol`|Dizeyi Long Integer 'a Dönüştür|
|`strtoul`|Dizeyi işaretsiz uzun tamsayıya Dönüştür|
|`_strtoi64`|Dizeyi 64-bit tamsayıya Dönüştür **`__int64`**|
|`_strtoui64`|Dizeyi işaretsiz 64-bit tamsayıya Dönüştür **`__int64`**|

`wcstod`,, ve, sırasıyla,,, `wcstol` `wcstoul` `_wcstoi64` `strtod` `strtol` `strtoul` ve ' nin geniş karakterli sürümleridir `_strtoi64` . Bu geniş karakter işlevlerinin her birine yönelik dize bağımsız değişkeni, geniş karakterli bir dizedir; Her işlev, başka bir şekilde tek baytlık karakteriyle aynı şekilde davranır.

`strtod`İşlev iki bağımsız değişkeni alır: ilki giriş dizesidir ve ikinci karakter işaretçisi, dönüştürme işlemini sonlandırır. `strtol`, `strtoul` , **_strtoi64** ve **_strtoui64** dönüştürme işleminde kullanılacak sayı temeli olarak üçüncü bir bağımsız değişken alır.

Giriş dizesi, belirtilen türden sayısal bir değer olarak yorumlanabilen bir karakter dizisidir. Her işlev, bir sayının parçası olarak tanıyamadığı ilk karakterde dizeyi okumayı durduruyor. Bu, Sonlandırıcı null karakteri olabilir. ,, Ve için, `strtol` `strtoul` `_strtoi64` `_strtoui64` Bu sonlandırma karakteri Kullanıcı tarafından sağlanan sayı tabanından daha büyük veya buna eşit olan ilk sayısal karakter de olabilir.

Bir dönüştürme bitiş karakteri için Kullanıcı tarafından sağlanan işaretçi, çağrı zamanında **null** olarak ayarlanmamışsa, taramayı durduran karaktere yönelik bir işaretçi burada depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), dize işaretçisinin değeri o adreste saklanır.

`strtod` aşağıdaki biçimde bir dize bekler:

[*boşluk*] [*imzala*] [`digits`] [**.**`digits`] [{**d** &#124; **d** &#124; **e** &#124; **e**} [*oturum açma*] `digits` ]

Boşluk veya sekme karakterlerinden oluşan bir *boşluk* , yoksayılan karakter içerebilir; *işareti* artı ( **+** ) ya da eksi ( **-** ); ve `digits` bir veya daha fazla ondalık basamak. Taban karakterinden önce bir basamak görünmezse, en az bir sayı, taban karakterinden sonra görünmelidir. Ondalık basamakların ardından, giriş harfinden (**d**, **d**, **e** veya **e**) ve isteğe bağlı olarak işaretli bir tamsayıdan oluşan bir üs gelebilir. Ne bir üs bölümü ne de bir taban karakteri görünmüyorsa, dizedeki son basamağı izlemek için bir taban karakteri varsayılır. Bu forma uymayan ilk karakter taramayı durduruyor.

`strtol`,, `strtoul` `_strtoi64` Ve `_strtoui64` işlevleri aşağıdaki biçimde bir dize bekler:

[*boşluk*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [ `digits` ]

Temel bağımsız değişken 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. 0 ise, temeli belirlemekte, dönüştürme sonu işaretçisi tarafından başvurulan başlangıç karakterleri kullanılır. İlk karakter 0 ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır; Aksi takdirde, ondalık sayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arasında değerler atanır; yalnızca atanmış değerlerine *tabandan* küçük olan harflerine izin verilir. `strtoul` ve `_strtoui64` artı ( **+** ) ya da eksi ( **-** ) işareti ön ekine izin verir; baştaki eksi işareti, dönüş değerinin nelenmiş olduğunu gösterir.

Çıkış değeri `LC_NUMERIC` yerel ayarın kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) . **_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

Bu işlevler tarafından döndürülen değer taşma veya yetersiz durumuna neden olduğunda ya da dönüştürme mümkün olmadığında, özel durum değerleri gösterildiği gibi döndürülür:

|İşlev|Koşul|Döndürülen değer|
|--------------|---------------|--------------------|
|`strtod`|Taşma|+/- `HUGE_VAL`|
|`strtod`|Yetersiz veya dönüştürme yok|0|
|`strtol`|+ Taşma|**LONG_MAX**|
|`strtol`|-Taşma|**LONG_MIN**|
|`strtol`|Yetersiz veya dönüştürme yok|0|
|`_strtoi64`|+ Taşma|**_I64_MAX**|
|`_strtoi64`|-Taşma|**_I64_MIN**|
|`_strtoi64`|Dönüştürme yok|0|
|`_strtoui64`|Taşma|**_UI64_MAX**|
|`_strtoui64`|Dönüştürme yok|0|

**_I64_MAX**, _ **I64_MIN** ve **_UI64_MAX** sınırlar. H içinde tanımlanır.

`wcstod`,,, `wcstol` `wcstoul` ve, sırasıyla,,, `_wcstoi64` `_wcstoui64` ve ' nin geniş karakterli sürümleridir `strtod` `strtol` `strtoul` `_strtoi64` `_strtoui64` ; Bu geniş karakter işlevlerinin her birine bir dönüştürme sonu bağımsız değişkeninin işaretçisi geniş karakterli bir dizedir. Aksi takdirde, bu geniş karakter işlevlerinin her biri, tek baytlık karakter karşılığına benzer şekilde davranır.

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../c-runtime-library/locale.md)<br/>
[Multibyte-Character sıralarının yorumu](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Kayan nokta desteği](../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)
