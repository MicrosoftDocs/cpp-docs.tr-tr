---
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
ms.openlocfilehash: f7a898d70e506ed4707ea718faa0ed618682c2c7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944817"
---
# <a name="to-functions"></a>to İşlevleri

Her biri ve ilişkili makrosu **varsa, tek** bir karakteri başka bir karaktere dönüştürür.

|||
|-|-|
|[__toascıı](../c-runtime-library/reference/toascii-toascii.md)|[ToUpper, _toupper, kasaüstü](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|
|[ToLower, _tolower, kasada küçük](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||

## <a name="remarks"></a>Açıklamalar

**To** işlevleri ve makro dönüştürmeleri aşağıdaki gibidir.

|Yordam|Makrosu|Açıklama|
|-------------|-----------|-----------------|
|`__toascii`|`__toascii`|ASCII `c` karakterine dönüştürür|
|`tolower`|`tolower`|Uygunsa `c` küçük harfe dönüştürür|
|`_tolower`|`_tolower`|Küçük `c` harfe dönüştürür|
|`towlower`|Yok.|Karşılık `c` gelen geniş karakterli küçük harfe dönüştürür|
|`toupper`|`toupper`|Uygunsa `c` büyük harfe dönüştürür|
|`_toupper`|`_toupper`|Büyük `c` harfe dönüştürür|
|`towupper`|Yok.|C 'yi karşılık gelen geniş karakterli büyük harfe dönüştürür|

Aynı zamanda makrolar olarak tanımlanan, ve ' nin işlev sürümlerini kullanmak **için, makro** tanımlarını `#undef` yönergelerle kaldırın ya da CType dahil edin. Olsun. /Za derleyici seçeneğini kullanırsanız, derleyici veya `toupper` `tolower`' nin işlev sürümünü kullanır. `toupper` Ve`tolower` işlevlerinin bildirimleri Stdlib ' dir. Olsun.

Bu yordam, dönüştürülmüş değer ASCII karakter kümesindeki bir karakteri temsil ettiğinden `c` , 0 ' ın düşük sıra 7 biti hariç tümünü ayarlar. `__toascii` Zaten `c` bir ASCII karakterini temsil ediyorsa, `c` değiştirilmez.

`tolower` Ve`toupper` yordamları:

- `LC_CTYPE` Geçerli yerel ayarın kategorisine bağımlıdır ( `isupper` `tolower` çağrılar ve `toupper` çağrılar `islower`).

- Dönüştür `c`geçerli yerel ayarda uygun durumun dönüştürülebilir bir harfini temsilediyorsavebuyerelayariçintersdurumvarsa.`c` Aksi takdirde `c` , değiştirilmez.

`_tolower` Ve`_toupper` yordamları:

- Yerel ayar bağımsız, çok daha hızlı `tolower` ve **ToUpper sürümleridir.**

- Yalnızca **ısascıı (** `c` **)** ve **ıupper**`c` **() ya da** **ılower (** `c` **)** , sırasıyla sıfır olmadığında kullanılabilir.

- Dönüştürme için uygun durumun `c` ASCII harfi değilse tanımsız sonuçlara sahip olur.

`c` Ve `towlower` işlevleri,yalnızcaaşağıdakikoşullardanherikisidesıfırdeğilse,dönüştürülmüşbirkopyasınıdöndürür.`towupper` Aksi takdirde `c` , değiştirilmez.

- `c`, uygun durumda olan geniş bir karakterdir ( `iswupper` Yani, sırasıyla, ve ' nin sıfır dışında).

- Hedef durumunun karşılık gelen geniş bir karakteri vardır (yani `iswlower` , sırasıyla, veya **ıswupper** , sıfır dışında).

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
