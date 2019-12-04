---
title: Derleyici hatası C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 1d775551d0f4955dc4eda9b0d418ea31e065714f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743139"
---
# <a name="compiler-error-c3482"></a>Derleyici hatası C3482

' this ' yalnızca statik olmayan bir üye işlevi içinde bir lambda yakalaması olarak kullanılabilir

Statik bir yöntemde veya genel işlevde belirtilen lambda ifadesinin yakalama listesine `this` geçiremezsiniz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kapsayan işlevi statik olmayan bir metoda dönüştürün veya

- `this` işaretçisini lambda ifadesinin yakalama listesinden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3482 oluşturur:

```cpp
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
