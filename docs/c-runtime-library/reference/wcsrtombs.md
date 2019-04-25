---
title: wcsrtombs
ms.date: 11/04/2016
apiname:
- wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: 46ef195ec4685c327c4b5951ec44e5c363214b59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155335"
---
# <a name="wcsrtombs"></a>wcsrtombs

Geniş karakter dizesi çok baytlı karakter dize gösterimine dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [wcsrtombs_s](wcsrtombs-s.md).

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
Sonuç, çok baytlı karakter dizesi'nın adresi konumu dönüştürülür.

*wcstr*<br/>
Dolaylı olarak noktaları konumuna dönüştürülecek geniş karakter dizesi.

*Sayısı*<br/>
Dönüştürülecek karakter sayısı.

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Bayt sayısı başarılı bir şekilde, bir hata oluştuysa null bayt (varsa), yoksa -1 Sonlandırıcı null içermeden dönüştürülen döndürür.

## <a name="remarks"></a>Açıklamalar

**Wcsrtombs** işlevi dönüştürür bir içindeki belirtilen dönüşüm durumu başlayarak, geniş karakter dizesi *mbstate*, değerlerinin dolaylı olarak işaret *wcstr*, adresi içine *mbstr*. Dönüştürme için her bir karakteri kadar devam eder: ilgili olmayan bir karakter ile karşılaşıldığında geniş karakteri sonlandırarak null karşılaştı sonra veya bir sonraki karakteri içerdiği sınırını aşacak *sayısı*. Varsa **wcsrtombs** geniş karakterli null karakteri (L '\0') önce veya ne zaman karşılaştığında *sayısı* gerçekleşir dönüştürür, 8 bitlik 0 ve durur.

Bu nedenle, çok baytlı karakter dizesi *mbstr* yalnızca aşağıdaki durumlarda sonlandırılmış **wcsrtombs** dönüştürme sırasında bir geniş karakter null karakterle karşılaştığında. Dizileri işaret ettiği varsa *wcstr* ve *mbstr* üst üste, davranışını **wcsrtombs** tanımsızdır. **wcsrtombs** geçerli yerel ayarı LC_TYPE kategoriye göre etkilenir.

**Wcsrtombs** işlevi farklıdır [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) kendi restartability tarafından. Dönüştürme durumunu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır.  Örneğin, bir uygulama kullanırsınız **wcsrlen** yerine **wcsnlen**sonraki çağrı, **wcsrtombs** yerine kullanılan **wcstombs**.

Varsa *mbstr* bağımsız değişkeni **NULL**, **wcsrtombs** gerekli boyutu hedef dize baytı cinsinden döndürür. Varsa *mbstate* null, iç **mbstate_t** dönüştürme durumu kullanılır. Varsa karakter dizisi *wchar* karşılık gelen bir çok baytlı yok karakter gösterimi, -1 döndürülür ve **errno** ayarlanır **EILSEQ**.

C++'da, bu işlev bu işlevin daha yeni ve güvenli karşılığı çağıran bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Wcsrtombs** işlevi, geçerli iş parçacığındaki hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlev yürütülürken ve *mbstate* null değil.

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
|**wcsrtombs**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
