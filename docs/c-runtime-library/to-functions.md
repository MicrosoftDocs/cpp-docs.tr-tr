---
description: 'Hakkında daha fazla bilgi edinin:'
title: to İşlevleri
ms.date: 11/04/2016
api_location:
- msvcr120.dll
- msvcr90.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 4e2e8993bfe3ecc85071ab53bcd38c38c9da3370
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326873"
---
# <a name="to-functions"></a>to İşlevleri

Her biri ve ilişkili makrosu **varsa, tek** bir karakteri başka bir karaktere dönüştürür.

[__toascii](../c-runtime-library/reference/toascii-toascii.md)\
[ToLower, _tolower, kasada daha düşük](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)\
[ToUpper, _toupper, kasaüstü](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)

## <a name="remarks"></a>Açıklamalar

**To** işlevleri ve makro dönüştürmeleri aşağıdaki gibidir.

|Yordam|Makroya|Açıklama|
|-------------|-----------|-----------------|
|`__toascii`|`__toascii`|`c`ASCII karakterine dönüştürür|
|`tolower`|`tolower`|`c`Uygunsa küçük harfe dönüştürür|
|`_tolower`|`_tolower`|`c`Küçük harfe dönüştürür|
|`towlower`|Yok|`c`Karşılık gelen geniş karakterli küçük harfe dönüştürür|
|`toupper`|`toupper`|`c`Uygunsa büyük harfe dönüştürür|
|`_toupper`|`_toupper`|`c`Büyük harfe dönüştürür|
|`towupper`|Yok|C 'yi karşılık gelen geniş karakterli büyük harfe dönüştürür|

Aynı zamanda makrolar olarak tanımlanan **, ve '** nin işlev sürümlerini kullanmak için, Makro tanımlarını yönergelerle kaldırın `#undef` ya da CType. H 'yi dahil edin. /Za derleyici seçeneğini kullanırsanız, derleyici veya ' nin işlev sürümünü kullanır `toupper` `tolower` . `toupper`Ve `tolower` işlevlerinin bildirimleri Stdlib. H ' dir.

`__toascii`Bu yordam, `c` dönüştürülmüş değer ASCII karakter kümesindeki bir karakteri temsil ettiğinden, 0 ' ın düşük sıra 7 biti hariç tümünü ayarlar. `c`Zaten BIR ASCII karakterini temsil ediyorsa, `c` değiştirilmez.

`tolower`Ve `toupper` yordamları:

- `LC_CTYPE`Geçerli yerel ayarın kategorisine bağımlıdır ( `tolower` çağrılar `isupper` ve `toupper` çağrılar `islower` ).

- Dönüştür `c` `c` geçerli yerel ayarda uygun durumun dönüştürülebilir bir harfini temsil ediyorsa ve bu yerel ayar için ters durum varsa. Aksi takdirde, `c` değiştirilmez.

`_tolower`Ve `_toupper` yordamları:

- Yerel ayar bağımsız, çok daha hızlı `tolower` ve **ToUpper sürümleridir.**

- Yalnızca **ısascıı (** `c` **)** ve **ıupper** `c` **()** ya da **ılower (** `c` **)**, sırasıyla sıfır olmadığında kullanılabilir.

- `c`Dönüştürme için uygun durumun ASCII harfi değilse tanımsız sonuçlara sahip olur.

`towlower`Ve `towupper` işlevleri, `c` yalnızca aşağıdaki koşullardan her ikisi de sıfır değilse, dönüştürülmüş bir kopyasını döndürür. Aksi takdirde, `c` değiştirilmez.

- `c`, uygun durumda olan geniş bir karakterdir (yani, sırasıyla, ve ' `iswupper` nin  sıfır dışında).

- Hedef durumunun karşılık gelen geniş bir karakteri vardır (yani, `iswlower` sırasıyla, veya **ıswupper** , sıfır dışında).

## <a name="example"></a>Örnek

```c
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

[Veri dönüştürme](../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../c-runtime-library/locale.md)<br/>
[, isw yordamları](../c-runtime-library/is-isw-routines.md)
