---
title: __readeflags
ms.date: 09/02/2019
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: 6afdc0f20a3ae72865a80ba2eb7f896f79f63171
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857911"
---
# <a name="__readeflags"></a>__readeflags

**Microsoft 'a özgü**

Program durumu ve denetimi (EFLAGS) kaydını okur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned     int __readeflags(void); /* x86 */
unsigned __int64 __readeflags(void); /* x64 */
```

## <a name="return-value"></a>Dönüş değeri

EFLAGS yazmaç değeri. Dönüş değeri 32 bit platformda 32 bit uzunluğunda ve 64 bit platformda 64 bit uzunluğundadır.

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[__writeeflags](../intrinsics/writeeflags.md)
