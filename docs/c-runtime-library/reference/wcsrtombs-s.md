---
title: wcsrtombs_s
ms.date: 11/04/2016
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
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: bd965271a65fa91b427c7af7bbd4173b129e1d8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188577"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

Geniş karakter dizesi çok baytlı karakter dize gösterimine dönüştürür. Bir sürümünü [wcsrtombs](wcsrtombs.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Dönüştürülmüş dize null Sonlandırıcı dahil olmak üzere, bayt cinsinden boyutu.

*mbstr*<br/>
Arabellek için ortaya çıkan dönüştürülmüş çok baytlı karakter dizesi adresi.

*sizeInBytes*<br/>
Bayt cinsinden boyutu *mbstr* arabellek.

*wcstr*<br/>
Dönüştürülecek geniş karakter dizesine işaret eder.

*Sayısı*<br/>
İçinde depolanan bayt sayısı *mbstr* arabellek veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, bir hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* olduğu **NULL** ve *sizeInBytes* > 0|**EINVAL**|
|*wcstr* olduğu **NULL**|**EINVAL**|
|Hedef arabelleğinin içeren dönüştürülmüş dize çok küçük (sürece *sayısı* olduğu **_TRUNCATE**; aşağıdaki açıklamalara bakın)|**ERANGE**|

Bu koşullardan herhangi biri meydana gelirse, açıklanan şekilde geçersiz parametre özel durumu çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse işlev bir hata kodu döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Wcsrtombs_s** işlevi dönüştürür bir işaret ettiği geniş karakter dizesi *wcstr* çok baytlı karakter tarafından işaret edilen arabellek depolanan içine *mbstr*kullanarak Dönüştürme durumunu bulunan *mbstate*. Dönüştürme, her karakter için şu koşullardan biri karşılandığında kadar devam eder:

- Bir null geniş karakter karşılaşıldı

- Dönüştürülemeyen bir geniş karakter karşılaşıldı

- İçinde depolanan bayt sayısını *mbstr* arabellek eşittir *sayısı*.

Hedef dize her zaman null ile sonlandırılmış (bile bir hata olması durumunda).

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından **wcsrtombs_s** büyük bir işlem olarak dize dönüştürür yine de bir null yer bırakarak hedef arabellek içine Sığdır Sonlandırıcı.

Varsa **wcsrtombs_s** başarılı bir şekilde kaynak dizesini dönüştürür dönüştürülmüş dize halinde null sonlandırıcıyı da dahil olmak üzere, bayt cinsinden boyutu koyar  *&#42;pReturnValue* (sağlanan  *pReturnValue* değil **NULL**). Bu meydana bile *mbstr* bağımsız değişkeni **NULL** ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın *mbstr* olduğu **NULL**, *sayısı* göz ardı edilir.

Varsa **wcsrtombs_s** bir çok baytlı karakterin dönüştüremiyor uluslararası bir karakterle karşılaştığında -1 koyar  *\*pReturnValue*, için boş bir dize hedef arabelleğinin ayarlar, Ayarlar**errno** için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri işaret ettiği varsa *wcstr* ve *mbstr* üst üste, davranışını **wcsrtombs_s** tanımsızdır. **wcsrtombs_s** geçerli yerel ayarı LC_TYPE kategoriye göre etkilenir.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* örtüşmeyen ve *sayısı* doğru şekilde dönüştürmek için geniş karakter sayısını yansıtır.

**Wcsrtombs_s** işlevi farklıdır [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) kendi restartability tarafından. Dönüştürme durumunu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır. Örneğin, bir uygulama kullanırsınız **wcsrlen** yerine **wcslen**sonraki çağrı, **wcsrtombs_s** yerine kullanılan **wcstombs_s**.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Wcsrtombs_s** işlevi, geçerli iş parçacığındaki hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlev yürütülürken ve *mbstate* null.

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
