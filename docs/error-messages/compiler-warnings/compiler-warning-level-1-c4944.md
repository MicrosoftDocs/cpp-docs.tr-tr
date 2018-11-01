---
title: Derleyici Uyarısı (düzey 1) C4944
ms.date: 11/04/2016
f1_keywords:
- C4944
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
ms.openlocfilehash: 0c58a438f4e2c1437e1038b6087d57f47db30775
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585529"
---
# <a name="compiler-warning-level-1-c4944"></a>Derleyici Uyarısı (düzey 1) C4944

'symbol': 'assembly1' değerinden simge alınamıyor: 'symbol' geçerli kapsamda zaten var.

Bir kaynak kodu dosyasında tanımlanan bir simge ve ardından bir #using deyimi başvurulan sembol tanımlanmış bir derleme. Derlemedeki simgesi yok sayılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir bileşen Türetilme adlı bir tür ile oluşturur.

```
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnekler C4944 oluşturur.

```
// C4944b.cpp
// compile with: /clr /W1
class ClassA {
public:
   int u;
};

#using "C4944.dll"   // C4944 ClassA also defined C4944.dll

int main() {
   ClassA * x = new ClassA();
   x->u = 9;
   System::Console::WriteLine(x->u);
}
```