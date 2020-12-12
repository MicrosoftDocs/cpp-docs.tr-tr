---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3483'
title: Derleyici hatası C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: 7c67e1e4d44c64fbcc023ee410dff2ecdd92c361
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113395"
---
# <a name="compiler-error-c3483"></a>Derleyici hatası C3483

' var ' zaten Lambda yakalama listesinin bir parçası

Aynı değişkeni bir lambda ifadesinin yakalama listesine birden çok kez geçirtiniz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkenin tüm ek örneklerini yakalama listesinden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `n` lambda ifadesinin yakalama listesinde değişken bir kereden fazla göründüğünden C3483 oluşturur:

```cpp
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
