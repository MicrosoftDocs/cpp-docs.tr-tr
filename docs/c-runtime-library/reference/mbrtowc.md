---
title: mbrtowc
ms.date: 11/04/2016
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
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: bd719e7b336333f6e06a1db9b1e34784575a1602
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331538"
---
# <a name="mbrtowc"></a>mbrtowc

Geçerli yerel ayarında çok baytlı bir karakterin çok baytlı bir karakterin ortasında yeniden başlatma özelliği ile eşdeğer geniş karakter dönüştürün.

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
Dönüştürülen geniş karakter dizesini almak için bir geniş karakter adresini (tür **wchar_t**). Dönüş yok geniş karakter gerekiyorsa, bu değer null bir işaretçi olabilir.

*mbchar*<br/>
Bayt (bir çok baytlı karakter) sırasını adresi.

*Sayısı*<br/>
Denetlenecek bayt sayısı.

*mbstate*<br/>
Dönüştürme durum nesnesine yönelik işaretçi. Bu değer bir null işaretçi ise, işlev bir iç statik dönüştürme durumu nesnesi kullanır. Olduğundan iç **mbstate_t** nesne iş parçacığı güvenli değil, size her zaman kendi geçmesini öneririz *mbstate* bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

0 sonraki *sayısı* ya da daha az bayt depolanan null geniş karakter temsil eden çok baytlı karakterin tamamlamak *wchar*, *wchar* null bir işaretçi değil.

1 *sayısı*dahil olmak üzere sonraki *sayısı* veya daha az bayt geçerli çok baytlı bir karakterin tamamlayın. Döndürülen değer çok baytlı karakteri tamamlamak bayt sayısıdır. İçinde depolanan geniş karakter eşdeğer *wchar*, *wchar* null bir işaretçi değil.

(size_t) (-1) Kodlama bir hata oluştu. Sonraki *sayısı* veya daha az bayt tam ve geçerli çok baytlı karakter katkıda bulunmuyor. Bu durumda, **errno** EILSEQ ve dönüştürme shift durumda ayarlanır *mbstate* belirtilmemiş.

(size_t) -(2) Sonraki *sayısı* bayt tamamlanmamış ancak potansiyel olarak geçerli bir çok baytlı karakter ve tüm katkıda *sayısı* bayt işlenir. Hiçbir değer depolanan *wchar*, ancak *mbstate* işlevi yeniden başlatmak için güncelleştirilir.

## <a name="remarks"></a>Açıklamalar

Varsa *mbchar* null işaretçisiyse, işlev çağrısına eşdeğerdir:

`mbrtowc(NULL, "", 1, &mbstate)`

Bu durumda, bağımsız değişkenlerin değerini *wchar* ve *sayısı* göz ardı edilir.

Varsa *mbchar* null bir işaretçi değil işlevi inceler *sayısı* bayt *mbchar* gerekli sonraki tamamlamak için gereken bayt sayısını belirlemek için çok baytlı karakter. Sonraki karakteri geçerliyse, çok baytlı karaktere karşılık gelen depolanan *wchar* null bir işaretçi değilse. İlgili geniş null karakter değilse karakter, sonuçta elde edilen durumunu *mbstate* ilk dönüştürme durumudur.

**Mbrtowc** işlevi farklıdır [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) kendi restartability tarafından. Dönüştürme durumunu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır.  Örneğin, bir uygulamanın kullanması gereken **wcsrlen** yerine **wcslen** sonraki çağrı, **wcsrtombs** yerine kullanılan **wcstombs**.

## <a name="example"></a>Örnek

Çok baytlı bir karakter, geniş karakteri eşdeğer dönüştürür.

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
