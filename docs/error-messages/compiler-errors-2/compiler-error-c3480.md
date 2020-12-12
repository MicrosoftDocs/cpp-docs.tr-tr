---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3480'
title: Derleyici hatası C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: dbeed462410d36b466e807d576549c1b73ee4917
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113421"
---
# <a name="compiler-error-c3480"></a>Derleyici hatası C3480

' var ': bir Lambda yakalama değişkeni bir kapsayan işlev kapsamından gelmelidir

Lambda yakalama değişkeni kapsayan bir işlev kapsamından değil.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni lambda ifadesinin yakalama listesinden kaldırın.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3480 oluşturuyor çünkü değişken `global` kapsayan bir işlev kapsamından değil:

```cpp
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

Aşağıdaki örnek, `global` lambda ifadesinin yakalama listesinden değişkeni kaldırarak C3480 'i çözer:

```cpp
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
