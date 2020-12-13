---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3120'
title: Derleyici hatası C3120
ms.date: 11/04/2016
f1_keywords:
- C3120
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
ms.openlocfilehash: 533f0df3da392c36b07af41b9493a7c404972760
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151079"
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
