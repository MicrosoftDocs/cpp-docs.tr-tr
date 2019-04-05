---
title: Derleyici Hatası C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c4405eb81911b1081d19d25ba779d24bee8f6d37
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039984"
---
# <a name="compiler-error-c3484"></a>Derleyici Hatası C3484

Beklenen dönüş türünden önce ' ->'

Sağlamanız gereken `->` bir lambda ifadesinin dönüş türünden önce.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Sağlamak `->` dönüş türünden önce.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3484 oluşturur:

```
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek sağlayarak C3484 çözümler `->` lambda ifadesinin dönüş türünden önce:

```
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)