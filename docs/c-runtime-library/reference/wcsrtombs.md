---
title: wcsrtombs
ms.date: 4/2/2020
api_name:
- wcsrtombs
- _o_wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: af22a7d55c5f4958db6962e98f212fb5bb89e61e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328052"
---
# <a name="wcsrtombs"></a>wcsrtombs

Geniş bir karakter dizesini çok bayt karakter dize gösterimine dönüştürün. Bu işlevin daha güvenli bir sürümü mevcuttur; [wcsrtombs_s](wcsrtombs-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*mbstr*<br/>
Ortaya çıkan çok bayt karakter dizesinin adres konumu dönüştürülür.

*Wcstr*<br/>
Dolaylı olarak dönüştürülecek geniş karakter dizesinin konumunu işaret.

*Sayısı*<br/>
Dönüştürülecek karakter sayısı.

*mbstate*<br/>
**mbstate_t** dönüştürme durumu nesnesine işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Null sonlandırıcı null bayt (varsa) dahil değil, başarıyla dönüştürülen bayt sayısını, aksi takdirde bir hata oluştuysa -1 verir.

## <a name="remarks"></a>Açıklamalar

**Wcsrtombs** işlevi *mbstate'te*yer alan belirtilen dönüşüm durumundan başlayarak, *wcstr'de*işaret edilen dolaylı değerlerden *mbstr*adresine kadar geniş bir karakter dizisini dönüştürür. Dönüştürme kadar her karakter için devam edecektir: null sonlandırıcı geniş karakter karşılaştıktan sonra, karşılık gelen bir karakter karşılaşıldığında veya bir sonraki karakter *sayısı*içerdiği sınırı aşacak. **Wcsrtombs,** sayım gerçekleşmeden önce veya *sayıldığında* geniş karakterli null karakteriyle (L'\0') karşılaşırsa, 8-bit 0'a dönüştürür ve durur.

Böylece, *mbstr'deki* çok bayt karakter dizesi, ancak **wcsrtombs'un** dönüştürme sırasında geniş bir karakter null karakteriyle karşılaşması durumunda geçersiz kılınır. *Wcstr* ve *mbstr* çakışma ile işaret edilen diziler ise, **wcsrtombs** davranışı tanımsız. **wcsrtombs** geçerli yerel LC_TYPE kategorisinden etkilenir.

**Wcsrtombs** işlevi [wcstombs farklıdır, _wcstombs_l](wcstombs-wcstombs-l.md) yeniden başlatılabilirlik. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır.  Örneğin, bir uygulama **wcsnlen** yerine **wcsrlen**kullanır , **wcsrtombs** yerine sonraki **wcstombs**bir çağrı kullanıldı.

*Mbstr* bağımsız değişkeni **NULL**ise, **wcsrtombs** hedef dize baytlar gerekli boyutu döndürür. *Mbstate* null ise, iç **mbstate_t** dönüştürme durumu kullanılır. Karakter dizisi *wchar* karşılık gelen bir çok bayt karakter gösterimi yoksa, bir -1 döndürülür ve **errno** **EILSEQ**olarak ayarlanır.

C++'da bu işlev, bu işlevin daha yeni ve güvenli karşılığını çağıran bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="exceptions"></a>Özel durumlar

**Wcsrtombs** işlevi, bu işlev yürütülerken ve *mbstate* null değilken, geçerli iş parçacığı nda **setlocale** çağıran hiçbir işlev sürece çok iş parçacığı güvenlidir.

## <a name="example"></a>Örnek

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

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
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
