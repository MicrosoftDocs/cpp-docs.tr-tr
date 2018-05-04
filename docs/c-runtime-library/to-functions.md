---
title: işlevlere | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
dev_langs:
- C++
helpviewer_keywords:
- to functions
- string conversion, to different characters
- string conversion, case
- lowercase, converting strings
- uppercase, converting strings
- case, converting
- characters, converting
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c852f65e603f11bfaf5812a9cb688dbf0eb36904
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="to-functions"></a>to İşlevleri
Her biri **için** işlevleri ve onun ilişkili makrosu varsa, dönüştürür tek bir karakter için başka bir karakter.  
  
|||  
|-|-|  
|[__toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper, _toupper, towupper](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|  
|[tolower, _tolower, towlower](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||  
  
## <a name="remarks"></a>Açıklamalar  
 **İçin** işlevleri ve makrosu dönüşümleri aşağıdaki gibidir.  
  
|Yordam|Makrosu|Açıklama|  
|-------------|-----------|-----------------|  
|`__toascii`|`__toascii`|Dönüştürür `c` ASCII karakter|  
|`tolower`|`tolower`|Dönüştürür `c` uygunsa küçük|  
|`_tolower`|`_tolower`|Dönüştürür `c` küçük harfe|  
|`towlower`|Yok.|Dönüştürür `c` için karşılık gelen joker karakter küçük harf|  
|`toupper`|`toupper`|Dönüştürür `c` uygunsa büyük harfe|  
|`_toupper`|`_toupper`|Dönüştürür `c` büyük harf|  
|`towupper`|Yok.|C karşılık gelen joker karakter büyük harfe dönüştürür|  
  
 İşlev sürümlerini **için** makroları olarak da tanımlanır yordamları, ya da kaldırma makrosu tanımlarla `#undef` yönergeleri veya CTYPE içermez. H. /Za derleyici seçeneği kullanırsanız, derleyici işlevi sürümünü kullandığından `toupper` veya `tolower`. Bildirimlerini `toupper` ve `tolower` işlevlerdir STDLIB içinde. H.  
  
 `__toascii` Rutin ayarlar tüm ancak düşük düzey 7 bit `c` 0, böylece dönüştürülen değer ASCII karakter kümesinde bir karakteri temsil eder. Varsa `c` zaten bir ASCII karakter temsil eden `c` değişmez.  
  
 `tolower` Ve `toupper` yordamları:  
  
-   Bağımlı `LC_CTYPE` geçerli yerel ayar kategorisi (`tolower` çağrıları `isupper` ve `toupper` çağrıları `islower`).  
  
-   Dönüştürme `c` varsa `c` dönüştürülebilir harfini geçerli yerel uygun durumda ve aksi durumda bu yerel ayar için mevcut temsil eder. Aksi takdirde `c` değişmez.  
  
 `_tolower` Ve `_toupper` yordamları:  
  
-   Yerel ayar bağımsız, çok daha hızlı sürümleri `tolower` ve **toupper.**  
  
-   Kullanılabilir yalnızca **isascii (**`c`**)** ve her iki **isupper (**`c`**)** veya **islower (**`c`**)**, sırasıyla sıfır olmayan şunlardır.  
  
-   Tanımsız sonuçlara varsa yol `c` bir ASCII harfi dönüştürmek için uygun durumda değil.  
  
 `towlower` Ve `towupper` işlevler döndürür dönüştürülen bir kopyasını `c` aşağıdaki koşulların her ikisi de sıfır olmayan ve yalnızca. Aksi takdirde `c` değişmez.  
  
-   `c` geniş karakter uygun örneğinin (diğer bir deyişle, kendisi için `iswupper` veya **iswlower,** sırasıyla sıfır olmayan olduğu).  
  
-   Hedef durumu karşılık gelen bir geniş karakter (diğer bir deyişle, kendisi için `iswlower` veya **iswupper,** sırasıyla sıfır olmayan olduğu).  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../c-runtime-library/locale.md)   
 [is, isw Yordamları](../c-runtime-library/is-isw-routines.md)