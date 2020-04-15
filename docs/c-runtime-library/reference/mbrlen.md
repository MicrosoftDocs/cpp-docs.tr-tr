---
title: mbrlen
ms.date: 4/2/2020
api_name:
- mbrlen
- _o_mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 7503de22a8310335ddd678335916d3e74dab6e70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340986"
---
# <a name="mbrlen"></a>mbrlen

Çok bayt karakterin ortasında yeniden başlatma özelliğiyle geçerli yerel eşteki çok bayt karakterini tamamlamak için gereken bayt sayısını belirleyin.

## <a name="syntax"></a>Sözdizimi

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Çok bayt karakter dizesini incelemek için bir sonraki bayt işaretleyin.

*Sayısı*<br/>
İncelenecek maksimum bayt sayısı.

*mbstate*<br/>
*Str'in*baş baytının geçerli kayma durumuna işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

|||
|-|-|
0|Sonraki *sayı* veya daha az bayt, geniş null karakterini temsil eden çok bayt karakterini tamamlar.
1 *saymak*, dahil|Sonraki *sayı* veya daha az bayt geçerli bir çok bayt karakterini tamamlar. Döndürülen değer, çok bayt karakterini tamamlayan bayt sayısıdır.
(size_t) (-2)|Sonraki *sayım* baytları eksik ama potansiyel olarak geçerli bir çok bayt karakterine katkıda bulunur ve tüm *sayım* baytları işlenir.
(size_t) (-1)|Bir kodlama hatası oluştu. Sonraki *sayı* veya daha az bayt tam ve geçerli bir çok bayt karaktere katkıda bulunmaz. Bu durumda, **errno** EILSEQ olarak ayarlanır ve *mbstate* dönüşüm durumu belirtilmemiştir.

## <a name="remarks"></a>Açıklamalar

**Mbrlen** işlevi, herhangi bir kaydırma dizisi de dahil olmak üzere bir sonraki çok bayt karakterini tamamlamak için gereken bayt sayısını belirlemek için *str* tarafından işaret edilen bayt ile başlayan en çok *sayı* baytını inceler. Mbstate'in kullanıcı `mbrtowc(NULL, str, count, &mbstate)` *mbstate* tarafından sağlanan **bir mbstate_t** nesnesi veya kitaplık tarafından sağlanan statik bir iç nesne olduğu çağrıya eşdeğerdir.

**mbrlen** işlevi *mbstate* parametresinde tamamlanmamış bir çok bayt karakterin kaydırma durumunu kaydeder ve kullanır. Bu **mbrlen** gerekirse çok bayt karakterin ortasında yeniden başlatma yeteneği verir, en *sayı* bayt inceleyerek. *Mbstate* null işaretçisi ise, **mbrlen** kaydırma durumunu depolamak için bir iç, statik **mbstate_t** nesnesi kullanır. İç **mbstate_t** nesnesi iş parçacığı için güvenli olmadığından, her zaman kendi *mbstate* parametrenizi ayırmanızı ve geçirmenizi öneririz.

**Mbrlen** işlevi [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) yeniden başlatılabilirliğinden farklıdır. Kaydırma durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır.  Örneğin, **wcsrtombs**yerine daha sonra **wcsrtombs** için bir sonraki çağrı kullanılırsa bir uygulama **wcsrlen yerine wcsrlen** kullanmalıdır. **wcslen**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|geçerli değildir|geçerli değildir|**mbrlen**|geçerli değildir|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu örnek, çok bayt karakterlerin yorumlanmasının geçerli kod sayfasına nasıl bağlı olduğunu gösterir ve **mbrlen'in**devam etme yeteneğini gösterir.

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

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
