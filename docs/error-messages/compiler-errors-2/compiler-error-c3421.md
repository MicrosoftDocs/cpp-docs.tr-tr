---
title: Derleyici Hatası C3421
ms.date: 11/04/2016
f1_keywords:
- C3421
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
ms.openlocfilehash: 399224a3d091a26066a03df0c77511997ae2403c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182431"
---
# <a name="compiler-error-c3421"></a>Derleyici Hatası C3421

'type': ya da olduğu gibi bu sınıf için Sonlandırıcı çağrılamıyor erişilemez veya artık yok

Bir sonlandırıcı örtük olarak özel olduğundan, gelen kapsayan türdeki dışında çağrılamaz.

Daha fazla bilgi için [yok ediciler ve sonlandırıcılar, nasıl yapılır: Sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3421 oluşturur.

```
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