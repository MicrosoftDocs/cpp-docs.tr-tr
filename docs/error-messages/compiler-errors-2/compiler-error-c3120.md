---
title: Derleyici hatası C3120
ms.date: 11/04/2016
f1_keywords:
- C3120
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
ms.openlocfilehash: ced859be68f780d0f0dee31e31d80b994ee73404
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740955"
---
# <a name="compiler-error-c3120"></a>Derleyici hatası C3120

' method_name ': arabirim yöntemleri değişken bağımsız değişken listesi alamaz

Arabirim yöntemi değişken bağımsız değişken listesi alamaz. Örneğin, aşağıdaki arabirim tanımı C3120 oluşturur:

```cpp
// C3120.cpp
__interface A {
int X(int i, ...);    // C3120
};

int main(void) { return(0); }
```
