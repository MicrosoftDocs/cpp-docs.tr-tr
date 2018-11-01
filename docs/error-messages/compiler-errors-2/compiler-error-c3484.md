---
title: Derleyici Hatası C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: fd8909b664f739afa1ab1208be0984b8f410154d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468646"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)