---
title: Derleyici Hatası C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 025498f3fe244916cd0a06e36feee6fdb532acc6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380987"
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