---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: fbaf9e761f9f1450ccd12dc378ab6e498aa0df08
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857885"
---
# <a name="__readdr"></a>__readdr

**Microsoft 'a özgü**

Belirtilen hata ayıklama kaydının değerini okur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Parametreler

*Debugregister*\
'ndaki Hata ayıklama kaydını tanımlayan 0 ile 7 arasında bir sabit.

## <a name="return-value"></a>Dönüş değeri

Belirtilen hata ayıklama kaydının değeri.

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readdr`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[__readeflags](../intrinsics/readeflags.md)
