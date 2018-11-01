---
title: Derleyici Uyarısı (düzey 1) C4002
ms.date: 11/04/2016
f1_keywords:
- C4002
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
ms.openlocfilehash: f2d2166a1370c02cfbc2346a63a424239ccb2b92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463069"
---
# <a name="compiler-warning-level-1-c4002"></a>Derleyici Uyarısı (düzey 1) C4002

Makro 'identifier' için çok fazla sayıda gerçek parametre

Makro gerçek parametre sayısı, Makro tanımında biçimsel parametre sayısını aşıyor. Önişlemci toplar ek parametreler ancak yoksayar bunları makro genişletme sırasında.

Yanlış kullanırken C4002 oluşabilir [Variadic makrolar](../../preprocessor/variadic-macros.md).

Aşağıdaki örnek, C4002 oluşturur:

```
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

Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: makroda artık kabul ek virgül.

Derleyici artık bir makroda fazladan bir virgül kabul eder. Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümü geçerli olması kod için fazladan bir virgül kaldırın.

```
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