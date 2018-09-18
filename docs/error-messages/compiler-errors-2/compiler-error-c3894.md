---
title: Derleyici Hatası C3894 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3894
dev_langs:
- C++
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 373da78257ee0f5ce7307ab521cccb0297933240
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080096"
---
# <a name="compiler-error-c3894"></a>Derleyici Hatası C3894

'var': initonly statik veri üyesinin lvalue kullanımına yalnızca 'class' sınıfının sınıf oluşturucusunda izin verilir

Statik [initonly](../../dotnet/initonly-cpp-cli.md) veri üyeleri yalnızca kullanılabilir l-değeri, bir noktada bildirimin veya statik bir oluşturucu olarak.

Örnek (statik olmayan) initonly veri üyeleri yalnızca kendi bir noktada bildirimin veya örnek (statik olmayan) oluşturucuları l-değerler olarak kullanılabilir.

Aşağıdaki örnek, C3894 oluşturur:

```
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