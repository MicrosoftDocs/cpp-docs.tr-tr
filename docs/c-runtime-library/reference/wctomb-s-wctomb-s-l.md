---
title: wctomb_s, _wctomb_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5bdc05f903c1313d4844be8d5fc4fa619505670
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195125"
---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l

Bir geniş karakter karşılık gelen çok baytlı karaktere dönüştürür. Bir sürümünü [wctomb, _wctomb_l](wctomb-wctomb-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Sonucu gösteren bir kod veya bayt sayısı.

*mbchar*<br/>
Çok baytlı bir karakterin adresi.

*sizeInBytes*<br/>
Arabellek boyutu *mbchar*.

*wchar*<br/>
Bir geniş karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, bir hata kodu.

Hata koşulları

|*mbchar*|*sizeInBytes*|Dönüş değeri|*pRetValue*|
|--------------|-------------------|------------------|-----------------|
|**NULL**|>0|**EINVAL**|değiştirilmedi|
|Tüm|>**INT_MAX**|**EINVAL**|değiştirilmedi|
|Tüm|çok küçük|**EINVAL**|değiştirilmedi|

Yukarıdaki hata durumlardan biri oluşursa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **wctomb** döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**Wctomb_s** işlev dönüştürür, *wchar* çok baytlı karaktere karşılık gelen bağımsız değişken ve sonucunda depolar *mbchar*. Herhangi bir programda herhangi bir noktasından işlevi çağırabilir.

Varsa **wctomb_s** geniş karakter dönüştürür isteğe bağlı olarak bir çok baytlı karakterin bayt sayısını getirir (olan hiçbir zaman büyüktür **MB_CUR_MAX**) geniş karakter tarafındanişaretedilentamsayıiçine*pRetValue*. Varsa *wchar* geniş karakterli null karakteri (L '\0') **wctomb_s** doldurur *pRetValue* 1. Hedef işaretçi *mbchar* olduğu **NULL**, **wctomb_s** 0 koyar *pRetValue*. Geçerli yerel ayarda dönüştürme mümkün değilse, **wctomb_s** -1 koyar *pRetValue*.

**wctomb_s** için yerel ayara bağlı bilgiler; geçerli yerel ayarı kullanır **_wctomb_s_l** bunun yerine iletilmiş yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb_s**|\<stdlib.h >|
|**_wctomb_s_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program davranışlarını gösterir **wctomb** işlevi.

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
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
