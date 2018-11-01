---
title: wcstombs_s, _wcstombs_s_l
ms.date: 11/04/2016
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
ms.openlocfilehash: c9dc361139f8830b38910333fabedc371d84fcda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579068"
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

Karşılık gelen çok baytlı bir karakter dizisi için bir dizi geniş karakteri dönüştürür. Bir sürümünü [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*pReturnValue*<br/>
Dönüştürülecek karakter sayısı.

*mbstr*<br/>
Arabellek için ortaya çıkan dönüştürülmüş çok baytlı karakter dizesi adresi.

*sizeInBytes*<br/>
Bayt cinsinden boyutu *mbstr* arabellek.

*wcstr*<br/>
Dönüştürülecek geniş karakter dizesine işaret eder.

*Sayısı*<br/>
Depolamak için bayt sayısı *mbstr* arabellek, sonlandırıcı null karakter de dahil değil veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, bir hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* olduğu **NULL** ve *sizeInBytes* > 0|**EINVAL**|
|*wcstr* olduğu **NULL**|**EINVAL**|
|Hedef arabelleğinin içeren dönüştürülmüş dize çok küçük (sürece *sayısı* olduğu **_TRUNCATE**; aşağıdaki açıklamalara bakın)|**ERANGE**|

Bu koşullardan herhangi biri meydana gelirse, açıklanan şekilde geçersiz parametre özel durumu çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse işlev bir hata kodu döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Wcstombs_s** işlevi dönüştürür bir işaret ettiği geniş karakter dizesi *wcstr* çok baytlı karakter tarafından işaret edilen arabellek depolanan içine *mbstr*. Dönüştürme, her karakter için şu koşullardan biri karşılandığında kadar devam eder:

- Bir null geniş karakter karşılaşıldı

- Dönüştürülemeyen bir geniş karakter karşılaşıldı

- İçinde depolanan bayt sayısını *mbstr* arabellek eşittir *sayısı*.

Hedef dize her zaman null ile sonlandırılmış (bile bir hata olması durumunda).

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından **wcstombs_s** büyük bir işlem olarak dize dönüştürür yine de bir null yer bırakarak hedef arabellek içine Sığdır Sonlandırıcı. Dize kesildi, dönüş değeri olduğu **STRUNCATE**, ve Dönüştürme başarılı olarak kabul edilir.

Varsa **wcstombs_s** başarılı bir şekilde kaynak dizesini dönüştürür dönüştürülmüş dize halinde null sonlandırıcıyı da dahil olmak üzere, bayt cinsinden boyutu koyar  *&#42;pReturnValue* (sağlanan  *pReturnValue* değil **NULL**). Bu meydana bile *mbstr* bağımsız değişkeni **NULL** ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın *mbstr* olduğu **NULL**, *sayısı* göz ardı edilir.

Varsa **wcstombs_s** karşılaştığında bir çok baytlı karakterin dönüştüremiyor bir geniş karakter 0 koyar  *&#42;pReturnValue*, için boş bir dize hedef arabelleğinin ayarlar, ayarlar **errno**  için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri işaret ettiği varsa *wcstr* ve *mbstr* üst üste, davranışını **wcstombs_s** tanımsızdır.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* örtüşmeyen ve *sayısı* doğru şekilde dönüştürmek için geniş karakter sayısını yansıtır.

**wcstombs_s** herhangi bir yerel ayara bağımlı davranış için; geçerli yerel ayarı kullanır **_wcstombs_s_l** aynıdır **wcstombs** bunun yerine iletilmiş yerel ayar kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program davranışlarını gösterir **wcstombs_s** işlevi.

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
