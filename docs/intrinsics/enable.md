---
title: _etkinleştir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _enable
- _enable_cpp
dev_langs:
- C++
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce3b59bc6665c4622078285a0c3b4b5011bc7d9b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433388"
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