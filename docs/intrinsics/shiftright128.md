---
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: a18a9958a51f291e4997c23e87ee48f739562416
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220023"
---
# <a name="__shiftright128"></a>__shiftright128

**Microsoft 'a özgü**

2 64-bit miktarlar `LowPart` olarak temsil edilen 128 bitlik miktarı ve `HighPart`tarafından `Shift` belirtilen bir bit sayısıyla sağa doğru bir şekilde kaydırır ve sonucun düşük 64 bitlerini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Parametreler

*LowPart*\
'ndaki SHIFT için 128 bit miktarın düşük 64 biti.

*HighPart*\
'ndaki SHIFT için 128 bit miktarın yüksek 64 biti.

*Karakter*\
'ndaki Kaydırılacak bit sayısı.

## <a name="return-value"></a>Dönüş değeri

Sonucun 64 biti düşüktür.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__shiftright128`|X64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`0` `__shiftright128(0, 1, 64)` `1` `0` Değer her zaman modül 64 ' dir; Örneğin, çağırdığınızda, işlev yüksek parçalı bitleri sağa kaydıracaktır ve düşük bir kısmını döndürür, aksi takdirde beklenmeyebilir. `Shift`

## <a name="example"></a>Örnek

Bir örnek için bkz. [__shiftleft128](../intrinsics/shiftleft128.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__shiftleft128](../intrinsics/shiftleft128.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
