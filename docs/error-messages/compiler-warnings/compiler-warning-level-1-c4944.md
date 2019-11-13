---
title: Derleyici Uyarısı (düzey 1) C4944
ms.date: 11/04/2016
f1_keywords:
- C4944
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
ms.openlocfilehash: 339a136824f050391c23e268992a656714d1dabb
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050226"
---
# <a name="compiler-warning-level-1-c4944"></a>Derleyici Uyarısı (düzey 1) C4944

' symbol ': ' assembly1 ' öğesinden sembol içeri aktarılamıyor: ' symbol ' geçerli kapsamda zaten var

Bir sembol, kaynak kodu dosyasında tanımlandı ve sonra da simgeyi tanımlayan bir derlemeye #using bir bildirime başvurdu. Derlemedeki sembol yok sayılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, ClassA adlı bir türü olan bir bileşen oluşturur.

```csharp
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

## <a name="example"></a>Örnek

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