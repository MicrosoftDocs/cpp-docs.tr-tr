---
title: Derleyici hatası C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: f89208314c1d2e8ddb5100da72aa600a411b4608
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756805"
---
# <a name="compiler-error-c2548"></a>Derleyici hatası C2548

' class:: Member ': parametre parametresi için varsayılan parametre eksik

Varsayılan parametre listesinde bir parametre eksik. Parametre listesinde herhangi bir yerde varsayılan bir parametre sağlarsanız, sonraki tüm parametrelerin varsayılan parametrelerini tanımlamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2548 oluşturur:

```cpp
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```
