---
title: wcstombs, _wcstombs_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstombs
- _wcstombs_l
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
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: facc4855d1e36965eff7af70c5cb48f8fb77d419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l

Geniş bir karakter dizisi birden çok baytlı karakterler karşılık gelen bir dizi dönüştürür. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t wcstombs(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count
);
size_t _wcstombs_l(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t wcstombs(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only
template <size_t size>
size_t _wcstombs_l(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*mbstr*<br/>
Birden çok baytlı karakter dizisi adresi.

*wcstr*<br/>
Geniş bir karakter dizisi adresi.

*Sayısı*<br/>
Birden çok baytlı çıkış dizesi içinde depolanan bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Varsa **wcstombs** başarıyla baytlı dizeye dönüştürür sonlandırma hariç olmak üzere birden çok baytlı çıkış dizeye yazılan bayt sayısını döndürür **NULL** (varsa). Varsa *mbstr* bağımsız değişkeni **NULL**, **wcstombs** gereken boyut hedef dizesi bayt cinsinden döndürür. Varsa **wcstombs** birden çok baytlı karakter dönüştüremiyor geniş karakter karşılaştığında yazmak için cast -1 döndürür **size_t** ve ayarlar **errno** için **EILSEQ** .

## <a name="remarks"></a>Açıklamalar

**Wcstombs** işlevi dönüştürür gösterdiği geniş karakter dizesi *wcstr* için karşılık gelen çok baytlı karakter ve sonuçları depolar *mbstr* dizi. *Sayısı* parametresi birden çok baytlı çıkış dizesi içinde depolanan bayt sayısını belirtir (diğer bir deyişle, boyutu *mbstr*). Genel olarak, bir joker karakter dizesi dönüştürülürken kaç bayt gerekli olacak bilinmiyor. Bazı uluslararası karakterler yalnızca tek baytlık çıkış dizesinde gerektirir; diğer iki gerektirir. Giriş dizisinde her geniş karakter birden çok baytlı çıkış dizesinde iki bayt varsa (geniş karakter dahil olmak üzere **NULL**), sonuç uyacak şekilde sağlanır.

Varsa **wcstombs** joker karakter null karakteri (M '\0') önce veya ne zaman karşılaşırsa *sayısı* oluşur, dönüştürür, 8 bit 0 ve durdurur. Bu nedenle, birden çok baytlı karakter dizesi adresindeki *mbstr* null-yalnızca sonlandırılır **wcstombs** bir joker karakter null karakter dönüştürme sırasında karşılaşır. Dizileri gösterdiği varsa *wcstr* ve *mbstr* üst üste, davranışını **wcstombs** tanımlanmadı.

Varsa *mbstr* bağımsız değişkeni **NULL**, **wcstombs** gereken boyut hedef dizesi bayt cinsinden döndürür.

**wcstombs** parametrelerini doğrular. Varsa *wcstr* olan **NULL**, veya *sayısı* değerinden daha büyük **INT_MAX**, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [Parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, işlevi ayarlar **errno** için **EINVAL** ve -1 döndürür.

**wcstombs** geçerli yerel ayar için tüm yerel ayara bağımlı davranışı; kullanır **_wcstombs_l** yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h >|
|**_wcstombs_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu programın davranışını gösterilmektedir **wcstombs** işlevi.

```C
// crt_wcstombs.c
// compile with: /W3
// This example demonstrates the use
// of wcstombs, which converts a string
// of wide characters to a string of
// multibyte characters.

#include <stdlib.h>
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t  count;
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t *pWCBuffer = L"Hello, world.";

    printf("Convert wide-character string:\n" );

    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s instead
    printf("   Characters converted: %u\n",
            count );
    printf("    Multibyte character: %s\n\n",
           pMBBuffer );

    free(pMBBuffer);
}
```

```Output
Convert wide-character string:
   Characters converted: 13
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
