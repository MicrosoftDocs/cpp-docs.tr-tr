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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 4107ae6cb6366fa8ad80251ce94ee35ca59501bd
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910651"
---
# <a name="wcrtomb"></a>wcrtomb

Geniş bir karakteri çok baytlı karakter gösterimine dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [wcrtomb_s](wcrtomb-s.md).

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
Elde edilen çok baytlı karakter dönüştürülmüş karakteri.

*wchar*<br/>
Dönüştürülecek geniş bir karakter.

*mbstate*<br/>
**Mbstate_t** nesnesine yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dönüştürülmüş çok baytlı karakteri temsil etmek için gereken bayt sayısını, aksi takdirde bir hata oluşursa-1 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**Wcrtomb** işlevi, belirtilen dönüştürme durumundan *başlayarak,* *wchar*içinde bulunan değerden *mbchar*tarafından temsil edilen adrese kadar geniş bir karakter dönüştürür. Dönüş değeri, karşılık gelen çok baytlı karakteri temsil etmek için gereken bayt sayısıdır, ancak **MB_CUR_MAX** bayttan daha fazla dönmeyecektir.

*Mbstate* null ise, *mbchar* 'ın dönüştürme durumunu içeren iç **mbstate_t** nesnesi kullanılır. *Wchar* karakter dizisinin karşılık gelen bir çok baytlı karakter temsili yoksa,-1 döndürülür ve **errno** , **eilseq**olarak ayarlanır.

**Wcrtomb** işlevi [wctomb 'den farklı, _wctomb_l](wctomb-wctomb-l.md) yeniden başlangıçlarından farklıdır. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır. Örneğin, bir uygulama **wcsnlen**yerine **wcsrlen** s çağrısı, **wcstomb**yerine daha sonra bir **wcsrkaldırıldı** for çağrısı kullanıldıysa,.

C++ ' da, bu işlevin, bu işlevin daha yeni ve güvenli karşılıklarıyla ilgili bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="exceptions"></a>Özel durumlar

Geçerli iş parçacığında hiçbir işlev bu işlev yürütülürken ve *mbstate* null olduğunda, **wcrtomb** işlevi **setlocale** iş parçacığı açısından güvenlidir.

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
|**wcrtomb**|\<wchar. h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
