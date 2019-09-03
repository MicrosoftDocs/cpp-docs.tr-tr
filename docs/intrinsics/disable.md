---
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
ms.openlocfilehash: 94be850e1d494ff62df84922b46f28481be68314
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216822"
---
# <a name="_disable"></a>_disable

**Microsoft 'a özgü**

Kesmeleri devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _disable(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_disable`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`_disable`İşlemciyi kesme bayrağını temizlemesini söyler. X86 sistemlerinde, bu işlev Clear Interrupt bayrağı (`cli`) yönergesini üretir.

Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullanılıyorsa, çalışma zamanında ayrıcalıklı yönerge özel durumu oluşturulur.

ARM ve ARM64 platformlarında, bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
