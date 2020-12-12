---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3493'
title: Derleyici hatası C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: 8f16a53dbaf5b9924a4874d29d560f9c089eb244
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315536"
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
