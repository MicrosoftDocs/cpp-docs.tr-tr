---
title: wcrtomb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb
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
f1_keywords: wcrtomb
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c9dfe3b112754d573226fe992d346d57de56406
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtomb"></a>wcrtomb
Geniş karakter, birden çok baytlı karakter gösterimine dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`mbchar`  
 Sonuçta elde edilen çok baytlı karakter dönüştürülür.  
  
 [in]`wchar`  
 Dönüştürülecek geniş karakter.  
  
 [in]`mbstate`  
 Bir işaretçi bir `mbstate_t` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa dönüştürülen birden çok baytlı karakter yoksa -1 göstermek için gereken bayt sayısını döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `wcrtomb` İşlevi dönüştürür bulunan belirtilen dönüşüm durumunu'den başlayarak bir geniş karakter `mbstate`, içerdiği değerinden `wchar`, veri tarafından temsil edilen adresine `mbchar`. Dönüş değeri karşılık gelen birden çok baytlı karakter temsil etmek için gereken bayt sayısıdır. ancak değil döndürülecek birden fazla `MB_CUR_MAX` bayt sayısı.  
  
 Varsa `mbstate` null, iç `mbstate_t` dönüştürme durumunu içeren bir nesne `mbchar` kullanılır. Varsa bir karakter dizisi `wchar` karşılık gelen çok baytlı yok karakter gösterimi, -1 döndürülür ve `errno` ayarlanır `EILSEQ`.  
  
 `wcrtomb` İşlevi farklı olarak [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanırsınız `wcsrlen` yerine `wcsnlen`, bir sonraki çağrı, `wcsrtombs` yerine kullanılan `wcstombs`.  
  
 C++'da, bu işlev bu işlevin yeni, güvenli ortaklarınıza çağıran bir şablon aşırı sahiptir. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 `wcrtomb` İşlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu `setlocale` bu işlev yürütülürken ve sırasında `mbstate` null.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)