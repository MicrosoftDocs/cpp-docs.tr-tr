---
title: Derleyici Uyarısı (düzey 1) C4547
ms.date: 11/04/2016
f1_keywords:
- C4547
helpviewer_keywords:
- C4547
ms.assetid: 3edf1c2e-c0d5-444d-ae83-44a7cce24bb2
ms.openlocfilehash: 2a456d2fc4097dd01524f9b62d46dc49160cd7d2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186250"
---
# <a name="compiler-warning-level-1-c4547"></a>Derleyici Uyarısı (düzey 1) C4547

' operator ': virgülden önceki işlecin etkisi yok; yan etkisi olan işleç bekleniyordu

Derleyici hatalı biçimlendirilmiş bir virgül ifadesi algıladı.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek C4547 oluşturur:

```cpp
// C4547.cpp
// compile with: /W1
#pragma warning (default : 4547)
int i = 0;
int j = 1;
int main() {
   int l = (i != i,0);   // C4547
   // try the following line instead
   // int l = (i != i);
   // or
   // int l = ((void)(i != i),0);
}
```
