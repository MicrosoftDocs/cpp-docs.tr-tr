---
title: Derleyici Uyarısı (düzey 1) C4002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3b3d51b4408e79236993d49f7ceba5fc9537b6d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050144"
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