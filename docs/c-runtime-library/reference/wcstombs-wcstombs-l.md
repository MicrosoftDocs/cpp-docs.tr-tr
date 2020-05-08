---
title: wcstombs, _wcstombs_l
ms.date: 4/2/2020
api_name:
- wcstombs
- _wcstombs_l
- _o__wcstombs_l
- _o_wcstombs
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcstombs
- _wcstombs_l
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
ms.openlocfilehash: 33c7554f1ab5c9822a1908a4b50d0ee0764615ae
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910632"
---
# <a name="wcstombs-_wcstombs_l"></a>wcstombs, _wcstombs_l

Geniş bir karakter dizisini karşılık gelen çok baytlı karakterler dizisine dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md).

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
Çok baytlı karakter dizisinin adresi.

*wcstr*<br/>
Geniş karakter dizisinin adresi.

*biriktirme*<br/>
Çok baytlı çıkış dizesinde depolanabilecek en fazla bayt sayısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**Wcstombs** çok baytlı dizeyi başarıyla dönüştürdüğünde, Sonlandırıcı null (varsa) hariç olmak üzere çok baytlı çıkış dizesine yazılan bayt sayısını döndürür. *Mbstr* bağımsız değişkeni **null**ise, **wcstombs** , hedef dizenin bayt cinsinden gereken boyutunu döndürür. **Wcstombs** , çok baytlı bir karaktere dönüştüremediği geniş bir karakterle karşılaşırsa, **size_t** türüne-1 atama döndürür ve **errno** 'u **eilseq**olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**Wcstombs** işlevi, *wcstr* tarafından işaret edilen geniş karakterli dizeyi karşılık gelen çok baytlı karakterlere dönüştürür ve sonuçları *mbstr* dizisinde depolar. *Count* parametresi, çok baytlı çıkış dizesinde depolanabilecek en fazla bayt sayısını (yani *mbstr*boyutunu) gösterir. Genel olarak, geniş karakterli bir dize dönüştürülürken kaç baytın gerekli olacağını bilinen değildir. Bazı geniş karakterler çıktı dizesinde yalnızca bir bayt gerektirir; diğerleri iki gerektirir. Giriş dizesindeki her geniş karakter için çok baytlı çıkış dizesinde iki bayt varsa (geniş karakter null değeri dahil), sonucun sığması garanti edilir.

**Wcstombs** geniş karakter null karakteriyle (L ' \ 0 ') karşılaşırsa veya bu *sayı* gerçekleştiğinde, bunu 8 bit 0 değerine dönüştürür ve duraklar. Bu nedenle, *mbstr* konumundaki çok baytlı karakter dizesi, dönüştürme sırasında yalnızca **wcstomb** bir geniş karakter null karakteriyle karşılaştığında null olarak sonlandırılır. *Wcstr* ve *mbstr* tarafından işaret edilen diziler çakışırsa, **wcstombs** davranışı tanımsızdır.

*Mbstr* bağımsız değişkeni **null**ise, **wcstombs** , hedef dizenin bayt cinsinden gereken boyutunu döndürür.

**wcstombs** , parametrelerini doğrular. *Wcstr* **null**ise veya *sayı* **INT_MAX**değerinden büyükse, bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md) açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür.

**wcstombs** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_wcstombs_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs**|\<Stdlib. h>|
|**_wcstombs_l**|\<Stdlib. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program **wcstombs** işlevinin davranışını gösterir.

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[Widechartoçok baytlı](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
