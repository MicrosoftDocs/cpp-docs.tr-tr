---
description: 'Hakkında daha fazla bilgi edinin: __writeeflags'
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 9c439194782f52b474ec6c6365705ebd8756c6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331871"
---
# <a name="__writeeflags"></a>__writeeflags

**Microsoft'a Özgü**

Belirtilen değeri program durumu ve denetim (EFLAGS) kaydına yazar.

## <a name="syntax"></a>Sözdizimi

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>Parametreler

*Deeri*\
'ndaki EFLAGS kaydına yazılacak değer. `Value`Parametresi, 32 bit platformun 32 bit uzunluğunda ve 64 bit platform için 64 bit uzunluğunda olur.

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
