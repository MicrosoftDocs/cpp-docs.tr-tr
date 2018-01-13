---
title: wctomb_s, _wctomb_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_s_l
- wctomb_s
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
- wctomb_s
- _wctomb_s_l
dev_langs: C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c819f62f36966363f32eb16b7af758de274d3d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l
Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürür. Bir sürümünü [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pRetValue`  
 Bayt veya sonucu gösteren bir kod sayısı.  
  
 [out]`mbchar`  
 Birden çok baytlı karakter adresi.  
  
 [in]`sizeInBytes`  
 Arabellek boyutu `mbchar`.  
  
 [in]`wchar`  
 Geniş karakter.  
  
 [in]`locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır başarılı olursa, hatasında bir hata kodu.  
  
 Hata koşulları  
  
|`mbchar`|`sizeInBytes`|Dönüş değeri|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|değiştirilmedi|  
|tüm|>`INT_MAX`|`EINVAL`|değiştirilmedi|  
|tüm|çok küçük|`EINVAL`|değiştirilmedi|  
  
 Yukarıdaki hata koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `wctomb` döndürür `EINVAL` ve ayarlar `errno` için `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `wctomb_s` İşlev dönüştürür kendi `wchar` karşılık gelen birden çok baytlı karakter bağımsız değişkeni ve sonucunda depolar `mbchar`. Herhangi bir noktadan herhangi bir programda işlevini çağırın.  
  
 Varsa `wctomb_s` geniş karakter dönüştürür isteğe bağlı olarak birden çok baytlı karakter bayt sayısı koyar (hangi asla büyük `MB_CUR_MAX`) gösterdiği değeri tamsayıya geniş karakter `pRetValue`. Varsa `wchar` joker karakter null karakteri (M '\0'), `wctomb_s` doldurur `pRetValue` 1. Varsa hedef işaretçi `mbchar` null, `wctomb_s` 0 koyar `pRetValue`. Dönüştürme geçerli yerel ayarda mümkün değilse, `wctomb_s` -1 koyar `pRetValue`.  
  
 `wctomb_s`Geçerli yerel ayar için yerel ayara bağımlı bilgileri kullanır; `_wctomb_s_l` yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h >|  
|`_wctomb_s_l`|\<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bu programın davranışını gösterilmektedir `wctomb` işlevi.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)