---
title: Derleyici hatası C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: ded4a183f69e4903afb4c9dfeae22f7751ef76ad
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686286"
---
# <a name="compiler-error-c3484"></a>Derleyici hatası C3484

dönüş türünden önce '-> ' bekleniyor

`->`Lambda ifadesinin dönüş türünden önce sağlamanız gerekir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- `->`Dönüş türünden önce sağlayın.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3484 oluşturur:

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

Aşağıdaki örnek, `->` lambda ifadesinin dönüş türünden önce sağlayarak C3484 'i çözer:

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
