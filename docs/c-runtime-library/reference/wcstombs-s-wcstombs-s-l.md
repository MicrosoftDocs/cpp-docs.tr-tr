---
title: wcstombs_s, _wcstombs_s_l
ms.date: 4/2/2020
api_name:
- _wcstombs_s_l
- wcstombs_s
- _o__wcstombs_s_l
- _o_wcstombs_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 7254df673694bf4d91679f1a41837c10f61d28e2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910603"
---
# <a name="wcstombs_s-_wcstombs_s_l"></a>wcstombs_s, _wcstombs_s_l

Geniş bir karakter dizisini karşılık gelen çok baytlı karakterler dizisine dönüştürür. Bir [wcstomb sürümü,](wcstombs-wcstombs-l.md) [CRT içindeki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan güvenlik geliştirmeleriyle _wcstombs_l.

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

*Ön kapatma değeri*<br/>
Null Sonlandırıcı dahil olmak üzere, dönüştürülmüş dizenin bayt cinsinden boyutu.

*mbstr*<br/>
Elde edilen dönüştürülmüş çok baytlı karakter dizesi için bir arabelleğin adresi.

*sizeInBytes*<br/>
*Mbstr* arabelleğinin bayt cinsinden boyutu.

*wcstr*<br/>
Dönüştürülecek geniş karakter dizesine işaret eder.

*biriktirme*<br/>
*Mbstr* arabelleğinde depolanacak, Sonlandırıcı null karakteri veya [_TRUNCATE](../../c-runtime-library/truncate.md)dahil olmayan en fazla bayt sayısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, hata durumunda hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* **null** ve *sizeInBytes* > 0|**EıNVAL**|
|*wcstr* **null**|**EıNVAL**|
|Hedef arabellek dönüştürülmüş dizeyi ( *sayı* **_TRUNCATE**olmadığı müddetçe) çok küçük. aşağıdaki açıklamalara bakın)|**ERANGE**|

Bu koşullardan herhangi biri gerçekleşirse, geçersiz parametre özel durumu [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev bir hata kodu döndürür ve tabloda belirtilen **errno** değerini ayarlar.

## <a name="remarks"></a>Açıklamalar

**Wcstombs_s** işlevi, *wcstr* tarafından işaret edilen geniş karakter dizesini *mbstr*tarafından işaret edilen arabellekte depolanan çok baytlı karakterlere dönüştürür. Bu koşullardan biri karşılanana kadar dönüştürme her karakter için devam eder:

- Null geniş bir karakterle karşılaşıldı

- Dönüştürülebilecek geniş bir karaktere rastlandı

- *Mbstr* arabelleği cinsinden depolanan bayt *sayısı.*

Hedef dize her zaman null ile sonlandırılır (bir hata durumunda bile).

*Count* değeri [_TRUNCATE](../../c-runtime-library/truncate.md)özel değer ise, **wcstombs_s** , dizenin büyük bir kısmını hedef arabelleğe sığdıracak şekilde dönüştürür. Dize kesilmişse, dönüş değeri **Strunde**olur ve dönüştürme başarılı olarak kabul edilir.

**Wcstombs_s** , kaynak dizeyi başarıyla dönüştürdüğünde, null Sonlandırıcı da dahil olmak üzere, dönüştürülmüş dizenin bayt cinsinden boyutunu *&#42;pReturnValue* 'A koyar (belirtilen *pReturnValue* **null**değil). Bu durum *mbstr* bağımsız değişkeni **null** olsa da, gerekli arabellek boyutunu belirlemekte bir yol sağlar. *Mbstr* **null**ise, *sayı* yoksayılıp sayılmadığını unutmayın.

**Wcstombs_s** çok baytlı bir karaktere dönüştüremediği geniş bir karakterle karşılaşırsa, 0 ' ı *&#42;pReturnValue*' a koyar, hedef arabelleği boş bir dizeye ayarlar, **errno** ' ı **Eilseq**olarak ayarlar ve **eilseq**' i döndürür.

*Wcstr* ve *mbstr* tarafından işaret edilen diziler çakıştığında, **wcstombs_s** davranışı tanımsızdır.

> [!IMPORTANT]
> *Wcstr* ve *mbstr* 'in çakışmadığından ve bu *sayının* dönüştürülecek geniş karakter sayısını doğru yansıttığından emin olun.

**wcstombs_s** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_wcstombs_s_l** , bunun yerine geçirilen yerel ayarı kullanması dışında **wcstombs** ile aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs_s**|\<Stdlib. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program **wcstombs_s** işlevinin davranışını gösterir.

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[Widechartoçok baytlı](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
