---
description: 'Hakkında daha fazla bilgi edinin: _udiv64'
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 21f383cd78885ab8d3d8bb66a87623a73b59ff95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333637"
---
# <a name="_udiv64"></a>_udiv64

`_udiv64`İç, 64 bitlik işaretsiz bir tamsayıyı 32 bit işaretsiz bir tamsayı ile böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_udiv64` , **Microsoft 'a özgüdür**.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Parametreler

*eni*\
'ndaki Bölünecek 64 bitlik işaretsiz tamsayı.

*Lene*\
'ndaki Bölünecek 32 bitlik işaretsiz tamsayı.

*geri kalanında*\
dışı 32 bitlik işaretsiz tamsayı kalanı.

## <a name="return-value"></a>Döndürülen değer

Bölüm 32 bitleri.

## <a name="remarks"></a>Açıklamalar

`_udiv64`İç bölünen *Bölüneni* *bölendir*. *Kalanı, kalanı tarafından işaret* edilen 32 bitlik işaretsiz tamsayıya depolar ve bölümün 32 bitlerini döndürür.

`_udiv64`İç, Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Ayrıca bkz.

[_div64](div64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
