---
title: Derleyici hatası C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: ea2c1a3d9a10fee455d20490f0408982f47ee0a7
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684735"
---
# <a name="compiler-error-c3493"></a>Derleyici hatası C3493

varsayılan yakalama modu belirtilmediğinden ' var ' örtük olarak yakalanamaz

Boş lambda ifadesi yakalama, `[]` lambda ifadesinin herhangi bir değişkeni açıkça veya örtük olarak yakalamaz belirtir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Varsayılan bir yakalama modu sağlayın veya

- Bir veya daha fazla değişkeni açık olarak yakala.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir dış değişkeni değiştirdiği ancak boş yakalama yan tümcesini belirttiğinden C3493 oluşturur:

```cpp
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

Aşağıdaki örnek, varsayılan yakalama modu olarak başvuruya göre belirterek C3493 çözer.

```cpp
// C3493b.cpp

int main()
{
   int m = 55;
   [&](int n) { m = n; }(99);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
