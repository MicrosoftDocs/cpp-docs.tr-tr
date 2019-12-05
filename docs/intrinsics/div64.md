---
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 59c5eae66f9e93cb88f9512e405376f2ef5f1ceb
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858028"
---
# <a name="_div64"></a>_div64

`_div64` iç, 64 bitlik bir tamsayıyı 32 bit tamsayıya böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_div64`, **Microsoft 'a özgüdür**.

## <a name="syntax"></a>Sözdizimi

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Parametreler

*bölünen* \
'ndaki Bölünecek 64 bitlik tamsayı.

*bölen* \
'ndaki Bölünecek 32 bitlik tamsayı.

*kalan* \
dışı Kalanın 32 bitlik tamsayı bitleri.

## <a name="return-value"></a>Dönüş değeri

Bölüm 32 bitleri.

## <a name="remarks"></a>Açıklamalar

`_div64` iç böler *bölen tarafından bölündükten*. *Kalanı, kalanı tarafından işaret*edilen 32 bitlik tamsayıyla depolar ve bölümün 32 bitlerini döndürür.

`_div64` iç, Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_div64`|x86, x64|ımintrin. h > \<|

## <a name="see-also"></a>Ayrıca bkz.

[_udiv64](udiv64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
