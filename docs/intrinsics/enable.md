---
description: 'Hakkında daha fazla bilgi edinin: _enable'
title: _enable
ms.date: 09/02/2019
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: b9c84a31869dd356d5ee6ebd4eae5bd579cf319e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337049"
---
# <a name="_enable"></a>_enable

**Microsoft'a Özgü**

Kesmeleri izin vermez.

## <a name="syntax"></a>Syntax

```C
void _enable(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_enable`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`_enable` İşlemciyi kesme bayrağını ayarlamaya yöneltir. X86 sistemlerinde, bu işlev kesme bayrağını ayarla ( `sti` ) yönergesini üretir.

Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullanılıyorsa, ayrıcalıklı yönerge özel durumu oluşturulur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
