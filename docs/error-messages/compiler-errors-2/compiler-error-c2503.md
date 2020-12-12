---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2503'
title: Derleyici hatası C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: 941af8af7fc4399e3c091b9d12a882619f4fc62c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213097"
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
