---
title: Derleyici Hatası C3374 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3374
dev_langs:
- C++
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4fce4e39dac7342e8d564c0adc7537a856c05d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104900"
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