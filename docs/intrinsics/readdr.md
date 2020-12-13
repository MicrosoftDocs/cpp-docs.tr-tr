---
description: 'Hakkında daha fazla bilgi edinin: __readdr'
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: b3b5952d940db91b278344ab45edb3e8b914c094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341015"
---
# <a name="__readdr"></a>__readdr

**Microsoft'a Özgü**

Belirtilen hata ayıklama kaydının değerini okur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Parametreler

*DebugRegister*\
'ndaki Hata ayıklama kaydını tanımlayan 0 ile 7 arasında bir sabit.

## <a name="return-value"></a>Döndürülen değer

Belirtilen hata ayıklama kaydının değeri.

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readdr`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
