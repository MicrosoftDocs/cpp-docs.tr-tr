---
title: __shiftright128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __shiftright128
dev_langs:
- C++
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10e848321f105f60643f579c12772f6a40edebeb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383525"
---
# <a name="shiftright128"></a>__shiftright128

**Microsoft'a özgü**

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

*Kaydırma*<br/>
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)