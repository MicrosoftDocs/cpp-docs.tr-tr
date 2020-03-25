---
title: Derleyici Uyarısı (düzey 3) C4102
ms.date: 11/04/2016
f1_keywords:
- C4102
helpviewer_keywords:
- C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
ms.openlocfilehash: 53a68c476e307143d30f3bdbec88c0edb7d1bbd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199090"
---
# <a name="compiler-warning-level-3-c4102"></a>Derleyici Uyarısı (düzey 3) C4102

' Label ': başvurulmayan etiket

Etiket tanımlanmış, ancak hiçbir şekilde başvurulmadı. Derleyici etiketi yoksayar.

Aşağıdaki örnek C4102 oluşturur:

```cpp
// C4102.cpp
// compile with: /W3
int main() {
   int a;

   test:   // C4102, remove the unreferenced label to resolve

   a = 1;
}
```
