---
title: Derleyici hatası C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: 255fb12d587a94aac798814736f0b26770f608b0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760484"
---
# <a name="compiler-error-c3480"></a>Derleyici hatası C3480

' var ': bir Lambda yakalama değişkeni bir kapsayan işlev kapsamından gelmelidir

Lambda yakalama değişkeni kapsayan bir işlev kapsamından değil.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni lambda ifadesinin yakalama listesinden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `global` değişken bir kapsayan işlev kapsamından olmadığından C3480 oluşturuyor:

```cpp
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, `global` değişkenini lambda ifadesinin yakalama listesinden kaldırarak C3480 çözer:

```cpp
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
