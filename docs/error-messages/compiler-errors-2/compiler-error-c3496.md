---
title: Derleyici hatası C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: b9542f1904c6797a77c88c88a37aff9348364268
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738186"
---
# <a name="compiler-error-c3496"></a>Derleyici hatası C3496

' this ' her zaman değere göre yakalanır: ' & ' yoksayıldı

`this` işaretçisini başvuruya göre yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- `this` işaretçiyi değere göre yakala.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesinin yakalama listesinde `this` işaretçisine bir başvuru göründüğünden, C3496 oluşturur:

```cpp
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
