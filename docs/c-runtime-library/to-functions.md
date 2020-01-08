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
ms.openlocfilehash: df8f59088cd402503fe31f768557e3ed936b31ec
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301697"
---
# <a name="to-functions"></a>to İşlevleri

Her biri ve ilişkili makrosu **varsa, tek** bir karakteri başka bir karaktere dönüştürür.

|||
|-|-|
|[__toascii](../c-runtime-library/reference/toascii-toascii.md)|[ToUpper, _toupper, kasaüstü](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|
|[ToLower, _tolower, kasada daha düşük](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||

## <a name="remarks"></a>Açıklamalar

**To** işlevleri ve makro dönüştürmeleri aşağıdaki gibidir.

|Yordam|Makrosu|Açıklama|
|-------------|-----------|-----------------|
|`__toascii`|`__toascii`|`c` ASCII karakterine dönüştürür|
|`tolower`|`tolower`|Uygunsa `c` küçük harfe dönüştürür|
|`_tolower`|`_tolower`|`c` küçük harfe dönüştürür|
|`towlower`|Yok.|`c`, karşılık gelen geniş karakterli küçük harfe dönüştürür|
|`toupper`|`toupper`|Uygunsa `c` büyük harfe dönüştürür|
|`_toupper`|`_toupper`|`c` büyük harfe dönüştürür|
|`towupper`|Yok.|C 'yi karşılık gelen geniş karakterli büyük harfe dönüştürür|

Aynı zamanda makrolar olarak da tanımlanan, **ve '** nin işlev sürümlerini kullanmak için, makro tanımlarını `#undef` yönergeleriyle kaldırın ya da CType eklemeyin. Olsun. /Za derleyici seçeneğini kullanırsanız, derleyici `toupper` veya `tolower`işlev sürümünü kullanır. `toupper` ve `tolower` işlevlerinin bildirimleri STDLIB ' dir. Olsun.

`__toascii` yordamı,, dönüştürülen değerin ASCII karakter kümesindeki bir karakteri temsil edebilmesi için, düşük sıralı 7 bit `c` hariç tümünü 0 olarak ayarlar. `c` zaten bir ASCII karakterini temsil ediyorsa, `c` değiştirilmez.

`tolower` ve `toupper` yordamları:

- Geçerli yerel ayarın `LC_CTYPE` kategorisine bağımlıdır (`tolower` çağrılar `isupper` ve `toupper` çağrıları `islower`).

- `c` geçerli yerel ayarda uygun durumun dönüştürülebilir bir harfini temsil ediyorsa ve bu yerel ayar için ters durum varsa `c` Dönüştür. Aksi takdirde, `c` değiştirilmez.

`_tolower` ve `_toupper` yordamları:

- , `tolower` ve **ToUpper** 'nin yerel ayara bağımsız, çok daha hızlı sürümleridir.

- Yalnızca **ısascıı (** `c` **)** ve **ıupper** (`c` **)** ya da **ılower (** `c` **)** sıfır dışında olduğunda kullanılabilir.

- `c`, dönüştürme için uygun durumun ASCII harfi değilse tanımsız sonuçlara sahip olur.

`towlower` ve `towupper` işlevleri, yalnızca aşağıdaki koşulların her ikisi de sıfır değilse `c` dönüştürülmüş bir kopyasını döndürür. Aksi takdirde, `c` değiştirilmez.

- `c`, uygun durumun geniş bir karakteridir (yani, sırasıyla, `iswupper` veya **ıswlower** , sıfır dışında).

- Hedef durumunun karşılık gelen geniş bir karakteri vardır (yani, sırasıyla `iswlower` veya **ıswupper** , sıfır dışında).

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

[Veri Dönüştürme](../c-runtime-library/data-conversion.md)<br/>
[locale](../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)
