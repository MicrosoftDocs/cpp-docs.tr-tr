---
title: Derleyici Hatası C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: db448b462cd3a3f325c529e730e5c8f65e2b8f51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598816"
---
# <a name="compiler-error-c3185"></a>Derleyici Hatası C3185

'typeid' kullanılan yönetilen veya WinRT türü 'type', 'operator' bunun yerine kullanın

Uygulayamazsınız [TypeID](../../cpp/typeid-operator.md) yönetilen işleci veya kullanın; türü WinRT [TypeID](../../windows/typeid-cpp-component-extensions.md) yerine.

Aşağıdaki örnek, C3185 oluşturur ve bu sorunun nasıl gösterir:

```
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
