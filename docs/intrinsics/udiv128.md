---
description: 'Hakkında daha fazla bilgi edinin: _udiv128'
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: f88546a179106f4291fcaeb865f1aad9e67c4045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333649"
---
# <a name="_udiv128"></a>_udiv128

`_udiv128`İç, 128 bitlik işaretsiz bir tamsayıyı 64 bit işaretsiz bir tamsayı ile böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_udiv128` , **Microsoft 'a özgüdür**.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>Parametreler

*Highbölünen* \
'ndaki Bölünen yüksek 64 bitleri.

*Lowbölünen* \
'ndaki Bölünün düşük 64 bitleri.

*Lene* \
'ndaki Bölünecek 64 bitlik tamsayı.

*geri kalanında* \
dışı Kalanın 64 bitlik tamsayı bitleri.

## <a name="return-value"></a>Döndürülen değer

Bölüm 64 bitleri.

## <a name="remarks"></a>Açıklamalar

128 bit bölünme sayısının üst 64 bitini ve *düşük olan 64 ' ı* *lowbölünen* olarak geçirin. İç değer bu değeri *bölene* böler. *Kalanı, kalanı tarafından işaret* edilen 64 bitlik işaretsiz tamsayıya depolar ve bölümün 64 bitlerini döndürür.

`_udiv128`İç, Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_udiv128`|x64|\<immintrin.h>|

## <a name="see-also"></a>Ayrıca bkz.

[_div128](div128.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
