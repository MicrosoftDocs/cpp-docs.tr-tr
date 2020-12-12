---
description: 'Hakkında daha fazla bilgi edinin: _ismbbgraph _ismbbgraph_l'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 093d7d2ca9b9bde427078f390f2036866529d8da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306358"
---
# <a name="_ismbbgraph-_ismbbgraph_l"></a>_ismbbgraph, _ismbbgraph_l

Belirli bir çok baytlı karakterin bir grafik karakter olup olmadığını belirler.

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

*,*<br/>
Sınanacak tamsayı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

İfade yoksa sıfır dışında bir değer döndürür:

`isctype(c, ( _PUNCT | _UPPER | _LOWER | _DIGIT )) || _ismbbkprint(c)`

*c* için sıfır veya değilse 0 olur. **_ismbbgraph** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbbgraph_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbgraph**|\<mbctype.h>|
|**_ismbbgraph_l**|\<mbctype.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb yordamlar](../../c-runtime-library/ismbb-routines.md)<br/>
