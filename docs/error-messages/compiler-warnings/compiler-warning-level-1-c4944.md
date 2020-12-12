---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4944'
title: Derleyici Uyarısı (düzey 1) C4944
ms.date: 11/04/2016
f1_keywords:
- C4944
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
ms.openlocfilehash: 8feff4072bec649761e14dbd74a74e7023f810cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328014"
---
# <a name="compiler-warning-level-1-c4944"></a>Derleyici Uyarısı (düzey 1) C4944

' symbol ': ' assembly1 ' öğesinden sembol içeri aktarılamıyor: ' symbol ' geçerli kapsamda zaten var

Bir sembol, kaynak kodu dosyasında tanımlandı ve sonra da simgeyi tanımlayan bir derlemeye #using bir bildirime başvurdu. Derlemedeki sembol yok sayılır.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, ClassA adlı bir türü olan bir bileşen oluşturur.

```csharp
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Aşağıdaki örnekler C4944 oluşturur.

```cpp
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
