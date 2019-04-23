---
title: Derleyici Hatası C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: 1bbf9b269075717ae397b7d29ee28c278b1e4ec8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034945"
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)