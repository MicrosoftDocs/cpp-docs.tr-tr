---
title: c16rtomb, c32rtomb
ms.date: 10/22/2019
api_name:
- c16rtomb
- c32rtomb
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: 8f480d9b450b528275fea78ae878269fa6a4fa54
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811069"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

UTF-16 veya UTF-32 geniş karakterini UTF-8 çok baytlı karaktere dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>Parametreler

*mbchar*\
Dönüştürülmüş UTF-8 çok baytlı karakterini depolamak için bir diziye yönelik işaretçi.

*wchar*\
Dönüştürülecek geniş bir karakter.

*durum* \
**Mbstate_t** nesnesine yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş değeri

Tüm kaydırma dizileri dahil olmak üzere, *mbchar*dizi nesnesinde depolanan bayt sayısı. *Wchar* geçerli bir geniş karakter değilse, değer (**size_t**) (-1) döndürülür, **errno** değeri **eilseq**olarak ayarlanır ve *durum* değeri belirtilmemiş olur.

## <a name="remarks"></a>Açıklamalar

**C16rtomb** IşLEVI, UTF-16 Le karakter *wchar* karakterini eşit UTF-8 çok baytlı dar karakter dizisine dönüştürür. *Mbchar* null bir işaretçi değilse, işlev, çevrilmiş sırayı *mbchar*tarafından işaret edilen dizi nesnesinde depolar. **MB_CUR_MAX** bayt sayısı *mbchar*'da depolanır ve *durum* , ortaya çıkan çok baytlı kaydırma durumuna ayarlanır.

*Wchar* null geniş bir karakter ise, ilk kaydırma durumunu geri yüklemek için gereken bir sıra, gerekirse, sonra null karakter tarafından depolanır. *durum* , ilk dönüştürme durumuna ayarlanır. **C32rtomb** işlevi aynıdır, ancak bir UTF-32 karakterini dönüştürür.

*Mbchar* null bir işaretçiyse, bu davranış, *mbchar* için bir iç arabellek ve *wchar*için geniş bir null karakter içeren işleve yapılan çağrıya eşdeğerdir.

*Durum* dönüştürme durumu nesnesi, bu işlev için sonraki çağrıları ve çok baytlı çıkış karakterlerinin kaydırma durumunu koruyacak diğer yeniden başlatılabilir işlevleri ayarlamanıza olanak sağlar. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımını karıştıradığınızda sonuçlar tanımsızdır.

UTF-16 karakterlerini UTF-8 çok baytlı karakterlere dönüştürmek için [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md), [wcstombs_s veya _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) işlevlerini kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++:\<uşar. h >|

Uyumluluk bilgileri için bkz. [Uyumluluk](../compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Yerel ayar](../locale.md)\
[Çok baytlı karakter sıralarının yorumu](../interpretation-of-multibyte-character-sequences.md)\
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)\
[wcrtomb](wcrtomb.md)\
[wcrtomb_s](wcrtomb-s.md)
