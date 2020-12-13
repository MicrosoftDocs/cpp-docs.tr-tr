---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4002'
title: Derleyici Uyarısı (düzey 1) C4002
ms.date: 11/04/2016
f1_keywords:
- C4002
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
ms.openlocfilehash: 5a0150c10e6a80604b97528dcedfc15b2cf4d0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336003"
---
# <a name="compiler-warning-level-1-c4002"></a>Derleyici Uyarısı (düzey 1) C4002

' tanımlayıcı ' makrosunun gerçek parametre sayısı çok fazla

Makrodaki gerçek parametrelerin sayısı, makro tanımındaki biçimsel parametre sayısını aşıyor. Önişlemci ek parametreleri toplar ancak makro genişletmesi sırasında onları yoksayar.

C4002, değişken olmayan bağımsız [makrolar](../../preprocessor/variadic-macros.md)kullanılırken hatalı gerçekleşir.

Aşağıdaki örnek C4002 oluşturur:

```cpp
// C4002.cpp
// compile with: /W1
#define test(a) (a)

int main() {
   int a = 1;
   int b = 2;
   a = test(a,b);   // C4002
   // try..
   a = test(a);
}
```

Bu hata, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: makrodaki ek virgüller artık kabul edilmedi.

Derleyici, bir makroda daha fazla virgül kabul etmez. Kodun hem Visual Studio .NET 2003 hem de Visual Studio .NET sürümlerinde geçerli olması için Visual C++, ek virgüller kaldırın.

```cpp
// C4002b.cpp
// compile with: /W1
#define F(x,y)
int main()
{
   F(2,,,,,,3,,,,,,)   // C4002
   // Try the following line instead:
   // F(2,3)
}
```
