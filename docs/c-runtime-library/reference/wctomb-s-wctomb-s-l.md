---
title: wctomb_s, _wctomb_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7812eeb234676b84d9f6e8077c895e958dd45281
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l

Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürür. Bir sürümünü [wctomb, _wctomb_l](wctomb-wctomb-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Bayt veya sonucu gösteren bir kod sayısı.

*mbchar*<br/>
Birden çok baytlı karakter adresi.

*sizeInBytes*<br/>
Arabellek boyutu *mbchar*.

*wchar*<br/>
Geniş karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı olursa, hatasında bir hata kodu.

Hata koşulları

|*mbchar*|*sizeInBytes*|Dönüş değeri|*pRetValue*|
|--------------|-------------------|------------------|-----------------|
|**NULL**|>0|**EINVAL**|değiştirilmedi|
|tüm|>**INT_MAX**|**EINVAL**|değiştirilmedi|
|tüm|çok küçük|**EINVAL**|değiştirilmedi|

Yukarıdaki hata koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **wctomb** döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**Wctomb_s** işlev dönüştürür kendi *wchar* karşılık gelen birden çok baytlı karakter bağımsız değişkeni ve sonucunda depolar *mbchar*. Herhangi bir noktadan herhangi bir programda işlevini çağırın.

Varsa **wctomb_s** geniş karakter dönüştürür isteğe bağlı olarak birden çok baytlı karakter bayt sayısı koyar (hangi asla büyük **MB_CUR_MAX**) tarafından işaretdeğeritamsayıyagenişkarakter*pRetValue*. Varsa *wchar* joker karakter null karakteri (M '\0'), **wctomb_s** doldurur *pRetValue* 1. Varsa hedef işaretçi *mbchar* null, **wctomb_s** 0 koyar *pRetValue*. Dönüştürme geçerli yerel ayarda mümkün değilse, **wctomb_s** -1 koyar *pRetValue*.

**wctomb_s** geçerli yerel ayar için yerel ayara bağımlı bilgileri; kullanır **_wctomb_s_l** yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb_s**|\<stdlib.h >|
|**_wctomb_s_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu programın davranışını gösterilmektedir **wctomb** işlevi.

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
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
