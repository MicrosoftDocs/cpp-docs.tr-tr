---
title: c16rtomb, c32rtomb1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3282fb13e5b59ad3214c67410eef5186687114e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394552"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Geçerli yerel birden çok baytlı karakter UTF-16 veya UTF-32 geniş karakter dönüştürün.

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
İşaretçi dönüştürülen birden çok baytlı karakter depolamak için bir dizi.

*wchar*<br/>
Dönüştürülecek geniş karakter.

*Durumu*<br/>
Bir işaretçi bir **mbstate_t** nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Dizi nesnesi içinde depolanan bayt sayısı *mbchar*, tüm üst karakter sıraları dahil olmak üzere. Varsa *wchar* geçerli bir uluslararası karakter, değeri değil (**size_t**)(-1) döndürülür, **errno** ayarlanır **EILSEQ**, değeri*durumu* belirtilmedi.

## <a name="remarks"></a>Açıklamalar

**C16rtomb** işlevi dönüştürür UTF-16 karakter *wchar* için geçerli yerel eşdeğer birden çok baytlı dar karakter dizisi. Varsa *mbchar* tarafından için dizi nesnesi dönüştürülen sırayla işaret işlevi depoları null işaretçi değil *mbchar*. En fazla **MB_CUR_MAX** bayt depolanır *mbchar*, ve *durumu* elde edilen birden çok baytlı shift durumuna ayarlanır.    Varsa *wchar* null geniş bir karakter olan bir sırası için gerekli olan ilk kaydırma durumu depolanır, gerekirse, geri yükleme ve ardından null karakteriyle ve *durumu* ilk dönüştürme durumuna ayarlanır. **C32rtomb** işlevi aynıdır, ancak UTF-32 karakter dönüştürür.

Varsa *mbchar* null işaretçi davranışı, bir iç arabellek için değiştirir işlevi çağrısı eşdeğerdir *mbchar* ve geniş bir null karakter için *wchar*.

*Durumu* dönüştürme durumu nesne bu işlev ve çok baytlı çıkış karakterleri shift durumunu korumak yeniden başlatılabilir diğer işlevleri yapılan sonraki çağrılar yapmanızı sağlar. Yeniden başlatılabilir ve yeniden başlatılabilir olmayan işlevleri kullanımını karışık veya çağrı olsa sonuçları tanımsız **setlocale** yeniden başlatılabilir işlev çağrıları arasında yapılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h >|

Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
