---
title: wctomb_s, _wctomb_s_l
ms.date: 11/04/2016
apiname:
- _wctomb_s_l
- wctomb_s
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
- wctomb_s
- _wctomb_s_l
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
ms.openlocfilehash: 1eaa6f0b81daaa7d8c7626398fe30b45ead979c3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498923"
---
# <a name="wctomb_s-_wctomb_s_l"></a>wctomb_s, _wctomb_s_l

Geniş bir karakteri karşılık gelen çok baytlı karaktere dönüştürür. Bir [wctomb, _wckaldırıldı _l](wctomb-wctomb-l.md) 'nin BIR sürümü [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t wctomb_s(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar
);
errno_t _wctomb_s_l(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*pRetValue*<br/>
Bayt sayısı veya sonucu gösteren bir kod.

*mbchar*<br/>
Çok baytlı bir karakterin adresi.

*sizeInBytes*<br/>
*Mbchar*arabelleğinin boyutu.

*wchar*<br/>
Geniş bir karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, hata durumunda hata kodu.

Hata koşulları

|*mbchar*|*sizeInBytes*|Dönüş değeri|*pRetValue*|
|--------------|-------------------|------------------|-----------------|
|**DEĞER**|>0|**EINVAL**|değiştirilmedi|
|kaydedilmemiş|>**INT_MAX**|**EINVAL**|değiştirilmedi|
|kaydedilmemiş|çok küçük|**EINVAL**|değiştirilmedi|

Yukarıdaki hata koşullarından herhangi biri oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa **wctomb** , **EINVAL** döndürür ve **errno** değerini **EINVAL**olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**Wctomb_s** işlevi, *wchar* bağımsız değişkenini karşılık gelen çok baytlı karaktere dönüştürür ve sonucu *mbchar*üzerinde depolar. İşlevi herhangi bir programda herhangi bir noktadan çağırabilirsiniz.

**Wctomb_s** geniş karakteri çok baytlı bir karaktere dönüştürdüğünde, geniş karakter içindeki bayt sayısını, *pRetValue*tarafından işaret edilen tamsayıyakoyar. *Wchar* , geniş karakterli null karakterdir (L ' \ 0 '), **Wctomb_s** *pRetValue değerini* 1 olarak doldurur. Hedef işaretçi *mbchar* değeri **null**Ise, **wctomb_s** *pRetValue*içine 0 koyar. Dönüştürme geçerli yerel ayarda mümkün değilse, **Wctomb_s** *pRetValue*içinde-1 koyar.

**wctomb_s** , yerel ayara bağımlı bilgiler için geçerli yerel ayarı kullanır; **_wckaldırıldı _s_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb_s**|\<Stdlib. h >|
|**_wctomb_s_l**|\<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program **wctomb** işlevinin davranışını gösterir.

```cpp
// crt_wctomb_s.cpp
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    int i;
    wchar_t wc = L'a';
    char *pmb = (char *)malloc( MB_CUR_MAX );

    printf_s( "Convert a wide character:\n" );
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );
    printf_s( "   Characters converted: %u\n", i );
    printf_s( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[Widechartoçok baytlı](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
