---
title: wcrtomb_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb_s
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
f1_keywords: wcrtomb_s
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13134a3e6b34be13d6d878cf94f204bb6c87a458
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtombs"></a>wcrtomb_s
Geniş karakter, birden çok baytlı karakter gösterimine dönüştürür. Bir sürümünü [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pReturnValue`  
 Bir hata oluştuğunda yazılan bayt sayısı veya -1 döndürür.  
  
 [out]`mbchar`  
 Sonuçta elde edilen çok baytlı karakter dönüştürülür.  
  
 [in]`sizeOfmbchar`  
 Boyutunu `mbchar` bayt değişken.  
  
 [in]`wchar`  
 Dönüştürülecek geniş karakter.  
  
 [in]`mbstate`  
 Bir işaretçi bir `mbstate_t` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür sıfır veya bir `errno` bir hata oluşursa değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 `wcrtomb_s` İşlevi dönüştürür bulunan belirtilen dönüşüm durumunu'den başlayarak bir geniş karakter `mbstate`, içerdiği değerinden `wchar`, veri tarafından temsil edilen adresine `mbchar`. `pReturnValue` Değer dönüştürülen bayt ancak hiçbir sayısı olacak birden fazla `MB_CUR_MAX` bayt ya da bir hata oluştuysa -1.  
  
 Varsa `mbstate` null, iç `mbstate_t` dönüştürme durumu kullanılır. Karakter içeriyorsa `wchar` bir karşılık gelen birden çok baytlı karakter değeri yok `pReturnValue` -1 olur ve işlev döndürülecek `errno` değerini `EILSEQ`.  
  
 `wcrtomb_s` İşlevi farklı olarak [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanırsınız `wcsrlen` yerine `wcslen`, bir sonraki çağrı, `wcsrtombs_s` yerine kullanıldı`wcstombs_s.`  
  
 C++'da, bu işlevi kullanarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 `wcrtomb_s` İşlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu `setlocale` bu işlev yürütülürken ve `mbstate` null.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
The corresponding wide character "Q" was converted to a the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)