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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: c20066cddb3f28d31d2964ec720b64ed49836f65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328041"
---
# <a name="wcstombs_s-_wcstombs_s_l"></a>wcstombs_s, _wcstombs_s_l

Geniş karakter dizisini karşılık gelen çok bayt karakter dizisine dönüştürür. [WCT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleriyle [_wcstombs_l wcstombs'un](wcstombs-wcstombs-l.md) bir sürümü.

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
Null terminator dahil dönüştürülen dize baytboyutu.

*mbstr*<br/>
Dönüştürülen çok bayt karakter dizesi için bir arabellek adresi.

*sizeBytes*<br/>
*Mbstr* arabelleği baytboyutu.

*Wcstr*<br/>
Dönüştürülecek geniş karakter dizesini işaret edin.

*Sayısı*<br/>
Sonlandırıcı null karakteri veya [_TRUNCATE](../../c-runtime-library/truncate.md)dahil değil, *mbstr* arabelleğinde depolanması gereken maksimum bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, hata bir hata kodu.

|Hata koşulu|İade değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* **NULL** ve *sizeBytes* > 0|**Eınval**|
|*wcstr* **NULL** olduğunu|**Eınval**|
|Hedef arabellek dönüştürülen dizeyi içeremeyecek kadar küçüktür *(sayım* **_TRUNCATE**sürece ; aşağıdaki Açıklamalar'a bakın)|**Erange**|

Bu koşullardan herhangi biri oluşursa, geçersiz parametre özel durumu [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, işlev bir hata kodu döndürür ve tabloda belirtildiği gibi **errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**wcstombs_s** işlevi, *wcstr* tarafından işaret edilen geniş karakter dizisini *mbstr'nin*işaret ettiği arabellekte depolanan çok bayt karakterlere dönüştürür. Dönüştürme, bu koşullardan biri karşılanana kadar her karakter için devam edecektir:

- Null geniş bir karaktere rastlanır

- Dönüştürülemeyen geniş bir karakterle karşılaşılır

- *mbstr* arabelleğinde depolanan bayt sayısı *eşittir sayısı.*

Hedef dize her zaman null-sonlandırıldı (bir hata durumunda bile).

*Sayım* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md)ise, **wcstombs_s,** null terminator için yer bırakırken, hedef arabelleğe sığacak kadar dize dönüştürür. Dize kesilirse, iade değeri **STRUNCATE'dir**ve dönüştürme başarılı kabul edilir.

**wcstombs_s** kaynak dizesini başarıyla dönüştürürse, boyutu dönüştürülmüş dizedeki baytlara, null terminator da dahil olmak *üzere,&#42;pReturnValue'e* koyar (sağlanan *pReturnValue* **NULL**değildir). Bu, *mbstr* bağımsız değişkeni **NULL** olsa bile oluşur ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. *Mbstr* **NULL**ise, *sayım* yoksayılır unutmayın.

**wcstombs_s** çok bayt karaktere dönüştüremez geniş bir karakter karşılaşırsa, *&#42;pReturnValue*0 koyar, boş bir dize hedef arabellek ayarlar, **EILSEQ** **için errno** ayarlar , ve **EILSEQ**döndürür .

*Wcstr* ve *mbstr* çakışma ile işaret edilen diziler ise, **wcstombs_s** davranışı tanımsızdır.

> [!IMPORTANT]
> Wcstr ve *mbstr'nin* çakışmadığından ve bu *wcstr* *sayımda* dönüştürülecek geniş karakter sayısını doğru şekilde yansıttığından emin olun.

**wcstombs_s,** yerele bağımlı herhangi bir davranış için geçerli yerel durumu kullanır; **_wcstombs_s_l** **wcstombs** ile aynıdır, ancak bunun yerine geçirilen yerelliği kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu **program, wcstombs_s** işlevinin davranışını gösterir.

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
