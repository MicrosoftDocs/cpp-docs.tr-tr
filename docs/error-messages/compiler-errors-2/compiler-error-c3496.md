---
title: Derleyici Hatası C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 025498f3fe244916cd0a06e36feee6fdb532acc6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026710"
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)