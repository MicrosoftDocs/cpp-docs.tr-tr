---
title: Derleyici Hatası C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: c9ee9130d77e844ab435ecc34dcf53e12449abba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474938"
---
# <a name="compiler-error-c3374"></a>Derleyici Hatası C3374

Temsilci örneği oluşturulmuyorsa 'function' adresi alınamaz

Bir işlevin adresini, bir temsilci örneği oluşturulmasını dışındaki bir bağlamda yapılmadı.

Aşağıdaki örnek, C3374 oluşturur:

```
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)