---
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: ddb46f33b0fccc1cedc2a704265b096ba715b506
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858002"
---
# <a name="_udiv64"></a>_udiv64

`_udiv64` iç, 64 bitlik işaretsiz bir tamsayıyı 32 bit işaretsiz bir tamsayı ile böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_udiv64`, **Microsoft 'a özgüdür**.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Parametreler

*bölünen*\
'ndaki Bölünecek 64 bitlik işaretsiz tamsayı.

*bölen*\
'ndaki Bölünecek 32 bitlik işaretsiz tamsayı.

*kalan*\
dışı 32 bitlik işaretsiz tamsayı kalanı.

## <a name="return-value"></a>Dönüş değeri

Bölüm 32 bitleri.

## <a name="remarks"></a>Açıklamalar

`_udiv64` iç böler *bölen tarafından bölündükten*. *Kalanı, kalanı tarafından işaret*edilen 32 bitlik işaretsiz tamsayıya depolar ve bölümün 32 bitlerini döndürür.

`_udiv64` iç, Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|ımintrin. h > \<|

## <a name="see-also"></a>Ayrıca bkz.

[_div64](div64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
