---
title: Derleyici Uyarısı (düzey 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: c7facdde54b44ba2ce07db0447b251d7014f76c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518488"
---
# <a name="compiler-warning-level-4-c4690"></a>Derleyici Uyarısı (düzey 4) C4690

> \[ emitidl (pop)]: atma sayısından fazla

## <a name="remarks"></a>Açıklamalar

[Emitidl](../../windows/emitidl.md) özniteliği POP gönderildi daha fazla bir kez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4690 oluşturur. Bu sorunu gidermek için tam olarak dilediğiniz kadar bu öznitelik POP emin olmak için gönderilir.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
