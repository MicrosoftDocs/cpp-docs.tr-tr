---
title: wcstombs, _wcstombs_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstombs
- _wcstombs_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
dev_langs: C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fa142902722ac5df6ac93b28daf9e76b99f54f5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l
Geniş bir karakter dizisi birden çok baytlı karakterler karşılık gelen bir dizi dönüştürür. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mbstr`  
 Birden çok baytlı karakter dizisi adresi.  
  
 `wcstr`  
 Geniş bir karakter dizisi adresi.  
  
 `count`  
 Birden çok baytlı çıkış dizesi içinde depolanan bayt sayısı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `wcstombs` başarıyla baytlı dizeye dönüştürür sonlandırma hariç olmak üzere birden çok baytlı çıkış dizeye yazılan bayt sayısını döndürür `NULL` (varsa). Varsa `mbstr` bağımsız değişkeni `NULL`, `wcstombs` gereken boyut hedef dizesi bayt cinsinden döndürür. Varsa `wcstombs` birden çok baytlı karakter dönüştüremiyor geniş karakter karşılaştığında yazmak için cast -1 döndürür `size_t` ve ayarlar `errno` için `EILSEQ`.  
  
## <a name="remarks"></a>Açıklamalar  
 `wcstombs` İşlevi dönüştürür gösterdiği geniş karakter dizesi `wcstr` için karşılık gelen çok baytlı karakter ve sonuçları depolar `mbstr` dizi. `count` Parametresi birden çok baytlı çıkış dizesi içinde depolanan bayt sayısını belirtir (diğer bir deyişle, boyutu `mbstr`). Genel olarak, bir joker karakter dizesi dönüştürülürken kaç bayt gerekli olacak bilinmiyor. Bazı uluslararası karakterler yalnızca tek baytlık çıkış dizesinde gerektirir; diğer iki gerektirir. Giriş dizisinde her geniş karakter birden çok baytlı çıkış dizesinde iki bayt varsa (geniş karakter dahil olmak üzere `NULL`), sonuç uyacak şekilde sağlanır.  
  
 Varsa `wcstombs` joker karakter null karakteri (M '\0') önce veya ne zaman karşılaşırsa `count` oluşur, dönüştürür, 8 bit 0 ve durdurur. Bu nedenle, birden çok baytlı karakter dizesi adresindeki `mbstr` null-yalnızca sonlandırılır `wcstombs` bir joker karakter null karakter dönüştürme sırasında karşılaşır. Dizileri gösterdiği varsa `wcstr` ve `mbstr` üst üste, davranışını `wcstombs` tanımlanmadı.  
  
 Varsa `mbstr` bağımsız değişkeni `NULL`, `wcstombs` gereken boyut hedef dizesi bayt cinsinden döndürür.  
  
 `wcstombs`parametreleri doğrular. Varsa `wcstr` olan `NULL`, veya `count` değerinden daha büyük `INT_MAX`, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, işlevi ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
 `wcstombs`Geçerli yerel ayar için tüm yerel ayara bağımlı davranışı kullanır; `_wcstombs_l` yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h >|  
|`_wcstombs_l`|\<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bu programın davranışını gösterilmektedir `wcstombs` işlevi.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 13  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)