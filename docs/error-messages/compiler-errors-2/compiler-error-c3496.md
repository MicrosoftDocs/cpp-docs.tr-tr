---
title: Derleyici Hatası C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: c0075bf0e3749966a5e5b9fcd775b5d73171bf17
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599426"
---
# <a name="compiler-error-c3496"></a>Derleyici Hatası C3496

'this' her zaman değere göre yakalanan: '&' yoksayıldı

Yakalama gerçekleştiremez `this` başvuruya göre işaretçi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yakalama `this` işaretçi değeri.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3496 oluşturur çünkü bir başvuru `this` işaretçi bir lambda ifadesinin yakalama listede görünür:

```
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)