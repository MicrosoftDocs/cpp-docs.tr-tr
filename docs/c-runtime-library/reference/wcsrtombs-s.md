---
description: 'Hakkında daha fazla bilgi edinin: wcsrtombs_s'
title: wcsrtombs_s
ms.date: 4/2/2020
api_name:
- wcsrtombs_s
- _o_wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: 4a25be8bf1c61fec10c54a4ecdb870a383b31e9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340534"
---
# <a name="wcsrtombs_s"></a>wcsrtombs_s

Geniş karakter dizesini çok baytlı karakter dizesi gösterimine Dönüştür. [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içeren bir [wcsrkaldırıldı s](wcsrtombs.md) sürümü.

## <a name="syntax"></a>Sözdizimi

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
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
*Mbstr* arabelleğinde depolanacak en fazla bayt sayısı veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
**Mbstate_t** dönüştürme durumu nesnesine yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, hata durumunda hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* **null** ve *sizeInBytes* > 0|**EıNVAL**|
|*wcstr* **null**|**EıNVAL**|
|Hedef arabellek dönüştürülmüş dizeyi ( *sayı* **_TRUNCATE** olmadığı müddetçe) çok küçük. aşağıdaki açıklamalara bakın)|**ERANGE**|

Bu koşullardan herhangi biri gerçekleşirse, geçersiz parametre özel durumu [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev bir hata kodu döndürür ve tabloda belirtilen **errno** değerini ayarlar.

## <a name="remarks"></a>Açıklamalar

**Wcsrtombs_s** işlevi, *wcstr* tarafından işaret edilen bir geniş karakter dizesini, *mbstr* tarafından işaret edilen arabellekte depolanan çok baytlı karakterlere, *mbstate* içinde yer alan dönüştürme durumu kullanılarak dönüştürülür. Bu koşullardan biri karşılanana kadar dönüştürme her karakter için devam eder:

- Null geniş bir karakterle karşılaşıldı

- Dönüştürülebilecek geniş bir karaktere rastlandı

- *Mbstr* arabelleği cinsinden depolanan bayt *sayısı.*

Hedef dize her zaman null ile sonlandırılır (bir hata durumunda bile).

*Count* değeri [_TRUNCATE](../../c-runtime-library/truncate.md)özel değer ise, **wcsrtombs_s** , dizenin büyük bir kısmını hedef arabelleğe sığdıracak şekilde dönüştürür.

**Wcsrtombs_s** , kaynak dizeyi başarıyla dönüştürdüğünde, null Sonlandırıcı da dahil olmak üzere, dönüştürülmüş dizenin bayt cinsinden boyutunu *&#42;pReturnValue* 'A koyar (belirtilen *pReturnValue* **null** değil). Bu durum *mbstr* bağımsız değişkeni **null** olsa da, gerekli arabellek boyutunu belirlemekte bir yol sağlar. *Mbstr* **null** ise, *sayı* yoksayılıp sayılmadığını unutmayın.

**Wcsrtombs_s** çok baytlı bir karaktere dönüştüremediği geniş bir karakterle karşılaşırsa,-1 ' i *\* önceden yapılan değere* koyar, hedef arabelleği boş bir dizeye ayarlar, **errno** 'U **eilseq** olarak ayarlar ve **eilseq** döndürür.

*Wcstr* ve *mbstr* tarafından işaret edilen diziler çakıştığında, **wcsrtombs_s** davranışı tanımsızdır. **wcsrtombs_s** , geçerli yerel ayarın LC_TYPE kategorisinden etkilenir.

> [!IMPORTANT]
> *Wcstr* ve *mbstr* 'in çakışmadığından ve bu *sayının* dönüştürülecek geniş karakter sayısını doğru yansıttığından emin olun.

**Wcsrtombs_s** işlevi [wcstombs_s,](wcstombs-s-wcstombs-s-l.md) yeniden başlangıçlarından _wcstombs_s_l farklıdır. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır. Örneğin, bir uygulama, **wcstombs_s** yerine **wcsrtombs_s** sonraki bir çağrı kullanıldıysa **wcslen** yerine **wcsrlen** kullanır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="exceptions"></a>Özel durumlar

Geçerli iş parçacığında hiçbir işlev bu işlev yürütülürken ve *mbstate* null olduğunda, **wcsrtombs_s** işlevi  iş parçacığı güvenlidir.

## <a name="example"></a>Örnek

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
