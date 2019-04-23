---
title: _div64
ms.date: 04/17/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: a221cc7cf0655a41873c6777aecd8a9b27131b74
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59983106"
---
# <a name="div64"></a>_div64

`_div64` İç bir 64-bit tamsayı 32-bit tamsayı ile böler. Sayının dönüş değerine ve iç işaretçi parametresi üzerinden kalanı döndürür. `_div64` olan **Microsoft'a özgü**.

## <a name="syntax"></a>Sözdizimi

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Parametreler

*Bölünen* \
[in] Bölmek için 64-bit tamsayı.

*bölen* \
[in] Bölen 32-bit tamsayı.

*Kalan* \
[out] Kalan 32-bit tamsayı bitleri.

## <a name="return-value"></a>Dönüş değeri

Sayının 32 bit.

## <a name="remarks"></a>Açıklamalar

`_div64` İç böler *bölünen* tarafından *bölen*. İşaret ettiği 32-bit tamsayı içinde kalan depolar *kalan*ve 32 bit sayının döndürür.

`_div64` İç Visual Studio 2019 için RTM'de mevcut başlatılıyor.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h >|

## <a name="see-also"></a>Ayrıca bkz.

[_udiv64](udiv64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
