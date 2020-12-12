---
description: 'Hakkında daha fazla bilgi edinin: __shiftright128'
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: 71f8a0d9b740ebfef5e930715e07d1ec31950269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306982"
---
# <a name="__shiftright128"></a>__shiftright128

**Microsoft'a Özgü**

2 64-bit miktarlar olarak temsil edilen 128 bitlik miktarı `LowPart` ve `HighPart` tarafından belirtilen bir bit sayısıyla sağa doğru bir şekilde kaydırır `Shift` ve sonucun düşük 64 bitlerini döndürür.

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

## <a name="return-value"></a>Döndürülen değer

Sonucun 64 biti düşüktür.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__shiftright128`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`Shift`Değer her zaman modül 64 ' dir; Örneğin, çağırdığınızda, `__shiftright128(0, 1, 64)` işlev yüksek parçalı `0` bitleri sağa kaydıracaktır ve düşük bir kısmını döndürür, `0` `1` Aksi takdirde beklenmeyebilir.

## <a name="example"></a>Örnek

Bir örnek için bkz. [__shiftleft128](../intrinsics/shiftleft128.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__shiftleft128](../intrinsics/shiftleft128.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
