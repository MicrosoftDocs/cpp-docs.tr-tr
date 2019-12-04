---
title: Derleyici hatası C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: 4cfe574f79eae2e45dc62315245a1b8b773d04df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746909"
---
# <a name="compiler-error-c2503"></a>Derleyici hatası C2503

' class ': taban sınıflar Sıfır boyutlu diziler içeremez

Temel sınıf veya yapı Sıfır boyutlu dizi içerir. Sınıftaki bir dizide en az bir öğe olmalıdır.

Aşağıdaki örnek C2503 oluşturur:

```cpp
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```
