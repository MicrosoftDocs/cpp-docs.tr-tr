---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 646330ca92af08903485fd4583eb2c217fe3e023
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216678"
---
# <a name="__readdr"></a>__readdr

Belirtilen hata ayıklama kaydının değerini okur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Parametreler

*DebugRegister*\
'ndaki Hata ayıklama kaydını tanımlayan 0 ile 7 arasında bir sabit.

## <a name="return-value"></a>Dönüş değeri

Belirtilen hata ayıklama kaydının değeri.

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readdr`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
