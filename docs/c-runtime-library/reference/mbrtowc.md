---
title: mbrtowc
ms.date: 4/2/2020
api_name:
- mbrtowc
- _o_mbrtowc
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: be46c3f3c728b70c7cbf060572acc24662637a81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340926"
---
# <a name="mbrtowc"></a>mbrtowc

Çok baytlı bir karakterin ortasında yeniden başlatma özelliğiyle geçerli yerel ayardaki çok bayt karakteri eşdeğer geniş karaktere dönüştürün.

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

*Wchar*<br/>
Dönüştürülmüş geniş karakter dizesini almak için geniş bir karakterin adresi **(wchar_t**yazın). İade geniş karakter gerekiyorsa, bu değer null işaretçisi olabilir.

*mbchar*<br/>
Bayt dizisinin adresi (çok bayt karakter).

*Sayısı*<br/>
Kontrol etmek için bayt sayısı.

*mbstate*<br/>
Dönüştürme durumu nesnesi için işaretçi. Bu değer null işaretçisi ise, işlev statik bir iç dönüşüm durumu nesnesi kullanır. İç **mbstate_t** nesnesi iş parçacığı için güvenli olmadığından, her zaman kendi *mbstate* bağımsız değişkeninizi geçirmenizi öneririz.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

0 Sonraki *sayı* veya daha az bayt *wchar*depolanır null geniş karakteri temsil eden çok bayt karakteri tamamlamak , *wchar* bir null işaretçi değilse.

1 *saymak,* bir sonraki *sayı* veya daha az bayt geçerli bir çok bayt karakteri tamamlamak dahil. Döndürülen değer, çok bayt karakterini tamamlayan bayt sayısıdır. Geniş karakter eşdeğeri *wchar*depolanır , *wchar* null işaretçi değilse.

(size_t) (-1) Bir kodlama hatası oluştu. Sonraki *sayı* veya daha az bayt tam ve geçerli bir çok bayt karaktere katkıda bulunmaz. Bu durumda, **errno** EILSEQ olarak ayarlanır ve *mbstate* dönüşüm kaydırma durumu belirtilmemiştir.

(size_t) (-2) Sonraki *sayım* baytları eksik ama geçerli bir çok bayt karakterine katkıda bulunur ve tüm *sayım* baytları işlenir. *Wchar'da*hiçbir değer depolanır, ancak işlevi yeniden başlatmak için *mbstate* güncelleştirilir.

## <a name="remarks"></a>Açıklamalar

*Mbchar* null işaretçisi ise, işlev çağrıya eşdeğerdir:

`mbrtowc(NULL, "", 1, &mbstate)`

Bu durumda, *wchar* ve *sayısı* bağımsız değişkenlerinin değeri yoksayılır.

*Mbchar* null işaretçi değilse, işlev bir sonraki çok bayt karakterini tamamlamak için gerekli bayt sayısını belirlemek için *mbchar'dan* *bayt sayısını* inceler. Bir sonraki karakter geçerliyse, karşılık gelen çok bayt karakter null işaretçi değilse *wchar'da* depolanır. Karakter karşılık gelen geniş null karakter ise, *mbstate* ortaya çıkan durum ilk dönüşüm durumudur.

**Mbrtowc** fonksiyonu [mbtowc farklıdır, _mbtowc_l](mbtowc-mbtowc-l.md) yeniden başlatılabilirlik. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır.  Örneğin, **wcsrtombs**yerine daha sonra **wcsrtombs** için bir sonraki çağrı kullanılırsa bir uygulama **wcsrlen yerine wcsrlen** kullanmalıdır. **wcslen**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="example"></a>Örnek

Çok baytlı bir karakteri geniş karakter eşdeğerine dönüştürür.

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
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
