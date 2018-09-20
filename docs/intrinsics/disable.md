---
title: _disable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _disable_cpp
- _disable
dev_langs:
- C++
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2e0eb09934847c2f7b67c9e4961b02d31c68df2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382420"
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