---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 0e66bbe978199f47134aa288bdd2bac4eb3e332a
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59983112"
---
# <a name="udiv128"></a>_udiv128

`_udiv128` İç bir 128-bit işaretsiz tamsayıyı 64-bit işaretsiz tamsayı ile böler. Sayının dönüş değerine ve iç işaretçi parametresi üzerinden kalanı döndürür. `_udiv128` olan **Microsoft'a özgü**.

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

*highDividend* \
[in] Bölünen yüksek 64 bit.

*lowDividend* \
[in] Bölünen düşük 64 bit.

*bölen* \
[in] Bölen 64-bit tamsayı.

*Kalan* \
[out] Kalan 64-bit tamsayı bitleri.

## <a name="return-value"></a>Dönüş değeri

Sayının 64 bit.

## <a name="remarks"></a>Açıklamalar

Geçmesi 128 bit bölünen üst 64 bit *highDividend*ve daha düşük bir 64 bit cinsinden *lowDividend*. İç bu değere böler *bölen*. İşaret ettiği 64-bit işaretsiz tamsayı içinde kalan depolar *kalan*ve 64 bit sayının döndürür.

`_udiv128` İç Visual Studio 2019 için RTM'de mevcut başlatılıyor.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_udiv128`|X64|\<immintrin.h >|

## <a name="see-also"></a>Ayrıca bkz.

[_div128](div128.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
