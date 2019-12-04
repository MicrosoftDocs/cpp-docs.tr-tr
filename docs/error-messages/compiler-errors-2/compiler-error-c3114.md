---
title: Derleyici hatası C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 6f548c72a0e95c533ed711fe9f2583a7abd6c500
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760767"
---
# <a name="compiler-error-c3114"></a>Derleyici hatası C3114

' Argument ': geçerli bir adlandırılmış öznitelik bağımsız değişkeni değil

Bir öznitelik sınıfı veri üyesinin geçerli bir adlandırılmış bağımsız değişken olabilmesi için, `static`, `const`veya `literal`olarak işaretlenmemelidir. Bir özellik ise, özelliğin `static` olmaması ve Get ve set erişimcilerine sahip olması gerekir.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md) ve [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3114 oluşturur.

```cpp
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
