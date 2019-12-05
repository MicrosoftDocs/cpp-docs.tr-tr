---
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 6b9b6976369ed810789e5749a2e30029cad4c2d7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858054"
---
# <a name="__writeeflags"></a>__writeeflags

**Microsoft 'a özgü**

Belirtilen değeri program durumu ve denetim (EFLAGS) kaydına yazar.

## <a name="syntax"></a>Sözdizimi

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>Parametreler

*Değer*\
'ndaki EFLAGS kaydına yazılacak değer. `Value` parametresi 32 bit platformun 32 bit uzunluğunda ve 64-bit platform için 64 bit uzunluğundadır.

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[__readeflags](../intrinsics/readeflags.md)
