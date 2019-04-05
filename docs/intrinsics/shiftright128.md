---
title: __shiftright128
ms.date: 11/04/2016
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: b721abc9be22709fdc221951e2012300d6b96762
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030108"
---
# <a name="shiftright128"></a>__shiftright128

**Microsoft'a Özgü**

İki 64-bit miktarlar olarak temsil edilen bir 128-bit miktarı kaydırır `LowPart` ve `HighPart`, sağ tarafından belirtilen bit sayısı `Shift` ve düşük 64 bit sonuç döndürür.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

#### <a name="parameters"></a>Parametreler

*Alt kısım*<br/>
[in] Kaydırmak için 128 bit miktarı düşük 64 bit.

*HighPart*<br/>
[in] Yüksek 64 bit kaydırmak için 128 bit miktarı.

*Shift*<br/>
[in] Kaydırılacak bit sayısı.

## <a name="return-value"></a>Dönüş Değeri

Düşük 64 bit sonuç.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__shiftright128`|X64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`Shift` Değerdir her zaman 64 bu nedenle, örneğin, çağırırsanız `__shiftright128(0, 1, 64)`, işlev yüksek bölümü kayar `0` BITS sağ ve düşük bir kısmını döndürür `0` ve `1` aksi beklenebilir gibi.

## <a name="example"></a>Örnek

Bir örnek için bkz. [__shiftleft128](../intrinsics/shiftleft128.md).

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)