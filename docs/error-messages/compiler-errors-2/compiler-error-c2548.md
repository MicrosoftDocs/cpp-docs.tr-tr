---
title: Derleyici Hatası C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: 2c680d86a0ea69d67f9e53a481f2f096f4cc7878
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353475"
---
# <a name="compiler-error-c2548"></a>Derleyici Hatası C2548

'class::member': parametre parametresinin varsayılan parametresi eksik

Varsayılan parametre listesini bir parametre eksik. Bir parametre listesindeki herhangi bir varsayılan parametre sağlarsanız, sonraki tüm parametreler için varsayılan parametreleri tanımlamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2548 oluşturur:

```
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```