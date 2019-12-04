---
title: Derleyici hatası C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 0eacb6ce6426674d23fc78596ead3730f46ae370
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743048"
---
# <a name="compiler-error-c3485"></a>Derleyici hatası C3485

bir lambda tanımında CV niteleyicileri bulunamaz

Lambda ifadesinin tanımının bir parçası olarak bir `const` veya `volatile` niteleyicisi kullanamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Lambda ifadeniz tanımından `const` veya `volatile` niteleyicisini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesinin tanımının bir parçası olarak `const` niteleyicisi kullandığından, C3485 oluşturur:

```cpp
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
