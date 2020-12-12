---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3482'
title: Derleyici hatası C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 752ce53b590ef5c10c25e0d0e850c7c4cc2776bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315705"
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
