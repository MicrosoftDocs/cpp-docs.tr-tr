---
title: Derleyici Hatası C3483 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: decc04f25689b24c560f59a71fd22a9708754352
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091692"
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