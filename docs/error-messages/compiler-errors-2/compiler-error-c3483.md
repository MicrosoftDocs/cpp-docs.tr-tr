---
title: Derleyici Hatası C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: c958eee234d25b008eb8cb03f40b45b8aaba81a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573465"
---
# <a name="compiler-error-c3483"></a>Derleyici Hatası C3483

'var' zaten lambda yakalama listesinin bir parçasıdır

Birden fazla kez bir lambda ifadesinin yakalama listeye'de aynı değişken geçirildi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Tüm ek örneklerini değişkeni yakalama listeden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek olduğundan C3483 oluşturur değişkeni `n` lambda ifadesinin yakalama listesinde birden fazla kez görüntülenir:

```
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)