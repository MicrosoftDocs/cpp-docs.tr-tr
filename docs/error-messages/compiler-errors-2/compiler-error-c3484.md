---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3484'
title: Derleyici hatası C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: 6d3e72ef89ad33333c840b549cfc5c7c40495130
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315692"
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
