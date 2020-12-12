---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3894'
title: Derleyici hatası C3894
ms.date: 11/04/2016
f1_keywords:
- C3894
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
ms.openlocfilehash: 6290cb247e45c4bd3fd3b140f467d608203b488b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115787"
---
# <a name="compiler-error-c3894"></a>Derleyici hatası C3894

' var ': initonly statik veri üyesinin lvalue kullanımına yalnızca ' class ' sınıfının sınıf oluşturucusunda izin verilir

Statik [initonly](../../dotnet/initonly-cpp-cli.md) veri üyeleri, yalnızca bildirim noktasında veya statik oluşturucuda yalnızca l değerleri olarak kullanılabilir.

Örnek (statik olmayan) initonly veri üyeleri, yalnızca bildirim noktasında veya örnek (statik olmayan) oluşturucular içinde yalnızca l değerleri olarak kullanılabilir.

Aşağıdaki örnek C3894 oluşturur:

```cpp
// C3894.cpp
// compile with: /clr
ref struct Y1 {
   initonly static int data_var = 0;

public:
   // class constructor
   static Y1() {
      data_var = 99;   // OK
      System::Console::WriteLine("in static constructor");
   }

   // not the class constructor
   Y1(int i) {
      data_var = i;   // C3894
   }

   static void Test() {}

};

int main() {
   Y1::data_var = 88;   // C3894
   int i = Y1::data_var;
   Y1 ^ MyY1 = gcnew Y1(99);
   Y1::Test();
}
```
