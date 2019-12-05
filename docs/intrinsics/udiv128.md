---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 5e8cc9ca3dbf19a04d07edb1d73df84f2e29a5c3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857989"
---
# <a name="_udiv128"></a>_udiv128

`_udiv128` iç, 128 bitlik işaretsiz bir tamsayıyı 64 bit işaretsiz bir tamsayı ile böler. Dönüş değeri bölümü, iç, bir işaretçi parametresi ile geri kalanı döndürür. `_udiv128`, **Microsoft 'a özgüdür**.

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

*Lowkar* \
'ndaki Bölünün düşük 64 bitleri.

*bölen* \
'ndaki Bölünecek 64 bitlik tamsayı.

*kalan* \
dışı Kalanın 64 bitlik tamsayı bitleri.

## <a name="return-value"></a>Dönüş değeri

Bölüm 64 bitleri.

## <a name="remarks"></a>Açıklamalar

128 bit bölünme sayısının üst 64 bitini ve *düşük olan 64 ' ı* *lowbölünen*olarak geçirin. İç değer bu değeri *bölene*böler. *Kalanı, kalanı tarafından işaret*edilen 64 bitlik işaretsiz tamsayıya depolar ve bölümün 64 bitlerini döndürür.

`_udiv128` iç, Visual Studio 2019 RTM 'den başlayarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_udiv128`|X64|ımintrin. h > \<|

## <a name="see-also"></a>Ayrıca bkz.

[_div128](div128.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
