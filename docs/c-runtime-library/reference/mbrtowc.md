---
title: mbrtowc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbrtowc
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
f1_keywords: mbrtowc
dev_langs: C++
helpviewer_keywords: mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: afbc17fbe93fdead069ca89ebbaf0eee400cd746
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mbrtowc"></a>mbrtowc
Geçerli yerel birden çok baytlı karakter birden çok baytlı karakter ortasında yeniden özelliği ile eşdeğer geniş karakter dönüştürün.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t mbrtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   mbstate_t *mbstate  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `wchar`  
 Dönüştürülen geniş karakter dizesini almak için geniş karakter adresini (tür `wchar_t`). Hiçbir dönüş geniş karakter gerekiyorsa bu değer null bir işaretçi olabilir.  
  
 `mbchar`  
 Adresi, bir dizi bayt (birden çok baytlı karakter).  
  
 `count`  
 Denetlenecek bayt sayısı.  
  
 `mbstate`  
 Dönüştürme durumu nesnesine işaretçi. Bu değer null işaretçi ise, bir statik iç dönüştürme durumu nesnesi işlevini kullanır. Çünkü iç `mbstate_t` nesnesi iş parçacığı açısından güvenli değil, her zaman kendi geçirdiğiniz olmasını öneririz `mbstate` bağımsız değişkeni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri:  
  
 0  
 Sonraki `count` veya daha az sayıda bayt depolanan null geniş karakter temsil eden birden çok baytlı karakter tamamlamak `wchar`, `wchar` null işaretçi değil.  
  
 1 `count`(dahil)  
 Sonraki `count` veya geçerli bir birden çok baytlı karakter daha az sayıda bayt tamamlayın. Döndürülen değer birden çok baytlı karakter tamamlamak bayt sayısıdır. Eşdeğer geniş karakter depolanan `wchar`, `wchar` null işaretçi değil.  
  
 (size_t) (-1)  
 Bir kodlama hatası oluştu. Sonraki `count` veya daha az sayıda bayt tam ve geçerli birden çok baytlı karakter katkıda bulunmamaktadır. Bu durumda, `errno` EILSEQ ve dönüştürme shift durumda ayarlanır `mbstate` belirtilmedi.  
  
 (size_t) (-2)  
 Sonraki `count` bayt katkıda tamamlanmamış ancak büyük olasılıkla geçerli birden çok baytlı karakter ve tüm `count` bayt işlenir. Hiçbir değer depolanan `wchar`, ancak `mbstate` işlevi yeniden başlatmak için güncelleştirilmiştir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `mbchar` null işaretçi işlevi çağrısına eşdeğerdir:  
  
 `mbrtowc(NULL, "", 1, &mbstate)`  
  
 Bu durumda, bağımsız değişken değeri `wchar` ve `count` göz ardı edilir.  
  
 Varsa `mbchar` null işaretçinin değil işlevi inceler `count` baytlar `mbchar` gerekli sonraki birden çok baytlı karakter tamamlamak için gereken bayt sayısını belirlemek için. Sonraki karakteri geçerliyse, karşılık gelen birden çok baytlı karakter depolanan `wchar` yoksa null işaretçi. Karakter geniş null karşılık gelen ise karakter, sonuçta elde edilen durumu `mbstate` ilk dönüştürme durumdur.  
  
 `mbrtowc` İşlevi farklı olarak [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış.  Örneğin, bir uygulama kullanması gereken `wcsrlen` yerine `wcslen` sonraki çağrı, `wcsrtombs` yerine kullanılan `wcstombs`.  
  
## <a name="example"></a>Örnek  
 Birden çok baytlı karakter kendi geniş karakter eşdeğer dönüştürür.  
  
```  
// crt_mbrtowc.cpp  
  
#include <stdio.h>  
#include <mbctype.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
#define BUF_SIZE 100  
  
int Sample(char* szIn, wchar_t* wcOut, int nMax)  
{  
    mbstate_t   state = {0}; // Initial state  
    size_t      nConvResult,   
                nmbLen = 0,  
                nwcLen = 0;  
    wchar_t*    wcCur = wcOut;  
    wchar_t*    wcEnd = wcCur + nMax;  
    const char* mbCur = szIn;  
    const char* mbEnd = mbCur + strlen(mbCur) + 1;  
    char*       szLocal;  
  
    // Sets all locale to French_Canada.1252  
    szLocal = setlocale(LC_ALL, "French_Canada.1252");  
    if (!szLocal)  
    {  
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");  
        return 1;  
    }  
  
    printf("Locale set to: \"%s\"\n", szLocal);  
  
    // Sets the code page associated current locale's code page  
    // from a previous call to setlocale.  
    if (_setmbcp(_MB_CP_SBCS) == -1)  
    {  
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");  
        return 1;  
    }  
  
    while ((mbCur < mbEnd) && (wcCur < wcEnd))  
    {  
        //  
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);  
        switch (nConvResult)  
        {  
            case 0:  
            {  // done  
                printf("Conversion succeeded!\nMultibyte String: ");  
                printf(szIn);  
                printf("\nWC String: ");  
                wprintf(wcOut);  
                printf("\n");  
                mbCur = mbEnd;  
                break;  
            }  
  
            case -1:  
            {  // encoding error  
                printf("The call to mbrtowc has detected an encoding error.\n");  
                mbCur = mbEnd;  
                break;  
            }  
  
            case -2:  
            {  // incomplete character  
                if   (!mbsinit(&state))  
                {  
                    printf("Currently in middle of mb conversion, state = %x\n", state);  
                    // state will contain data regarding lead byte of mb character  
                }  
  
                ++nmbLen;  
                ++mbCur;  
                break;  
            }  
  
            default:  
            {  
                if   (nConvResult > 2) // The multibyte should never be larger than 2  
                {  
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);  
                }  
  
                ++nmbLen;  
                ++nwcLen;  
                ++wcCur;  
                ++mbCur;  
            break;  
            }  
        }  
    }  
  
   return 0;  
}  
  
int main(int argc, char* argv[])  
{  
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";  
    wchar_t wcBuf[BUF_SIZE] = {L''};  
  
    return Sample(mbBuf, wcBuf, BUF_SIZE);  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
Locale set to: "French_Canada.1252"  
Conversion succeeded!  
Multibyte String: AaBbCcÜïα∩≡xXyYzZ  
WC String: AaBbCcÜïα∩≡xXyYzZ  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`mbrtowc`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)