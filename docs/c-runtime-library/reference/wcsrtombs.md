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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: cad31f28c5542a96eae9f144344882b71806052a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910626"
---
# <a name="wcsrtombs"></a>wcsrtombs

Geniş karakter dizesini çok baytlı karakter dizesi gösterimine Dönüştür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [wcsrtombs_s](wcsrtombs-s.md).

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
Elde edilen dönüştürülmüş çok baytlı karakter dizesinin adres konumu.

*wcstr*<br/>
Dolaylı olarak dönüştürülecek geniş karakter dizesinin konumunu gösterir.

*biriktirme*<br/>
Dönüştürülecek karakter sayısı.

*mbstate*<br/>
**Mbstate_t** dönüştürme durumu nesnesine yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla dönüştürülen bayt sayısını döndürür, null Sonlandırıcı null baytı (varsa) dahil edilmez, aksi takdirde bir hata oluştuysa-1.

## <a name="remarks"></a>Açıklamalar

**Wcsrişaretlenen s** işlevi, *mbstate*içinde bulunan belirtilen dönüştürme durumundan başlayarak, bir geniş karakter dizesini, *wcstr*içinde dolaylı olarak işaret edilen değerleri *mbstr*adresine dönüştürür. Karşılık gelen bir karakter ile karşılaşıldığında veya bir sonraki karakter, *say*'da bulunan sınırı aştığında, her karakter için dönüştürme işlemi devam edecek. **Wcsrkaldırıldı s** geniş karakterli null karakterle (L ' \ 0 ') karşılaşırsa veya *sayı* gerçekleştiğinde, bunu 8 bit 0 değerine dönüştürür ve duraklar.

Bu nedenle, *mbstr* konumundaki çok baytlı karakter dizesi, dönüştürme sırasında yalnızca **wcsrkaldırıldı s** bir geniş karakter null karakteriyle karşılaştığında null sonlandırılmış olur. *Wcstr* ve *mbstr* tarafından işaret edilen diziler çakıştığında, **wcsrkaldırıldı s** davranışı tanımsızdır. **wcsrkaldırıldı s** , geçerli yerel ayarın LC_TYPE kategorisinden etkilendi.

**Wcsr^ s** işlevi [, wcstombs öğesinden farklı, _wcstombs_l](wcstombs-wcstombs-l.md) yeniden başlangıçlarından farklıdır. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır.  Örneğin, bir uygulama **wcsnlen**yerine **wcsrlen** s çağrısı, **wcstomb**yerine daha sonra bir **wcsrkaldırıldı** for çağrısı kullanıldıysa,.

*Mbstr* bağımsız değişkeni **null**ise, **wcsrkaldırıldı s** , hedef dizenin bayt cinsinden gereken boyutunu döndürür. *Mbstate* null ise, iç **mbstate_t** dönüştürme durumu kullanılır. *Wchar* karakter dizisinin karşılık gelen bir çok baytlı karakter temsili yoksa,-1 döndürülür ve **errno** , **eilseq**olarak ayarlanır.

C++ ' da bu işlevin, bu işlevin daha yeni ve güvenli karşılığı sağlayan bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="exceptions"></a>Özel durumlar

Geçerli iş parçacığındaki hiçbir işlev, bu işlev yürütülürken ve *mbstate* null **olmadığı sürece,** **wcsrkaldırıldı s** işlevi çoklu iş parçacığı güvenlidir.

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
|**wcsrtombs**|\<wchar. h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
