---
title: mbrtowc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbrtowc
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
- mbrtowc
dev_langs:
- C++
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 256c3df754607d0d9321f87d565e2ce94491035c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405321"
---
# <a name="mbrtowc"></a>mbrtowc

Geçerli yerel birden çok baytlı karakter birden çok baytlı karakter ortasında yeniden özelliği ile eşdeğer geniş karakter dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>Parametreler

*wchar*<br/>
Dönüştürülen geniş karakter dizesini almak için geniş karakter adresini (tür **wchar_t**). Hiçbir dönüş geniş karakter gerekiyorsa bu değer null bir işaretçi olabilir.

*mbchar*<br/>
Adresi, bir dizi bayt (birden çok baytlı karakter).

*Sayısı*<br/>
Denetlenecek bayt sayısı.

*mbstate*<br/>
Dönüştürme durumu nesnesine işaretçi. Bu değer null işaretçi ise, bir statik iç dönüştürme durumu nesnesi işlevini kullanır. Çünkü iç **mbstate_t** nesnesi iş parçacığı açısından güvenli değil, her zaman kendi geçirdiğiniz olmasını öneririz *mbstate* bağımsız değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

0 sonraki *sayısı* veya daha az sayıda bayt depolanan null geniş karakter temsil eden birden çok baytlı karakter tamamlamak *wchar*, *wchar* null işaretçi değil.

1 *sayısı*(dahil) sonraki *sayısı* veya geçerli bir birden çok baytlı karakter daha az sayıda bayt tamamlayın. Döndürülen değer birden çok baytlı karakter tamamlamak bayt sayısıdır. Eşdeğer geniş karakter depolanan *wchar*, *wchar* null işaretçi değil.

(size_t) (-1) Bir kodlama hatası oluştu. Sonraki *sayısı* veya daha az sayıda bayt tam ve geçerli birden çok baytlı karakter katkıda bulunmamaktadır. Bu durumda, **errno** EILSEQ ve dönüştürme shift durumda ayarlanır *mbstate* belirtilmedi.

(size_t) (-2) Sonraki *sayısı* bayt katkıda tamamlanmamış ancak büyük olasılıkla geçerli birden çok baytlı karakter ve tüm *sayısı* bayt işlenir. Hiçbir değer depolanan *wchar*, ancak *mbstate* işlevi yeniden başlatmak için güncelleştirilmiştir.

## <a name="remarks"></a>Açıklamalar

Varsa *mbchar* null işaretçi işlevi çağrısına eşdeğerdir:

`mbrtowc(NULL, "", 1, &mbstate)`

Bu durumda, bağımsız değişken değeri *wchar* ve *sayısı* göz ardı edilir.

Varsa *mbchar* null işaretçinin değil işlevi inceler *sayısı* baytlar *mbchar* gerekli sonraki tamamlamak için gereken bayt sayısını belirlemek için birden çok baytlı karakter. Sonraki karakteri geçerliyse, karşılık gelen birden çok baytlı karakter depolanan *wchar* yoksa null işaretçi. Karakter geniş null karşılık gelen ise karakter, sonuçta elde edilen durumu *mbstate* ilk dönüştürme durumdur.

**Mbrtowc** işlevi farklı olarak [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan *mbstate* sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış.  Örneğin, bir uygulama kullanması gereken **wcsrlen** yerine **wcslen** sonraki çağrı, **wcsrtombs** yerine kullanılan **wcstombs**.

## <a name="example"></a>Örnek

Birden çok baytlı karakter kendi geniş karakter eşdeğer dönüştürür.

```cpp
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

### <a name="sample-output"></a>Örnek Çıktı

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
