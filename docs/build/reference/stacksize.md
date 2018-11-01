---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: de2aa99375f588d682b714632590ba8e0db8ddcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597229"
---
# <a name="stacksize"></a>STACKSIZE

Yığın boyunu bayt cinsinden ayarlar.

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

Yığın ayarlamak için eşdeğer bir yöntem, [yığın ayırmaları](../../build/reference/stack-stack-allocations.md) (/ yığın) seçeneği. Hakkında ayrıntılar için bu seçeneği belgelerine bakın *rezerve* ve `commit` bağımsız değişkenler.

Bu seçenek DLL'ler üzerinde etkisi yoktur.

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)