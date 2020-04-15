---
title: wctomb_s, _wctomb_s_l
ms.date: 4/2/2020
api_name:
- _wctomb_s_l
- wctomb_s
- _o__wctomb_s_l
- _o_wctomb_s
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
ms.openlocfilehash: 1ddc9a991f28c4a2ea491f3ddd04d78f6345e255
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367246"
---
# <a name="wctomb_s-_wctomb_s_l"></a>wctomb_s, _wctomb_s_l

Geniş bir karakteri karşılık gelen çok bayt karaktere dönüştürür. [WCT'de Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleriyle [_wctomb_l wctomb'un](wctomb-wctomb-l.md) bir sürümü.

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

*sizeBytes*<br/>
Arabellek *mbchar*boyutu .

*Wchar*<br/>
Geniş bir karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, hata bir hata kodu.

Hata Koşulları

|*mbchar*|*sizeBytes*|Döndürülen değer|*pRetValue*|
|--------------|-------------------|------------------|-----------------|
|**Null**|>0|**Eınval**|değiştirilmemiş|
|herhangi bir|>**INT_MAX**|**Eınval**|değiştirilmemiş|
|herhangi bir|çok küçük|**Eınval**|değiştirilmemiş|

Yukarıdaki hata koşullarından herhangi biri oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **wctomb** **EINVAL** döndürür ve **EINVAL** **için errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**wctomb_s** işlevi *wchar* bağımsız değişkenini ilgili çok bayt karakterine dönüştürür ve sonucu *mbchar'da*depolar. İşlevi herhangi bir programdaki herhangi bir noktadan arayabilirsiniz.

**wctomb_s** geniş karakteri çok bayt karaktere dönüştürürse, geniş karakterdeki bayt sayısını **(MB_CUR_MAX'den**büyük olmayan) *pRetValue*tarafından işaret edilen tamsayıya koyar. *Wchar* geniş karakterli null karakter (L'\0') ise, **wctomb_s** *pRetValue'ı* 1 ile doldurur. Hedef işaretçi *mbchar* **NULL**ise, **wctomb_s** *pRetValue*0 koyar. Dönüştürme geçerli yerel olarak mümkün değilse, **wctomb_s** *pRetValue*'e -1 koyar.

**wctomb_s,** yerel bilgilere bağımlı bilgiler için geçerli yerel durumu kullanır; **_wctomb_s_l,** bunun yerine geçirilen yerel alanı kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb_s**|\<stdlib.h>|
|**_wctomb_s_l**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program **wctomb** işlevinin davranışını göstermektedir.

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
