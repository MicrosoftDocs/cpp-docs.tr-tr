---
title: Derleyici Hatası C3484 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3484
dev_langs:
- C++
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a79574f85d05c6b1ac32416509ba1f8c05e26b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019192"
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