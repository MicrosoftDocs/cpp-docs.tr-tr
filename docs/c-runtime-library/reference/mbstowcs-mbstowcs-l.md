---
title: mbstowcs, _mbstowcs_l
ms.date: 11/04/2016
api_name:
- mbstowcs
- _mbstowcs_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbstowcs
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
ms.openlocfilehash: 3df851b08edfa9dfe5bf9b42b9abfd45a8939606
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952028"
---
# <a name="mbstowcs-_mbstowcs_l"></a>mbstowcs, _mbstowcs_l

Çok baytlı karakterlerden oluşan bir diziyi karşılık gelen geniş karakter dizisine dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t mbstowcs(
   wchar_t *wcstr,
   const char *mbstr,
   size_t count
);
size_t _mbstowcs_l(
   wchar_t *wcstr,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t mbstowcs(
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
size_t _mbstowcs_l(
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*wcstr*<br/>
Geniş karakter dizisinin adresi.

*mbstr*<br/>
Null ile sonlandırılmış çok baytlı karakterlerin bir dizisinin adresi.

*biriktirme*<br/>
Dönüştürülecek çok baytlı karakter sayısı üst sınırı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**Mbstowcs** kaynak dizeyi başarıyla dönüştürdüyse, dönüştürülmüş çok baytlı karakterlerin sayısını döndürür. *Wcstr* bağımsız değişkeni **null**ise, işlev hedef dizenin gereken boyutunu (geniş karakterlerle) döndürür. **Mbstowcs** geçersiz bir çok baytlı karakterle karşılaşırsa,-1 döndürür. Dönüş değeri *sayımla*, geniş karakterli dize null ile sonlandırılmaz.

> [!IMPORTANT]
> *Wcstr* ve *mbstr* 'in çakışmadığından ve bu *sayının* dönüştürülecek çok baytlı karakterlerin sayısını doğru yansıttığından emin olun.

## <a name="remarks"></a>Açıklamalar

**Mbstowcs** işlevi, *mbstr* tarafından işaret edilen en fazla sayıda *çok baytlı karakter* sayısını, geçerli yerel ayar tarafından belirlenen karşılık gelen geniş karakter dizesine dönüştürür. Elde edilen geniş karakterli dizeyi, *wcstr*tarafından temsil edilen adreste depolar. Sonuç [mbtowc](mbtowc-mbtowc-l.md)öğesine yapılan çağrı dizisine benzerdir. **Mbstowcs** tek baytlı null karakterle (' \ 0 ') karşılaşırsa, ya da bu *sayı* gerçekleştiğinde, null karakteri geniş karakterli bir null karaktere (L ' \ 0 ') dönüştürür ve duraklar. Bu nedenle, *wcstr* konumundaki geniş karakterli dize yalnızca dönüştürme sırasında null karakter ile karşılaşılırsa null olarak sonlandırılır. *Wcstr* ve *mbstr* tarafından işaret edilen diziler çakışırsa, davranış tanımsızdır.

*Wcstr* bağımsız değişkeni **null**ise, **mbstowcs** , null Sonlandırıcı dahil değil, dönüşümden kaynaklanan geniş karakter sayısını döndürür. Doğru değerin döndürülmesi için kaynak dize null ile sonlandırılmış olmalıdır. Sonuçta elde edilen geniş karakter dizesinin null sonlandırılmış olması gerekiyorsa, döndürülen değere bir tane ekleyin.

*Mbstr* bağımsız değişkeni **null**Ise veya *sayı* > **INT_MAX**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, errno **EINVAL** olarak ayarlanır ve işlev-1 döndürür.

**mbstowcs** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_mbstowcs_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

' C++De, bu işlevlerde bu işlevlerin daha yeni ve güvenli karşılıkları çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbstowcs**|\<Stdlib. h >|
|**_mbstowcs_l**|\<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbstowcs.c
// compile with: /W3
// illustrates the behavior of the mbstowcs function

#include <stdlib.h>
#include <stdio.h>
#include <locale.h>

int main( void )
{
    size_t size;
    int nChar = 2; // number of characters to convert
    int requiredSize;

    unsigned char    *pmbnull  = NULL;
    unsigned char    *pmbhello = NULL;
    char* localeInfo;

    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters
    wchar_t *pwc;

    /* Enable the Japanese locale and codepage */
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");
    printf("Locale information set to %s\n", localeInfo);

    printf( "Convert to multibyte string:\n" );

    requiredSize = wcstombs( NULL, pwchello, 0); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s
    printf("   Required Size: %d\n", requiredSize);

    /* Add one to leave room for the null terminator. */
    pmbhello = (unsigned char *)malloc( requiredSize + 1);
    if (! pmbhello)
    {
        printf("Memory allocation failure.\n");
        return 1;
    }
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s
    if (size == (size_t) (-1))
    {
        printf("Couldn't convert string. Code page 932 may"
                " not be available.\n");
        return 1;
    }
    printf( "   Number of bytes written to multibyte string: %u\n",
            (unsigned int) size );
    printf( "   Hex values of the" );
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );
    printf( "   Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");

    printf( "Convert back to wide-character string:\n" );

    /* Assume we don't know the length of the multibyte string.
     Get the required size in characters, and allocate enough space. */

    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996
    /* Add one to leave room for the null terminator */
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));
    if (! pwc)
    {
        printf("Memory allocation failure.\n");
        return 1;
    }
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996
    if (size == (size_t) (-1))
    {
       printf("Couldn't convert string--invalid multibyte character.\n");
    }
    printf( "   Characters converted: %u\n", (unsigned int)size );
    printf( "   Hex value of first 2" );
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );
    free(pwc);
    free(pmbhello);
}
```

```Output
Locale information set to Japanese_Japan.932
Convert to multibyte string:
   Required Size: 4
   Number of bytes written to multibyte string: 4
   Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1
   Codepage 932 uses 0x81 to 0x9f as lead bytes.

Convert back to wide-character string:
   Characters converted: 2
   Hex value of first 2 wide characters: 0x3042 0x3043
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
