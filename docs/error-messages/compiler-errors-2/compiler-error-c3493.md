---
title: Derleyici Hatası C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: ece70a99477b018f6d7a935911f475e4fb4397cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548011"
---
# <a name="compiler-error-c3493"></a>Derleyici Hatası C3493

hiçbir varsayılan yakalama modu belirtilmediğinden 'var' örtük olarak yakalanamıyor

Boş bir lambda ifadesi yakalama `[]`, lambda ifadesi açıkça yapacağını belirtir veya tüm değişkenler örtük olarak yakalayın.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Varsayılan yakalama modu sağlayın veya

- Açıkça bir veya daha fazla değişken yakalayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü bir dış değişkenine değiştirir ancak boş yakalama yan tümcesi belirtir C3493 oluşturur:

```
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek varsayılan yakalama modu başvuruya göre belirterek C3493 çözümler.

```
// C3493b.cpp

int main()
{
   int m = 55;
   [&](int n) { m = n; }(99);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)