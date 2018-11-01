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
ms.openlocfilehash: 64e7031ab578632322dfd5c73eb81e0750c1e0b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587817"
---
# <a name="disable"></a>_disable

**Microsoft'a özgü**

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)