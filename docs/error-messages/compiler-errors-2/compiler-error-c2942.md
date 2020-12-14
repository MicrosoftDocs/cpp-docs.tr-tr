---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2942'
title: Derleyici hatası C2942
ms.date: 11/04/2016
f1_keywords:
- C2942
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
ms.openlocfilehash: d68db30f1b70aed20e2501c88bddaf00bb330149
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249600"
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
