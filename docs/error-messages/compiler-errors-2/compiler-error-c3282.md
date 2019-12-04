---
title: Derleyici hatası C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: a119f8a9482d3f49c98873fee6f54b434416ee48
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757585"
---
# <a name="compiler-error-c3282"></a>Derleyici hatası C3282

Genel parametre listeleri yalnızca yönetilen veya Wınrtclasses, yapılar veya işlevlerde bulunabilir

Genel parametre listesi yanlış kullanıldı.  Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3282 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```
