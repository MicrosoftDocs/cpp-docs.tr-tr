---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2831'
title: Derleyici hatası C2831
ms.date: 11/04/2016
f1_keywords:
- C2831
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
ms.openlocfilehash: 65fece68763e38de8c5047c66327e0615865fa9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194507"
---
# <a name="compiler-error-c2831"></a>Derleyici hatası C2831

' işleç işleci ' Varsayılan parametrelere sahip olamaz

Yalnızca üç operatör Varsayılan parametrelere sahip olabilir:

- [Yeni](../../cpp/new-operator-cpp.md)

- Atama =

- Sol parantez (

Aşağıdaki örnek C2831 oluşturur:

```cpp
// C2831.cpp
// compile with: /c
#define BINOP <=
class A {
public:
   int i;
   int operator BINOP(int x = 1) {   // C2831
   // try the following line instead
   // int operator BINOP(int x) {
      return i+x;
   }
};
```
