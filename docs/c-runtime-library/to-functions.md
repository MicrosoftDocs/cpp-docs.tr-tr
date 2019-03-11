---
title: to İşlevleri
ms.date: 11/04/2016
apilocation:
- msvcr120.dll
- msvcr90.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- To
helpviewer_keywords:
- to functions
- string conversion, to different characters
- string conversion, case
- lowercase, converting strings
- uppercase, converting strings
- case, converting
- characters, converting
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
ms.openlocfilehash: 17d80507462b3eb0fdfb5d9e41da6162947bd3de
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742540"
---
# <a name="to-functions"></a>to İşlevleri

Her biri **için** işlevleri ve onun ilişkili makrosu varsa, tek bir karakterin başka bir karakterine dönüştürür.

|||
|-|-|
|[__toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper, _toupper, towupper](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|
|[tolower, _tolower, towlower](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||

## <a name="remarks"></a>Açıklamalar

**İçin** işlev ve makro dönüştürmeler aşağıdaki gibidir.

|Yordam|Makrosu|Açıklama|
|-------------|-----------|-----------------|
|`__toascii`|`__toascii`|Dönüştürür `c` ASCII karakteri|
|`tolower`|`tolower`|Dönüştürür `c` uygunsa küçük|
|`_tolower`|`_tolower`|Dönüştürür `c` küçük|
|`towlower`|Hiçbiri|Dönüştürür `c` için karşılık gelen geniş karakter küçük harf|
|`toupper`|`toupper`|Dönüştürür `c` uygun ise|
|`_toupper`|`_toupper`|Dönüştürür `c` büyük harf|
|`towupper`|Hiçbiri|C karşılık gelen geniş karakter büyük harfe dönüştürür.|

İşlev sürümleri kullanılacak **için** de makro olarak tanımlanan yordamları ile makro tanımları kaldırın `#undef` yönergeleri veya CTYPE içermez. H /Za derleyici seçeneğini kullanırsanız, derleyici işlev sürümü kullanan `toupper` veya `tolower`. Bildirimleri `toupper` ve `tolower` içinde STDLIB işlevlerdir. H

`__toascii` Rutin ayarlar tüm ancak düşük düzey 7 bit `c` 0, böylece dönüştürülen değer ASCII karakter kümesindeki bir karakteri temsil eder. Varsa `c` zaten bir ASCII karakteri temsil eden `c` değiştirilmez.

`tolower` Ve `toupper` yordamları:

- Bağımlı `LC_CTYPE` geçerli yerel ayarının kategori (`tolower` çağrıları `isupper` ve `toupper` çağrıları `islower`).

- Dönüştürme `c` varsa `c` dönüştürülebilir bir harf, geçerli yerel ayarı en uygun durumda ve ters durum var. Bu yerel ayara temsil eder. Aksi takdirde, `c` değiştirilmez.

`_tolower` Ve `_toupper` yordamları:

- Yerel ayarlardan bağımsızdır, daha hızlı bir şekilde sürümleri `tolower` ve **toupper.**

- Kullanılabilir yalnızca **isascii (**`c`**)** ve her iki **isupper (**`c`**)** veya **islower (**`c`**)** sırasıyla, sıfır dışında olan.

- Sonuçlar, tanımsız `c` bir ASCII harfi dönüştürmek için uygun durumda değil.

`towlower` Ve `towupper` işlevler dönüştürülmüş bir kopyasını döndürür `c` aşağıdaki koşulların her ikisinin de sıfır olmayan ve yalnızca. Aksi takdirde, `c` değiştirilmez.

- `c` uygun çalışmasının geniş bir karakterse (diğer bir deyişle, kendisi için `iswupper` veya **iswlower,** sırasıyla, sıfır dışında).

- Hedef durumu karşılık gelen bir geniş karakter yoktur (diğer bir deyişle, kendisi için `iswlower` veya **iswupper,** sırasıyla, sıfır dışında).

## <a name="example"></a>Örnek

```
// crt_toupper.c
/* This program uses toupper and tolower to
 * analyze all characters between 0x0 and 0x7F. It also
 * applies _toupper and _tolower to any code in this
 * range for which these functions make sense.
 */

#include <ctype.h>
#include <string.h>

char msg[] = "Some of THESE letters are Capitals.";
char *p;

int main( void )
{
   printf( "%s\n", msg );

   /* Reverse case of message. */
   for( p = msg; p < msg + strlen( msg ); p++ )
   {
      if( islower( *p ) )
         putchar( _toupper( *p ) );
      else if( isupper( *p ) )
         putchar( _tolower( *p ) );
      else
         putchar( *p );
   }
}
```

```Output
Some of THESE letters are Capitals.
sOME OF these LETTERS ARE cAPITALS.
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../c-runtime-library/data-conversion.md)<br/>
[locale](../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)
