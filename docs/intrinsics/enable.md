---
title: _enable
ms.date: 11/04/2016
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: 1d129db17b489972555efb0b5df2de52e01fa649
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631259"
---
# <a name="enable"></a>_enable

**Microsoft'a özgü**

Kesme sağlar.

## <a name="syntax"></a>Sözdizimi

```
void _enable(void);
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_enable`|x86, ARM, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`_enable` İşlemci Kesme bayrağı bildirir. X86 sistemleri, bu işlev Kesme bayrağı ayarlanmış oluşturur (`sti`) yönerge.

Bu işlev, yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullandıysanız, bir ayrıcalıklı yönerge özel durum oluşturulur.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)