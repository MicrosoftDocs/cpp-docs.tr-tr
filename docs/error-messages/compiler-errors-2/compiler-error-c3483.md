---
title: Derleyici Hatası C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: acbe89b5183d0991fb8d4a571a9595d6f6bafc6c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026129"
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)