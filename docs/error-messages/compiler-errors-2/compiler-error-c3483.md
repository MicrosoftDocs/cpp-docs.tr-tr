---
title: Derleyici Hatası C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: acbe89b5183d0991fb8d4a571a9595d6f6bafc6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381364"
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