---
title: Derleyici hatası C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c9895a3e5a8ae7e941fccde2da85fedfb3d2c6dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743126"
---
# <a name="compiler-error-c3484"></a>Derleyici hatası C3484

dönüş türünden önce '-> ' bekleniyor

Lambda ifadesinin dönüş türünden önce `->` sağlamanız gerekir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Dönüş türünden önce `->` sağlayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3484 oluşturur:

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, lambda ifadesinin dönüş türünden önce `->` sağlayarak C3484 çözer:

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
