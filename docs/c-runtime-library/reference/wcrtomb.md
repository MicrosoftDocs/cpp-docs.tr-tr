---
title: wcrtomb
ms.date: 4/2/2020
api_name:
- wcrtomb
- _o_wcrtomb
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
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: eda857b80404aebe46b090741e0b56d4fe692f34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328093"
---
# <a name="wcrtomb"></a>wcrtomb

Geniş bir karakteri çok bayt karakter gösterimine dönüştürün. Bu işlevin daha güvenli bir sürümü mevcuttur; [wcrtomb_s](wcrtomb-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*mbchar*<br/>
Ortaya çıkan çok bayt dönüştürülmüş karakter.

*Wchar*<br/>
Dönüştürmek için geniş bir karakter.

*mbstate*<br/>
**mbstate_t** bir nesneye işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dönüştürülen çok bayt karakterini temsil etmek için gereken bayt sayısını verir, aksi takdirde bir hata oluşursa -1.

## <a name="remarks"></a>Açıklamalar

**Wcrtomb** işlevi, *mbstate'te*bulunan belirtilen dönüşüm durumundan başlayarak, *wchar'da*bulunan değerden *mbchar*tarafından temsil edilen adrese geniş bir karakter dönüştürür. İade değeri, ilgili çok bayt karakterini temsil etmek için gereken bayt sayısıdır, ancak **MB_CUR_MAX** bayttan fazlasını döndürmez.

*Mbstate* null ise, *mbchar* dönüştürme durumunu içeren iç **mbstate_t** nesnesi kullanılır. Karakter dizisi *wchar* karşılık gelen bir çok bayt karakter gösterimi yoksa, bir -1 döndürülür ve **errno** **EILSEQ**olarak ayarlanır.

**Wcrtomb** işlevi [wctomb farklıdır, _wctomb_l](wctomb-wctomb-l.md) yeniden başlatılabilirlik. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır. Örneğin, bir uygulama **wcsnlen** yerine **wcsrlen**kullanır , **wcsrtombs** yerine sonraki **wcstombs**bir çağrı kullanıldı.

C++'da bu işlev, bu işlevin daha yeni ve güvenli karşıtlarını çağıran bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="exceptions"></a>Özel durumlar

**Wcrtomb** işlevi, geçerli iş parçacığındaki işlev bu işlev icra edilirken ve *mbstate* null iken **setlocale'yi** aradığı sürece çok iş parçacığı güvenlidir.

## <a name="example"></a>Örnek

```C
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
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
