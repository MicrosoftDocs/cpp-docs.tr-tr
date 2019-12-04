---
title: Derleyici hatası C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: 0d6c1467575e7fae7d5e4862f36e733a68210f8e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743100"
---
# <a name="compiler-error-c3483"></a>Derleyici hatası C3483

' var ' zaten Lambda yakalama listesinin bir parçası

Aynı değişkeni bir lambda ifadesinin yakalama listesine birden çok kez geçirtiniz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkenin tüm ek örneklerini yakalama listesinden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3483 üretir çünkü değişken `n` lambda ifadesinin yakalama listesinde birden çok kez görünüyor:

```cpp
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
