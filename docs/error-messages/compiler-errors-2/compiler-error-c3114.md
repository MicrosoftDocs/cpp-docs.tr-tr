---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3114'
title: Derleyici hatası C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 18d14ae01c0ae101ff0b66d837edd0699312af9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115956"
---
# <a name="compiler-error-c3114"></a>Derleyici hatası C3114

' Argument ': geçerli bir adlandırılmış öznitelik bağımsız değişkeni değil

Öznitelik sınıfı veri üyesinin geçerli bir adlandırılmış bağımsız değişken olabilmesi için, veya şeklinde işaretlenmemelidir **`static`** **`const`** **`literal`** . Bir özellik ise, özelliğin olmaması **`static`** ve Get ve set erişimcilerine sahip olması gerekir.

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
