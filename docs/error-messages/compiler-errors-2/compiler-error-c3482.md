---
title: Derleyici hatası C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 0463f6de51e324bd02c8b766fd39909ee2803ecd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212585"
---
# <a name="compiler-error-c3482"></a>Derleyici hatası C3482

' this ' yalnızca statik olmayan bir üye işlevi içinde bir lambda yakalaması olarak kullanılabilir

**`this`** Statik bir yöntemde veya genel işlevde belirtilen bir lambda ifadesinin yakalama listesine geçirilemez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kapsayan işlevi statik olmayan bir metoda dönüştürün veya

- **`this`** Lambda ifadesinin yakalama listesinden işaretçiyi kaldırın.

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

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
