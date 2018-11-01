---
title: c16rtomb, c32rtomb1
ms.date: 11/04/2016
apiname:
- c16rtomb
- c32rtomb
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
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: 0d735363bbb317b06c1ebc73a2b0678479a243ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536597"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Çok baytlı bir karakter geçerli yerel ayarı, UTF-16 veya UTF-32 bir geniş karakter dönüştürün.

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

*mbchar*<br/>
Çok baytlı dönüştürülmüş karakteri depolamak için bir dizi için işaretçi.

*wchar*<br/>
Dönüştürülecek bir geniş karakter.

*durumu*<br/>
Bir işaretçi bir **mbstate_t** nesne.

## <a name="return-value"></a>Dönüş Değeri

Dizi nesnesinde depolanan bayt sayısını *mbchar*, herhangi bir üst karakter sıraları dahil olmak üzere. Varsa *wchar* geçerli bir geniş karakter, değer değil (**size_t**)(-1) döndürülür **errno** ayarlanır **EILSEQ**, değeri*durumu* belirtilmemiş.

## <a name="remarks"></a>Açıklamalar

**C16rtomb** işlevi dönüştürür UTF-16 karakter *wchar* için geçerli yerel ayarı eşdeğer çok baytlı dar karakter dizisi. Varsa *mbchar* bir null işaretçiyse, dönüştürülen dizide dizi nesnesi tarafından işaret edilen işlevi depoları değil *mbchar*. En fazla **MB_CUR_MAX** bayt depolanır *mbchar*, ve *durumu* sonuç çok baytlı shift durumuna ayarlanır.    Varsa *wchar* null geniş bir karakter olan bir dizisi için gerekli olan ilk kaydırma durumu depolanır, gerekirse geri yükleme null karakter, ardından ve *durumu* dönüştürme ilk duruma ayarlanır. **C32rtomb** işlevi aynıdır, ancak bir UTF-32 karakter dönüştürür.

Varsa *mbchar* bir null işaretçiyse davranıştır bir iç arabellek için değiştirir işlevi çağrısı eşdeğer *mbchar* ve geniş null karakter *wchar*.

*Durumu* dönüştürme durumu nesne bu işleve ve çıkış çok baytlı karakter kaydırma durumunu korumak yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar yapmanızı sağlar. Yeniden başlatılabilir ve yeniden başlatılabilir olmayan işlevlerin kullanımını karışık olduğunda veya bir çağrı, sonuçlar tanımsız **setlocale** yeniden başlatılabilir işlev çağrıları arasında yapılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h >|

Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
