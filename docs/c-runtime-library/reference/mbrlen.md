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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 2e0e0ec9d92744fc904bae5ac7f91db8049de4cd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842123"
---
# <a name="mbrlen"></a>mbrlen

Çok baytlı bir karakterin ortasında yeniden başlatma özelliği ile geçerli yerel ayarda çok baytlı bir karakteri tamamlamaya yönelik gereken bayt sayısını belirleme.

## <a name="syntax"></a>Söz dizimi

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Çok baytlı bir karakter dizesinde incelemek için sonraki bayta yönelik işaretçi.

*count*<br/>
İncelenecek en fazla bayt sayısı.

*mbstate*<br/>
*Str*ilk baytının geçerli kaydırma durumuna yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

| Değer | Açıklama |
|--|--|
| 0 | Sonraki *sayı* veya daha az bayt, geniş boş karakteri temsil eden çok baytlı karakteri tamamlar. |
| 1- *Count*, dahil | Sonraki *sayı* veya daha az bayt geçerli bir çok baytlı karakteri tamamlar. Döndürülen değer, çok baytlı karakteri Tamamlanan bayt sayısıdır. |
| (size_t) (-2) | *Sıradaki bayt sayısı,* tamamlanmamış ancak büyük olasılıkla geçerli çok baytlı bir karaktere katkıda bulunur ve tüm *sayım* baytları işlenir. |
| (size_t) (-1) | Bir kodlama hatası oluştu. Sonraki *sayı* veya daha az bayt, bir bütün ve geçerli çok baytlı karaktere katkıda bulunmuyor. Bu durumda, **errno** EILSEQ olarak ayarlanır ve *mbstate* 'teki dönüştürme durumu belirtilmemiş olur. |

## <a name="remarks"></a>Açıklamalar

**Mbrlen** işlevi, tüm kaydırma dizileri dahil olmak üzere bir sonraki çok baytlı karakteri tamamlaması gereken bayt sayısını öğrenmek için *Str* tarafından işaret edilen bayt ile başlayan en fazla *sayıda* baytı inceler. `mbrtowc(NULL, str, count, &mbstate)` *Mbstate* 'in kullanıcı tarafından sağlanmış **mbstate_t** nesne veya kitaplık tarafından sunulan statik bir dahili nesne olduğu çağrıya eşdeğerdir.

**Mbrlen** işlevi, *mbstate* parametresinde tamamlanmamış bir çok baytlı karakterin vardiya durumunu kaydeder ve kullanır. Bu, daha çok baytlı bir karakterin ortasında yeniden başlatma yeteneğini, gerekirse en fazla *sayıda* baytı inceleyerek **mbrlen** özelliğini sağlar. *Mbstate* null işaretçisiyse **mbrlen** , SHIFT durumunu depolamak için bir iç, statik **mbstate_t** nesnesi kullanır. İç **mbstate_t** nesnesi iş parçacığı açısından güvenli olmadığından, her zaman kendi *mbstate* parametresini ayırmanız ve geçirmeniz önerilir.

**Mbrlen** işlevi, yeniden başlangıçından [_mbclen, mblen _mblen_l](mbclen-mblen-mblen-l.md) farklıdır. Kaydırma durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* içinde depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır.  Örneğin, bir uygulama, **wcstomb**yerine **wcsrkaldırıldı s** öğesine yapılan sonraki bir çağrı kullanılırsa **wcslen** yerine **wcsrlen** kullanmalıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|uygulanamaz|uygulanamaz|**mbrlen**|uygulanamaz|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek, çok baytlı karakterlerin nasıl yorumlandığının geçerli kod sayfasına nasıl bağlı olduğunu gösterir ve **mbrlen**'ın sürdürme özelliğini gösterir.

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
