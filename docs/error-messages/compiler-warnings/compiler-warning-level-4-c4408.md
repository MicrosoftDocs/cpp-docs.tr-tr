---
title: Derleyici Uyarısı (düzey 4) C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 90ca85384b28f1cf2cdef5e4083813686b96c524
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682964"
---
# <a name="compiler-warning-level-4-c4408"></a>Derleyici Uyarısı (düzey 4) C4408

anonymousstruct veya Union herhangi bir veri üyesi bildirmiyor

Anonim bir struct veya Union 'un en az bir veri üyesi olması gerekir.

Aşağıdaki örnek C4408 oluşturur:

```cpp
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```