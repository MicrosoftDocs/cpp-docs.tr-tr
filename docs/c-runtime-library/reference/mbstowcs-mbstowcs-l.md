---
title: mbstowcs, _mbstowcs_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbstowcs
- _mbstowcs_l
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
- mbstowcs
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adc91c7b17c8f95434a6dfc63e816df6df32c186
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mbstowcs-mbstowcsl"></a>mbstowcs, _mbstowcs_l

Birden çok baytlı karakter dizisi geniş karakterler karşılık gelen bir dizi dönüştürür. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md).

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
Geniş bir karakter dizisi adresi.

*mbstr*<br/>
Boş bir dizi adresini birden çok baytlı karakterler sonlandırıldı.

*Sayısı*<br/>
Dönüştürmek için birden çok baytlı karakterler maksimum sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Varsa **mbstowcs** başarıyla kaynak dizesi dönüştürür dönüştürülen birden çok baytlı karakterlerin sayısını döndürür. Varsa *wcstr* bağımsız değişkeni **NULL**, işlevi gerekli boyutunu (geniş karakter) hedef dize döndürür. Varsa **mbstowcs** geçersiz bir birden çok baytlı karakter karşılaştığında -1 döndürür. Dönüş değeri ise *sayısı*, joker karakter dizesi null ile sonlandırılmış değil.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* çakışmaması ve *sayısı* doğru şekilde dönüştürmek için birden çok baytlı karakter sayısını yansıtır.

## <a name="remarks"></a>Açıklamalar

**Mbstowcs** işlevi dönüştürür kadar en fazla sayıda *sayısı* tarafından için birden çok baytlı karakterler işaret *mbstr* olan karşılık gelen geniş karakter dizesi için Geçerli bölgeye göre belirlenir. Sonuçta elde edilen geniş karakter dizesi tarafından temsil edilen adresindeki depolar *wcstr*. Sonuç çağrıları için bir dizi benzer [mbtowc](mbtowc-mbtowc-l.md). Varsa **mbstowcs** tek baytlı null karakteri ('\0') önce veya ne zaman karşılaşırsa *sayısı* oluşur, durdurur ve bir joker karakter null karakter (M '\0') null karakter dönüştürür. Böylece geniş karakter dizesini *wcstr* null-yalnızca bir null karakter dönüştürme sırasında karşılaşılırsa sonlandırılır. Dizileri gösterdiği varsa *wcstr* ve *mbstr* üst üste davranışı tanımlanmadı.

Varsa *wcstr* bağımsız değişkeni **NULL**, **mbstowcs** null Sonlandırıcı hariç dönüştürme işlemini oluşturacağı geniş karakter sayısını verir. Kaynak dizesi null ile sonlandırılmış döndürülecek için geçerli bir değer olmalıdır. Null ile sonlandırılmış olması için sonuçta elde edilen geniş karakter dizesi gerekiyorsa, döndürülen değer birine ekleyin.

Varsa *mbstr* bağımsız değişkeni **NULL**, veya *sayısı* olan > **INT_MAX**, anlatıldığıgibigeçersizparametreişleyicisiçağrılır[ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, errno kümesine **EINVAL** ve işlev -1 döndürür.

**mbstowcs** geçerli yerel ayar için tüm yerel ayara bağımlı davranışı; kullanır **_mbstowcs_l** yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbstowcs**|\<stdlib.h >|
|**_mbstowcs_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
    /* Add one to leave room for the NULL terminator */
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
[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)<br/>
