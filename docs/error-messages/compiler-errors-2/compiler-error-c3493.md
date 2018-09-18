---
title: Derleyici Hatası C3493 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3493
dev_langs:
- C++
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad3c46117e77d432af27321165f1e1ab93d2ef3c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045113"
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