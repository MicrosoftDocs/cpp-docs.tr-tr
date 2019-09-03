---
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 1d05c5d6e25540a5de1b2f8231697c9a738759ce
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216768"
---
# <a name="_div64"></a>_div64

İç `_div64` , 64 bitlik bir tamsayıyı 32 bitlik bir tamsayıya böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_div64`, **Microsoft 'a özgüdür**.

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

## <a name="return-value"></a>Dönüş değeri

Bölüm 32 bitleri.

## <a name="remarks"></a>Açıklamalar

İç bölünen Bölüneni *bölendir*. `_div64` Kalanı, kalanı tarafından işaret edilen 32 bitlik tamsayıyla depolar ve bölümün32 bitlerini döndürür.

İç `_div64` , Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<ımintrin. h >|

## <a name="see-also"></a>Ayrıca bkz.

[_udiv64](udiv64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
