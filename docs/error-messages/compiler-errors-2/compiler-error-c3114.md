---
title: Derleyici Hatası C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: c5a4feae5c8805a27c020b532fd58e0562e46b6b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773781"
---
# <a name="compiler-error-c3114"></a>Derleyici Hatası C3114

'bağımsız değişkeni': geçerli bir adlandırılmış öznitelik bağımsız değişkeni

Geçerli bir adlandırılmış bağımsız değişkeni olarak bir öznitelik sınıfı veri üyesi için sırada bu değil işaretlenmelidir `static`, `const`, veya `literal`. Bir özellik, özelliğin olmamalıdır `static` ve gereken get ve set erişimcileri.

Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md) ve [kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3114 oluşturur.

```
// C3114.cpp
// compile with: /clr /c
public ref class A : System::Attribute {
public:
   static property int StaticProp {
      int get();
   }

   property int Prop2 {
      int get();
      void set(int i);
   }
};

[A(StaticProp=123)]   // C3114
public ref class R {};

[A(Prop2=123)]   // OK
public ref class S {};
```