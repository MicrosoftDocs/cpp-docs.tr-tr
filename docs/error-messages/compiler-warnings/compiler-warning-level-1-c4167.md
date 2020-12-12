---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4167'
title: Derleyici Uyarısı (düzey 1) C4167
ms.date: 11/04/2016
f1_keywords:
- C4167
helpviewer_keywords:
- C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
ms.openlocfilehash: 8d0b08ea4d97c6e85f5e07ce4844abdae7afafbd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266994"
---
# <a name="compiler-warning-level-1-c4167"></a>Derleyici Uyarısı (düzey 1) C4167

işlev: yalnızca iç işlev olarak kullanılabilir

**#Pragma işlevi** , derleyicinin iç biçimde kullanılması gereken bir işleve geleneksel bir çağrı kullanmasına zorlamaya çalışır. Pragma yoksayıldı.

Bu uyarıyı önlemek için **#pragma işlevini** kaldırın.

## <a name="example"></a>Örnek

```cpp
// C4167.cpp
// compile with: /W1
#include <malloc.h>
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only
int main(){}
```
