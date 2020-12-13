---
description: 'Hakkında daha fazla bilgi edinin: _div64'
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 4c9c8f02f7092c12d5734f96346897e2eca9898a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337072"
---
# <a name="_div64"></a>_div64

`_div64`İç, 64 bitlik bir tamsayıyı 32 bitlik bir tamsayıya böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_div64` , **Microsoft 'a özgüdür**.

## <a name="syntax"></a>Sözdizimi

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Parametreler

*eni* \
'ndaki Bölünecek 64 bitlik tamsayı.

*Lene* \
'ndaki Bölünecek 32 bitlik tamsayı.

*geri kalanında* \
dışı Kalanın 32 bitlik tamsayı bitleri.

## <a name="return-value"></a>Döndürülen değer

Bölüm 32 bitleri.

## <a name="remarks"></a>Açıklamalar

`_div64`İç bölünen *Bölüneni* *bölendir*. *Kalanı, kalanı tarafından işaret* edilen 32 bitlik tamsayıyla depolar ve bölümün 32 bitlerini döndürür.

`_div64`İç, Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Ayrıca bkz.

[_udiv64](udiv64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
