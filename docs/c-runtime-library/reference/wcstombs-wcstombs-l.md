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
ms.openlocfilehash: 5cbc89ff9a6c353b0df1df606a08a8c2515ed04a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217140"
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l

Karşılık gelen çok baytlı bir karakter dizisi için bir dizi geniş karakteri dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md).

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
Çok baytlı bir karakter dizisi adresi.

*wcstr*<br/>
Geniş bir karakter dizisi adresi.

*Sayısı*<br/>
Çok baytlı çıktı dizesinde depolanan bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Varsa **wcstombs** başarıyla çok baytlı bir dize dönüştürür (varsa) Sonlandırıcı null dışında çok baytlı çıkış dizeye yazılan bayt sayısını döndürür. Varsa *mbstr* bağımsız değişkeni **NULL**, **wcstombs** gerekli boyutu hedef dize baytı cinsinden döndürür. Varsa **wcstombs** bir çok baytlı karakterin dönüştüremiyor uluslararası bir karakterle karşılaştığında türüne yapılan -1 döndürür **size_t** ve ayarlar **errno** için **EILSEQ** .

## <a name="remarks"></a>Açıklamalar

**Wcstombs** işlevi tarafından işaret edilen geniş karakterli dize dönüştürür *wcstr* için karşılık gelen çok baytlı karakter ve sonuçlarda depolar *mbstr* dizisi. *Sayısı* parametresi en büyük çok baytlı çıktı dizesinde depolanan bayt sayısını gösterir (diğer bir deyişle, boyutu *mbstr*). Genel olarak, bir geniş karakter dizesi dönüştürülürken kaç bayt gerekli olacaktır bilinmiyor. Bazı geniş karakterler yalnızca tek bir bayt çıkış dizesindeki gerektirir; diğerleri ise iki gerektirir. (Geniş karakter null dahil) giriş dizesindeki her geniş karakter için çok baytlı çıktı dizesinde iki bayt varsa, sonuç uyacak şekilde sağlanır.

Varsa **wcstombs** geniş karakterli null karakteri (L '\0') önce veya ne zaman karşılaştığında *sayısı* gerçekleşir dönüştürür, 8 bitlik 0 ve durur. Bu nedenle, çok baytlı karakter dizesi *mbstr* yalnızca aşağıdaki durumlarda sonlandırılmış **wcstombs** dönüştürme sırasında bir geniş karakterli null karakterini karşılaşır. Dizileri işaret ettiği varsa *wcstr* ve *mbstr* üst üste, davranışını **wcstombs** tanımsızdır.

Varsa *mbstr* bağımsız değişkeni **NULL**, **wcstombs** gerekli boyutu hedef dize baytı cinsinden döndürür.

**wcstombs** kendi parametrelerini doğrular. Varsa *wcstr* olduğu **NULL**, veya *sayısı* büyüktür **INT_MAX**, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse işlev ayarlar **errno** için **EINVAL** ve -1 döndürür.

**wcstombs** herhangi bir yerel ayara bağımlı davranış için; geçerli yerel ayarı kullanır **_wcstombs_l** bunun yerine iletilmiş yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h >|
|**_wcstombs_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program davranışlarını gösterir **wcstombs** işlevi.

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
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
