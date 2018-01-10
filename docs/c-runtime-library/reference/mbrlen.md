---
title: mbrlen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords: mbrlen
dev_langs: C++
helpviewer_keywords: mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58f94a79bb5304ed1ebfe9b7c2241b28497c8c4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbrlen"></a>mbrlen
Geçerli yerel birden çok baytlı karakter ortasında yeniden özelliği ile birden çok baytlı karakter tamamlamak için gereken bayt sayısını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t mbrlen(  
   const char * str,  
   size_t count,  
   mbstate_t * mbstate  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Çok baytlı karakter dizesi incelemek için sonraki bayt işaretçi.  
  
 `count`  
 En fazla incelemek için bayt sayısı.  
  
 `mbstate`  
 İlk baytını geçerli shift durumunu işaretçi `str`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri:  
  
 0  
 Sonraki `count` veya daha az sayıda bayt geniş null karakteri temsil eden birden çok baytlı karakter tamamlayın.  
  
 1 `count`(dahil)  
 Sonraki `count` veya geçerli bir birden çok baytlı karakter daha az sayıda bayt tamamlayın. Döndürülen değer birden çok baytlı karakter tamamlamak bayt sayısıdır.  
  
 (size_t) (-2)  
 Sonraki `count` bayt katkıda tamamlanmamış ancak büyük olasılıkla geçerli birden çok baytlı karakter ve tüm `count` bayt işlenir.  
  
 (size_t) (-1)  
 Bir kodlama hatası oluştu. Sonraki `count` veya daha az sayıda bayt tam ve geçerli birden çok baytlı karakter katkıda bulunmamaktadır. Bu durumda, `errno` EILSEQ ve dönüştürme durumda ayarlanır `mbstate` belirtilmedi.  
  
## <a name="remarks"></a>Açıklamalar  
 `mbrlen` İşlevi inceler en fazla `count` tarafından bayt ile başlayan bayt işaret için `str` tüm üst karakter sıraları dahil olmak üzere sonraki birden çok baytlı karakter tamamlamak için gerekli olan bayt sayısını belirlemek için. Çağrısına eşdeğerdir `mbrtowc(NULL, str, count, &mbstate)` nerede `mbstate` ya da bir kullanıcı tarafından sağlanan olduğu `mbstate_t` nesne ya da kitaplığı tarafından sağlanan statik bir iç nesne.  
  
 `mbrlen` İşlev kaydeder ve tamamlanmamış bir birden çok baytlı karakter shift durumunu kullanır `mbstate` parametresi. Bu verir `mbrlen` , birden çok baytlı karakter ortasında yeniden özelliği en fazla inceleniyor olması gerekir `count` bayt sayısı. Varsa `mbstate` null işaretçi `mbrlen` dahili, statik kullanan `mbstate_t` shift durumunu depolamak için nesne. Çünkü iç `mbstate_t` nesnesi iş parçacığı açısından güvenli değil, her zaman ayırın ve kendi geçirin öneririz `mbstate` parametresi.  
  
 `mbrlen` İşlevi farklı olarak [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md) kendi restartability tarafından. Shift durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış.  Örneğin, bir uygulama kullanması gereken `wcsrlen` yerine `wcslen` sonraki çağrı, `wcsrtombs` yerine kullanılır`wcstombs.`  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|Geçerli değil|Geçerli değil|`mbrlen`|Geçerli değil|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`mbrlen`|\<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl birden çok baytlı karakterler yorumu geçerli kod sayfasına bağlıdır ve devam ettirme yeteneğini gösterir gösterir `mbrlen`.  
  
```C  
// crt_mbrlen.c  
// Compile by using: cl crt_mbrlen.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
size_t Example(const char * pStr)  
{  
    size_t      charLen = 0;  
    size_t      charCount = 0;  
    mbstate_t   mbState = {0};  
  
    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&  
            charLen != (size_t)-1)  
    {  
        if (charLen != (size_t)-2) // if complete mbcs char,  
        {  
            charCount++;  
        }  
    }   
    return (charCount);  
}   
  
int main( void )  
{  
    int         cp;  
    size_t      charCount = 0;  
    const char  *pSample =   
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";  
  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
  
    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale  
    _setmbcp(932); // and Japanese multibyte code page  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
}  
```  
  
```Output  
  
Code page: 0  
é╨éτé¬é╚: Shift-jis hiragana.  
Character count: 29  
  
Code page: 932  
????: Shift-jis hiragana.  
Character count: 25  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [locale](../../c-runtime-library/locale.md)