---
title: _disable
ms.date: 11/04/2016
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: 93db063c6b53f0bec739ba134728b83379a21f53
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024689"
---
# <a name="disable"></a>_disable

**Microsoft'a Özgü**

Kesmeleri devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

```
void _disable(void);
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_disable`|x86, ARM, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`_disable` İşlemci Kesme bayrağını temizleme bildirir. X86 sistemleri, bu işlev kesme bayrağını Temizle oluşturur (`cli`) yönerge.

Bu işlev, yalnızca çekirdek modunda kullanılabilir. Ayrıcalıklı yönerge özel durum, kullanıcı modunda kullandıysanız, çalışma zamanında durum oluşturulur.

ARM platformlarında, bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)