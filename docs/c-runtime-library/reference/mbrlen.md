---
title: mbrlen
ms.date: 11/04/2016
apiname:
- mbrlen
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
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 75ae134db0e74099a9b19f4820a44a197fdfda2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438460"
---
# <a name="mbrlen"></a>mbrlen

Çok baytlı bir karakterin çok baytlı bir karakterin ortasında yeniden başlatma özelliği ile geçerli ayardaki tamamlamak için gereken bayt sayısını belirler.

## <a name="syntax"></a>Sözdizimi

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
İşaretçi bir çok baytlı karakterin dizede incelemek için sonraki baytı.

*Sayısı*<br/>
İncelemek için bayt sayısı.

*mbstate*<br/>
İlk bayt geçerli shift durumuna yönelik işaretçi *str*.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

|||
|-|-|
0|Sonraki *sayısı* veya daha az bayt geniş null karakter temsil eden bir çok baytlı karakter.
1 *sayısı*(dahil)|Sonraki *sayısı* veya daha az bayt geçerli çok baytlı bir karakterin tamamlayın. Döndürülen değer çok baytlı karakteri tamamlamak bayt sayısıdır.
(size_t) -(2)|Sonraki *sayısı* bayt tamamlanmamış ancak potansiyel olarak geçerli bir çok baytlı karakter ve tüm katkıda *sayısı* bayt işlenir.
(size_t)(-1)|Kodlama bir hata oluştu. Sonraki *sayısı* veya daha az bayt tam ve geçerli çok baytlı karakter katkıda bulunmuyor. Bu durumda, **errno** EILSEQ ve dönüştürme durumda ayarlanır *mbstate* belirtilmemiş.

## <a name="remarks"></a>Açıklamalar

**Mbrlen** işlevi inceler en fazla *sayısı* bayt bayt ile başlayan tarafından işaret edilen *str* sonraki tamamlamak için gereken bayt sayısını belirlemek için tüm üst karakter sıraları dahil olmak üzere çok baytlı karakter. Çağrısına eşdeğerdir `mbrtowc(NULL, str, count, &mbstate)` burada *mbstate* ya da bir kullanıcı tarafından sağlanan olduğu **mbstate_t** nesne veya statik kitaplığı tarafından sağlanan iç nesne.

**Mbrlen** işlevi kaydeder ve tamamlanmamış bir çok baytlı karakter kaydırma durumu kullanır *mbstate* parametresi. Bu verir **mbrlen** ortasında bir çok baytlı karakterin yeniden başlatmayı yeteneği olması, en fazla inceleme *sayısı* bayt. Varsa *mbstate* null bir işaretçiyse, **mbrlen** kullanan bir dahili statik **mbstate_t** shift durumunu depolamak için nesne. Olduğundan iç **mbstate_t** nesne iş parçacığı güvenli değil, her zaman ayırın ve kendi geçmesini öneririz *mbstate* parametresi.

**Mbrlen** işlevi farklıdır [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) kendi restartability tarafından. Kaydırma durumu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır.  Örneğin, bir uygulamanın kullanması gereken **wcsrlen** yerine **wcslen** sonraki çağrı, **wcsrtombs** yerine kullanılan **wcstombs**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|Uygulanamaz|Uygulanamaz|**mbrlen**|Uygulanamaz|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbrlen**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek nasıl yorumunu birden çok baytlı karakterler geçerli kod sayfasına bağlıdır ve sürdürme yeteneğini gösterir gösterir **mbrlen**.

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

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
