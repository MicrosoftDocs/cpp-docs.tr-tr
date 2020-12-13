---
description: 'Hakkında daha fazla bilgi edinin: _disable'
title: _disable
ms.date: 09/02/2019
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: c118315a4fea2dad401cc5c6f3621a8ec3b1794c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337100"
---
# <a name="_disable"></a>_disable

**Microsoft'a Özgü**

Kesmeleri devre dışı bırakır.

## <a name="syntax"></a>Syntax

```C
void _disable(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_disable`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`_disable` İşlemciyi kesme bayrağını temizlemesini söyler. X86 sistemlerinde, bu işlev Clear Interrupt bayrağı ( `cli` ) yönergesini üretir.

Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullanılıyorsa, çalışma zamanında ayrıcalıklı yönerge özel durumu oluşturulur.

ARM ve ARM64 platformlarında, bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
