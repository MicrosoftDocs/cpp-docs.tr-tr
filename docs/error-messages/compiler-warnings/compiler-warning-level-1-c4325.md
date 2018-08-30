---
title: Derleyici Uyarısı (düzey 1) C4325 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd265938afb51cc402dc84f38b7e95188c6292a7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197491"
---
# <a name="compiler-warning-level-1-c4325"></a>Derleyici Uyarısı (düzey 1) C4325

> Standart bölümün öznitelikleri '*bölüm*' yoksayıldı

## <a name="remarks"></a>Açıklamalar

Standart bir bölümün özniteliklerini değiştiremezsiniz. Örneğin:

```cpp
#pragma section(".sdata", long)
```

Bunun üzerine yazacak `.sdata` kullanan standart bölüm **kısa** veri türü ile **uzun** veri türü.

Öznitelikleri değil değişebilir standart bölümler dahil,

- .Data

- .sdata

- .BSS

- .sbss

- .Text

- .const

- .sconst

- .rdata

- .srdata

Ek olarak bölümlerde daha sonra eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[section](../../preprocessor/section.md)