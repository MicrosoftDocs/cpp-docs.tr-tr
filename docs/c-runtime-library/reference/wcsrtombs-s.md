---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 71a2206df9d3afb64fcaf62848988cf116d9071f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328115"
---
# <a name="wcsrtombs_s"></a>wcsrtombs_s

Geniş bir karakter dizesini çok bayt karakter dize gösterimine dönüştürün. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [wcsrtombs](wcsrtombs.md) bir sürümü.

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
Null terminator dahil dönüştürülen dize baytboyutu.

*mbstr*<br/>
Dönüştürülen çok bayt karakter dizesi için bir arabellek adresi.

*sizeBytes*<br/>
*Mbstr* arabelleği baytboyutu.

*Wcstr*<br/>
Dönüştürülecek geniş karakter dizesini işaret edin.

*Sayısı*<br/>
*Mbstr* arabelleğinde depolanacak maksimum bayt sayısı veya [_TRUNCATE.](../../c-runtime-library/truncate.md)

*mbstate*<br/>
**mbstate_t** dönüştürme durumu nesnesine işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, hata bir hata kodu.

|Hata koşulu|İade değeri ve **errno**|
|---------------------|------------------------------|
|*mbstr* **NULL** ve *sizeBytes* > 0|**Eınval**|
|*wcstr* **NULL** olduğunu|**Eınval**|
|Hedef arabellek dönüştürülen dizeyi içeremeyecek kadar küçüktür *(sayım* **_TRUNCATE**sürece ; aşağıdaki Açıklamalar'a bakın)|**Erange**|

Bu koşullardan herhangi biri oluşursa, geçersiz parametre özel durumu [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, işlev bir hata kodu döndürür ve tabloda belirtildiği gibi **errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**wcsrtombs_s** işlevi mbstate bulunan dönüştürme durumunu kullanarak *mbstr*tarafından işaret edilen arabellekte depolanan çok bayt karakterlere *wcstr* tarafından işaret geniş karakter bir dizi *dönüştürür.* Dönüştürme, bu koşullardan biri karşılanana kadar her karakter için devam edecektir:

- Null geniş bir karaktere rastlanır

- Dönüştürülemeyen geniş bir karakterle karşılaşılır

- *mbstr* arabelleğinde depolanan bayt sayısı *eşittir sayısı.*

Hedef dize her zaman null-sonlandırıldı (bir hata durumunda bile).

*Sayım* [_TRUNCATE](../../c-runtime-library/truncate.md)özel bir değerse, **wcsrtombs_s,** null terminator için yer bırakırken, hedef arabelleğe sığacak kadar dize dönüştürür.

**wcsrtombs_s** kaynak dizesini başarıyla dönüştürürse, boyutu dönüştürülmüş dizebaylara, null terminator da dahil olmak *üzere,&#42;pReturnValue'e* koyar (sağlanan *pReturnValue* **NULL**değildir). Bu, *mbstr* bağımsız değişkeni **NULL** olsa bile oluşur ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. *Mbstr* **NULL**ise, *sayım* yoksayılır unutmayın.

**wcsrtombs_s** çok bayt karaktere dönüştüremez geniş bir karakter karşılaşırsa, bu * \*pReturnValue*-1 koyar, boş bir dize hedef arabellek ayarlar, **EILSEQ** **için errno** ayarlar , ve **EILSEQ**döndürür .

*Wcstr* ve *mbstr* çakışma ile işaret edilen diziler ise, **wcsrtombs_s** davranışı tanımsızdır. **wcsrtombs_s** geçerli yerel LC_TYPE kategorisinden etkilenir.

> [!IMPORTANT]
> Wcstr ve *mbstr'nin* çakışmadığından ve bu *wcstr* *sayımda* dönüştürülecek geniş karakter sayısını doğru şekilde yansıttığından emin olun.

**wcsrtombs_s** işlevi wcstombs_s farklıdır [_wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) yeniden başlatılabilirliği ile. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır. Örneğin, bir uygulama **wcsrlen** yerine **wcsrlen**kullanır , **wcsrtombs_s** için sonraki bir çağrı **wcstombs_s**yerine kullanıldı.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="exceptions"></a>Özel durumlar

Wcsrtombs_s **wcsrtombs_s** işlevi, bu işlev yürütülerken ve *mbstate* null iken geçerli iş parçacığı **çağıran ayaryerel** sürece multithread güvenlidir.

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

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
