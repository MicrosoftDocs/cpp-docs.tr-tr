---
title: Derleyici hatası C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: 178d1221886dc62edd9785d211e2189fa50962f4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738303"
---
# <a name="compiler-error-c3493"></a>Derleyici hatası C3493

varsayılan yakalama modu belirtilmediğinden ' var ' örtük olarak yakalanamaz

`[]`boş lambda ifadesi yakalama, lambda ifadesinin herhangi bir değişkeni açıkça veya örtük olarak yakalamaz belirtir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Varsayılan bir yakalama modu sağlayın veya

- Bir veya daha fazla değişkeni açık olarak yakala.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dış değişkeni değiştirdiği ancak boş yakalama yan tümcesini belirttiğinden C3493 oluşturur:

```cpp
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

## <a name="example"></a>Örnek

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

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
