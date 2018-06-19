---
title: wcsrtombs_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94e27965d1660f4c344d0026bbfce8685a935c7a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417307"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

Geniş karakter dizesi, birden çok baytlı karakter dizesi gösterimine dönüştürür. Bir sürümünü [wcsrtombs](wcsrtombs.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*pReturnValue*<br/>
Dönüştürülen karakter sayısı.

*mbstr*<br/>
Ortaya çıkan dönüştürülmüş birden çok baytlı karakter dizesi için bir arabellek adresi.

*sizeInBytes*<br/>
Bayt cinsinden boyutu *mbstr* arabellek.

*wcstr*<br/>
Dönüştürülecek geniş karakter dizesi noktalarına.

*Sayısı*<br/>
Depolanmasına bayt sayısını *mbstr* arabellek veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı olursa, hatasında bir hata kodu.

|Hata durumu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* olan **NULL** ve *sizeInBytes* > 0|**EINVAL**|
|*wcstr* olan **NULL**|**EINVAL**|
|Hedef arabellek dönüştürülmüş dizeyi içeren için çok küçük. (sürece *sayısı* olan **_TRUNCATE**; açıklamalar aşağıya bakın)|**ERANGE**|

Bu koşulların herhangi biri meydana gelirse, geçersiz bir parametre özel durum açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu işlevi döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Wcsrtombs_s** işlevi dönüştürür gösterdiği geniş karakter dizesi *wcstr* gösterdiği arabellek depolanan birden çok baytlı karakterler içine *mbstr*kullanarak içinde yer alan dönüştürme durumu *mbstate*. Bu koşullardan biri yerine getirilene kadar dönüştürme için her karakter devam eder:

- Null geniş karakter karşılaştı

- Dönüştürülemiyor geniş bir karakter ile karşılaşıldı

- Depolanan bayt sayısı *mbstr* arabellek eşittir *sayısı*.

Hedef dize her zaman null (bile bir hata olması durumunda) sonlandırılır.

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından **wcsrtombs_s** dize olarak büyük dönüştürür hala null yer bırakarak hedef arabelleğine sığacak Sonlandırıcı.

Varsa **wcsrtombs_s** başarıyla kaynak dizesi dönüştürür dönüştürülen dizenin null Sonlandırıcı içine dahil bayt cinsinden boyutu koyar  *&#42;pReturnValue* (sağlanan  *pReturnValue* değil **NULL**). Bu meydana olsa bile *mbstr* bağımsız değişkeni **NULL** ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın *mbstr* olan **NULL**, *sayısı* göz ardı edilir.

Varsa **wcsrtombs_s** birden çok baytlı karakter dönüştüremiyor geniş karakter karşılaştığında -1 koyar  *\*pReturnValue*, hedef arabelleği boş bir dize olarak ayarlar, Ayarlar**errno** için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri gösterdiği varsa *wcstr* ve *mbstr* üst üste, davranışını **wcsrtombs_s** tanımlanmadı. **wcsrtombs_s** geçerli yerel LC_TYPE kategoriye göre etkilenir.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* çakışmaması ve *sayısı* doğru şekilde dönüştürmek için geniş karakter sayısını yansıtır.

**Wcsrtombs_s** işlevi farklı olarak [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan *mbstate* sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanırsınız **wcsrlen** yerine **wcslen**, bir sonraki çağrı, **wcsrtombs_s** yerine kullanılan **wcstombs_s**.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Wcsrtombs_s** işlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlev yürütülürken ve *mbstate* null.

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

void main()
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
|**wcsrtombs_s**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
