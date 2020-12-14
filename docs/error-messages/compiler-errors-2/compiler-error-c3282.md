---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3282'
title: Derleyici hatası C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 9455f7e109da0efa87b215f0695eeeb41648c2b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311896"
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
