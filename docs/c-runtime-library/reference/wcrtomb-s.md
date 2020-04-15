---
title: wcrtomb_s
ms.date: 4/2/2020
api_name:
- wcrtomb_s
- _o_wcrtomb_s
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
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: ee25b18bfbb86b34e46c8c6776e8ab83157613e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328175"
---
# <a name="wcrtomb_s"></a>wcrtomb_s

Geniş bir karakteri çok bayt karakter gösterimine dönüştürün. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [wcrtomb](wcrtomb.md) bir sürümü.

## <a name="syntax"></a>Sözdizimi

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*pReturnValue*<br/>
Bir hata oluştuysa, yazılan bayt sayısını veya -1'i verir.

*mbchar*<br/>
Ortaya çıkan çok bayt dönüştürülmüş karakter.

*boyutOfmbchar*<br/>
Byte'deki *mbchar* değişkeninin boyutu.

*Wchar*<br/>
Dönüştürmek için geniş bir karakter.

*mbstate*<br/>
**mbstate_t** bir nesneye işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa sıfır veya **errno** değeri döndürür.

## <a name="remarks"></a>Açıklamalar

**wcrtomb_s** işlevi, *mbchar'da*bulunan belirtilen dönüşüm durumundan başlayarak, *wchar'da*bulunan değerden *mbchar*tarafından temsil edilen adrese geniş bir karakter dönüştürür. *pReturnValue* değeri dönüştürülen bayt sayısı dır, ancak bir hata oluştuysa **MB_CUR_MAX** baytveya -1'den fazla olamaz.

*Mbstate* null ise, iç **mbstate_t** dönüştürme durumu kullanılır. *Wchar'da* bulunan karakter karşılık gelen çok bayt karaktere sahip değilse, *pReturnValue* değeri -1 olur ve işlev **EILSEQ'nin** **errno** değerini döndürecektir.

**wcrtomb_s** [işlevi,](wctomb-s-wctomb-s-l.md) yeniden başlatılabilirliği _wctomb_s_l wctomb_s farklıdır. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır. Örneğin, bir uygulama **wcsrlen** yerine **wcsrlen**kullanır , **wcsrtombs_s** için sonraki bir çağrı **wcstombs_s**yerine kullanıldı.

C++'da, bu işlevi kullanmak şablon aşırı yüklemeleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="exceptions"></a>Özel durumlar

Bu işlev yürütülerken ve *mbstate* null iken geçerli iş parçacığı çağıran **ayaryerel** sürece **wcrtomb_s** işlevi çok iş parçacığı güvenlidir.

## <a name="example"></a>Örnek

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
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
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
