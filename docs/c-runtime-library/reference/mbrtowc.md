---
title: mbrtowc
ms.date: 11/04/2016
api_name:
- mbrtowc
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: b4c68ae8df9821d862b9f742d8a8ef7ace19c981
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952437"
---
# <a name="mbrtowc"></a>mbrtowc

Geçerli yerel ayarda bulunan çok baytlı bir karakteri, çok baytlı bir karakterin ortasında yeniden başlatma özelliği ile eşdeğer geniş karaktere dönüştürün.

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
Dönüştürülmüş geniş karakter dizesini (türü **wchar_t**) almak için geniş bir karakterin adresi. Bu değer, return Wide character gerekmiyorsa null bir işaretçi olabilir.

*mbchar*<br/>
Bir bayt dizisinin adresi (çok baytlı bir karakter).

*biriktirme*<br/>
Denetlenecek bayt sayısı.

*mbstate*<br/>
Dönüştürme durumu nesnesine yönelik işaretçi. Bu değer null işaretçisiyse, işlev statik bir iç dönüştürme durumu nesnesi kullanır. İç **mbstate_t** nesnesi iş parçacığı açısından güvenli olmadığından, her zaman kendi *mbstate* bağımsız değişkenini geçirmeniz önerilir.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

0 sonraki *sayı* veya daha az bayt *, wchar* null bir işaretçi değilse *wchar*içinde saklanan null geniş karakteri temsil eden çok baytlı karakteri tamamlar.

1- *Count*, sonraki *sayı* dahil olmak üzere veya daha az bayt geçerli bir çok baytlı karakter tamamlanmıştır. Döndürülen değer, çok baytlı karakteri Tamamlanan bayt sayısıdır. *Wchar* null bir işaretçi değilse, geniş karakter eşdeğeri *wchar*'da depolanır.

(size_t) (-1) Bir kodlama hatası oluştu. Sonraki *sayı* veya daha az bayt, bir bütün ve geçerli çok baytlı karaktere katkıda bulunmuyor. Bu durumda, **errno** EILSEQ olarak ayarlanır ve *mbstate* 'teki dönüştürme kaydırma durumu belirtilmemiş olur.

(size_t) (-2) *Sıradaki bayt sayısı,* tamamlanmamış ancak büyük olasılıkla geçerli çok baytlı bir karaktere katkıda bulunur ve tüm *sayım* baytları işlenir. *Wchar*'da hiçbir değer depolanmaz, ancak işlevi yeniden başlatmak için *mbstate* güncellenir.

## <a name="remarks"></a>Açıklamalar

*Mbchar* null işaretçisiyse, işlev çağrıya eşdeğerdir:

`mbrtowc(NULL, "", 1, &mbstate)`

Bu durumda, *wchar* ve *Count* bağımsız değişkenlerinin değeri yok sayılır.

*Mbchar* null bir işaretçi değilse, işlev, sonraki çok baytlı karakteri tamamlaması gereken bayt sayısını öğrenmek için *mbchar* 'dan *sayı* baytlarını inceler. Sonraki karakter geçerliyse, bir null işaretçi değilse, karşılık gelen çok baytlı karakter *wchar* 'da depolanır. Karakter, karşılık gelen geniş null karakter ise, *mbstate* sonuç durumu ilk dönüştürme durumudur.

**Mbrtowc** işlevi [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) öğesinden yeniden startability 'a göre farklılık gösterir. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır.  Örneğin, bir uygulama, **wcstomb**yerine **wcsrkaldırıldı s** öğesine yapılan sonraki bir çağrı kullanılırsa **wcslen** yerine **wcsrlen** kullanmalıdır.

## <a name="example"></a>Örnek

Çok baytlı bir karakteri, geniş karakter eşdeğerine dönüştürür.

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
|**mbrtowc**|\<wchar. h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
