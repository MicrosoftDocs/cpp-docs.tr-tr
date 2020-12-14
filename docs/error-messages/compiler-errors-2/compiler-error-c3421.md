---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3421'
title: Derleyici hatası C3421
ms.date: 11/04/2016
f1_keywords:
- C3421
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
ms.openlocfilehash: ccb7301eefaddda36f33cf292174c799711b3866
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316042"
---
# <a name="compiler-error-c3421"></a>Derleyici hatası C3421

' Type ': erişilemez olduğu veya var olmadığı için bu sınıfın sonlandırıcısını çağıramazsınız

Sonlandırıcı örtük olarak özeldir, bu nedenle kapsayan türünün dışından çağrılamaz.

Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI) içinde yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3421 oluşturur.

```cpp
// C3421.cpp
// compile with: /clr
ref class A {};

ref class B {
   !B() {}

public:
   ~B() {}
};

int main() {
   A a;
   a.!A();   // C3421

   B b;
   b.!B();   // C3421
}
```
