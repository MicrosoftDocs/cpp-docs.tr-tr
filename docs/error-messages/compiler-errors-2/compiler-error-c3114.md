---
title: Derleyici Hatası C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 6ce5b9860cd75619f26a3585981af5807c33535a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606680"
---
# <a name="compiler-error-c3114"></a>Derleyici Hatası C3114

'bağımsız değişkeni': geçerli bir adlandırılmış öznitelik bağımsız değişkeni

Geçerli bir adlandırılmış bağımsız değişkeni olarak bir öznitelik sınıfı veri üyesi için sırada bu değil işaretlenmelidir `static`, `const`, veya `literal`. Bir özellik, özelliğin olmamalıdır `static` ve gereken get ve set erişimcileri.

Daha fazla bilgi için [özelliği](../../windows/property-cpp-component-extensions.md) ve [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).

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