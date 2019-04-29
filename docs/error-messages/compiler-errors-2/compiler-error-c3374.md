---
title: Derleyici Hatası C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: 4b00b1cea8ac462c82c11d9f5b207706af74959c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328977"
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

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)