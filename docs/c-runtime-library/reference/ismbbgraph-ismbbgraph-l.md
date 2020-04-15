---
title: _ismbbgraph, _ismbbgraph_l
ms.date: 4/2/2020
api_name:
- _ismbbgraph_l
- _ismbbgraph
- _o__ismbbgraph
- _o__ismbbgraph_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbbgraph
- _ismbbgraph_l
- ismbbgraph
- ismbbgraph_l
helpviewer_keywords:
- _ismbbgraph_l function
- ismbbgraph_l function
- _ismbbgraph function
- ismbbgraph function
ms.assetid: b60db718-134f-4796-acc1-592d0b9efbb7
ms.openlocfilehash: 28e52c564bb554df1bd2228691034db5a13a2300
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343718"
---
# <a name="_ismbbgraph-_ismbbgraph_l"></a>_ismbbgraph, _ismbbgraph_l

Belirli bir çok bayt karakterin grafik bir karakter olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbgraph (
   unsigned int c
);
int _ismbbgraph_l (
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
İnteger test edilecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

İfade varsa sıfır olmayan bir değer verir:

`isctype(c, ( _PUNCT | _UPPER | _LOWER | _DIGIT )) || _ismbbkprint(c)`

*c*için sıfır değildir, yoksa 0'dır. **_ismbbgraph,** yerel e-eşe bağlı herhangi bir davranış için geçerli yerel alanı kullanır. **_ismbbgraph_l,** bunun yerine geçirilen yerel liği kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbgraph**|\<mbctype.h>|
|**_ismbbgraph_l**|\<mbctype.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
