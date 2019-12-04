---
title: Derleyici hatası C2942
ms.date: 11/04/2016
f1_keywords:
- C2942
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
ms.openlocfilehash: 98bb0d9945068042e00c7c48c0304314e281fa8f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758365"
---
# <a name="compiler-error-c2942"></a>Derleyici hatası C2942

' class ': tür sınıfı kimliği bir işlevin biçimsel bağımsız değişkeni olarak yeniden tanımlandı

Genel veya şablon sınıfını biçimsel bağımsız değişken olarak kullanamazsınız. Bir bağımsız değişkeni doğrudan genel veya şablon sınıfının oluşturucusuna geçiremezsiniz.

Aşağıdaki örnek C2942 oluşturur:

```

// C2942.cpp
// compile with: /c
template<class T>
struct TC {};
void f(int TC<int>) {}   // C2942

// OK
struct TC2 {};
void f(TC2 i) {}
```

C2942, genel türler kullanılırken de oluşabilir:

```cpp
// C2942b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
void f(int GC<int>) {}   // C2942
ref struct GC2 { };
void f(int GC2) {}
```
