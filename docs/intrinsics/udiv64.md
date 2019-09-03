---
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 6dabbc94260ef578eb1a58a1b289b4a4654decdd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219687"
---
# <a name="_udiv64"></a>_udiv64

İç `_udiv64` , 64 bitlik işaretsiz bir tamsayıyı 32 bit işaretsiz bir tamsayı ile böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_udiv64`, **Microsoft 'a özgüdür**.

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

## <a name="return-value"></a>Dönüş değeri

Bölüm 32 bitleri.

## <a name="remarks"></a>Açıklamalar

İç bölünen Bölüneni *bölendir*. `_udiv64` Kalanı, kalanı tarafından işaret edilen 32 bitlik işaretsiz tamsayıya depolar ve bölümün 32bitlerini döndürür.

İç `_udiv64` , Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<ımintrin. h >|

## <a name="see-also"></a>Ayrıca bkz.

[_div64](div64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
