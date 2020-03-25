---
title: Derleyici Uyarısı (düzey 1) C4002
ms.date: 11/04/2016
f1_keywords:
- C4002
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
ms.openlocfilehash: cb1e36a606f5c8bb0a1622260d64124264f0db32
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164774"
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

Derleyici, bir makroda daha fazla virgül kabul etmez. Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde kodun geçerli olması için C++, ek virgüller kaldırın.

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
