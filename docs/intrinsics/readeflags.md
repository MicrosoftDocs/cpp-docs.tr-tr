---
title: __readeflags
ms.date: 11/04/2016
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: 9913fb4287e673faf79b2c352bb42eda7f590fdd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026376"
---
# <a name="readeflags"></a>__readeflags

Program durumu ve denetim (EFLAGS) kaydını okur.

## <a name="syntax"></a>Sözdizimi

```
unsigned     int __readeflags(void);
unsigned __int64 __readeflags(void);
```

## <a name="return-value"></a>Dönüş Değeri

EFLAGS kayıt değeri. Dönüş değeri bir 32 bit platformda uzun ve 64 bit, 32 bit olan bir 64-bit platformlarda uzun.

## <a name="remarks"></a>Açıklamalar

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__writeeflags](../intrinsics/writeeflags.md)