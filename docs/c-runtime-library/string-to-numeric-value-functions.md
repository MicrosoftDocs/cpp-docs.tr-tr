---
title: Sayısal Değer İşlevleri Dizesi
ms.date: 11/04/2016
apilocation:
- msvcr80.dll
- msvcr110.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- _tcstoui64
- _tcstoi64
helpviewer_keywords:
- parsing, numeric strings
- string conversion, to numeric values
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
ms.openlocfilehash: d3e53c665378efdd63a373027f4edd6b7fb90ad3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544579"
---
# <a name="string-to-numeric-value-functions"></a>Sayısal Değer İşlevleri Dizesi

- [strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)

- [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)

- [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)

- [_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)

- [_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)

## <a name="remarks"></a>Açıklamalar

Her işlev **strtod** ailesi null ile sonlandırılmış bir dize sayısal bir değere dönüştürür. Aşağıdaki tabloda kullanabileceğiniz işlevler listelenmiştir.

|İşlev|Açıklama|
|--------------|-----------------|
|`strtod`|Çift duyarlıklı kayan noktalı değeri dize dönüştürme|
|`strtol`|Dizeye uzun tamsayı dönüştürün|
|`strtoul`|Dizeyi işaretsiz uzun tamsayı dönüştürme|
|`_strtoi64`|64 bit dize dönüştürme `__int64` tamsayı|
|`_strtoui64`|Dönüştürme dizesi 64-bit işaretsiz `__int64` tamsayı|

`wcstod`, `wcstol`, `wcstoul`, ve `_wcstoi64` geniş karakterli sürümleridir `strtod`, `strtol`, `strtoul`, ve `_strtoi64`sırasıyla. Bu geniş karakter işlevlerin her biri için dize bağımsız değişkeni geniş karakterli bir dizedir; Her işlev tek baytlık karakterlerdir çözümlemesiyle Aksi halde aynı şekilde davranır.

`strtod` İşlevi iki bağımsız değişkeni alır: ilk giriş dize ve karakter işaretçisine ikinci sona erdiği dönüştürme işlemi. `strtol`, `strtoul`, **_strtoi64** ve **_strtoui64** dönüştürme işleminde kullanılacak sayı tabanı olarak üçüncü bir bağımsız değişken alın.

Giriş dizesi belirtilen türde bir sayısal değer olarak yorumlanabilecek bir karakter dizisi ' dir. Her işlev bir sayının parçası olarak tanıyamaz ilk karakterde dizesini okumayı durdurur. Bu sondaki boş karakter olabilir. İçin `strtol`, `strtoul`, `_strtoi64`, ve `_strtoui64`, bu Sonlandırıcı karakter de büyük veya ona eşit kullanıcı tarafından sağlanan temel ilk sayısal karakter olabilir.

Kullanıcı tarafından sağlanan işaretçi dönüştürme son karakter olarak ayarlanmazsa, **NULL** çağrı zaman taramayı durduran karaktere bir işaretçi var. Bunun yerine depolanır. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), dize işaretçisini değerini bu adreste depolanır.

`strtod` Aşağıdaki formun dizesi bekliyor:

[*boşluk*] [*oturum*] [`digits`] [**.** `digits`] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*oturum*] `digits`]

A *boşluk* yoksayılan boşluk veya sekme karakterlerinden oluşabilir *oturum* ya da artı (**+**) veya eksidir (**-**); ve `digits` bir veya daha fazla ondalık basamaktır. Herhangi bir basamak taban karakterden önce görünüyorsa, en az bir taban karakterden sonra yer almalıdır. Ondalık basamak bir tanıtıcı harften oluşan bir üs gelebilir (**d**, **D**, **e**, veya **E**) ve isteğe bağlı olarak işaretli tamsayı. Üstel bir parça ya da bir taban karakter görünürse, taban karakterin dizedeki son basamağı izlediği varsayılır. Bu forma uymayan ilk karakter taramayı durdurur.

`strtol`, `strtoul`, `_strtoi64`, Ve `_strtoui64` işlevleri beklediğiniz aşağıdaki formun dizesi:

[*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [`digits`]

Temel bağımsız değişkenini 2 ile 36 arasında varsa sayının tabanı kullanılır. 0 ise, ilk karakterleri için dönüştürme son işaretçi tarafından başvurulan tabanı belirlemek için kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizlik bir tamsayı olarak yorumlanır; Aksi takdirde, bir ondalık sayı olarak yorumlanır. İlk karakter '0' ise ve ikinci karakter 'x' veya 'X' dize onaltılık bir tamsayı olarak yorumlanır. İlk karakter ' 1'-' 9' ise, dize ondalık bir tamsayı olarak yorumlanır. Harfler 'bir'-'z' (ya da 'A'-'Z'), 10-35 arasında değerler atanır; yalnızca atanan değerleri olan harf küçüktür *temel* izin verilir. `strtoul` ve `_strtoui64` artı izin ver (**+**) veya eksidir (**-**) oturum önekinin; baştaki eksi işareti dönüş değerine değilleme uygulandığını gösterir.

Çıkış değeri ayarından etkilenir `LC_NUMERIC` yerel ayarının kategori ayarına; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş.

Bu işlevler tarafından döndürülen değer, bir taşma veya yetersiz gelme neden olduğu veya dönüştürme mümkün olmadığı durumlarda, gösterildiği gibi özel durum değeri döndürülür:

|İşlev|Koşul|Döndürülen değer|
|--------------|---------------|--------------------|
|`strtod`|taşma|+/- `HUGE_VAL`|
|`strtod`|Underflow veya dönüştürme|0|
|`strtol`|+ Taşması|**LONG_MAX**|
|`strtol`|-Overflow|**LONG_MIN**|
|`strtol`|Underflow veya dönüştürme|0|
|`_strtoi64`|+ Taşması|**_I64_MAX**|
|`_strtoi64`|-Overflow|**_I64_MIN**|
|`_strtoi64`|Hiçbir dönüştürme|0|
|`_strtoui64`|taşma|**_UI64_MAX**|
|`_strtoui64`|Hiçbir dönüştürme|0|

**_I64_MAX**, _**I64_MIN**, ve **_UI64_MAX** SINIRLARI tanımlanır. H

`wcstod`, `wcstol`, `wcstoul`, `_wcstoi64`, ve `_wcstoui64` geniş karakterli sürümleridir `strtod`, `strtol`, `strtoul`, `_strtoi64`, ve `_strtoui64`sırasıyla; bir end-ın-dönüştürme işaretçisi Bu geniş karakter işlevlerin her biri bağımsız değişken geniş karakterli bir dizedir. Aksi takdirde, kendisine tek baytlık karakterlerdir karşılık gelen geniş karakter bu işlevlerin her biri aynı şekilde davranır.

## <a name="see-also"></a>Ayrıca Bkz.

[Veri Dönüştürme](../c-runtime-library/data-conversion.md)<br/>
[locale](../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Kayan Nokta Desteği](../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)