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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: fb95c6d73a3979a39995b9104a76fc42ca9e8535
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366714"
---
# <a name="wcstombs-_wcstombs_l"></a>wcstombs, _wcstombs_l

Geniş karakter dizisini karşılık gelen çok bayt karakter dizisine dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; [bkz wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md).

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
Çok bayt karakter dizisinin adresi.

*Wcstr*<br/>
Geniş karakter dizisinin adresi.

*Sayısı*<br/>
Çok bayt çıkış dizesinde depolanabilecek maksimum bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**Wcstombs** multibayt dizesini başarıyla dönüştürürse, null sonlandırma (varsa) hariç, multibayt çıkış dizesine yazılan bayt sayısını döndürür. *Mbstr* bağımsız değişkeni **NULL**ise, **wcstombs** hedef dize baytlar gerekli boyutu döndürür. **Wcstombs** çok bayt karaktere dönüştüremez geniş bir karakter karşılaşırsa, **size_t** türüne -1 döküm döndürür ve **EILSEQ** **için errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**WCStombs** işlevi, *wcstr* tarafından işaret edilen geniş karakterli dizeyi ilgili çok bayt karakterlere dönüştürür ve sonuçları *mbstr* dizisinde saklar. *Sayım* parametresi, çok bayt çıkış dizesinde depolanabilecek maksimum bayt sayısını (diğer bir deyişle *mbstr*boyutu) gösterir. Genel olarak, geniş karakterli bir dize dönüştürülürken kaç bayt gerekeceği bilinmemektedir. Bazı geniş karakterler çıkış dizesinde yalnızca bir bayt gerektirir; diğerleri iki gerektirir. Giriş dizesindeki her geniş karakter için çok bayt çıkış dizesinde iki bayt varsa (geniş karakter null dahil), sonucun uyması garanti edilir.

**Wcstombs,** sayım gerçekleşmeden önce veya *sayıldığında* geniş karakterli null karakteriyle (L'\0') karşılaşırsa, 8-bit 0'a dönüştürür ve durur. Böylece, *mbstr'deki* çok bayt karakter dizesi, ancak **wcstombs'un** dönüştürme sırasında geniş karakterli null karakteriyle karşılaşması durumunda geçersiz kılınır. *Wcstr* ve *mbstr* çakışma ile işaret edilen diziler ise, **wcstombs** davranışı tanımsız.

*Mbstr* bağımsız değişkeni **NULL**ise, **wcstombs** hedef dize baytlar gerekli boyutu döndürür.

**wcstombs** parametrelerini doğrular. *WCSTR* **NULL**ise veya *sayı* **INT_MAX**büyükse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin verilirse, işlev **errno'yu** **EINVAL'e** ayarlar ve -1 döndürür.

**wcstombs** herhangi bir yerel bağımlı davranış için geçerli yerel kullanır; **_wcstombs_l,** bunun yerine geçirilen yerel liği kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program **wcstombs** işlevinin davranışını göstermektedir.

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
