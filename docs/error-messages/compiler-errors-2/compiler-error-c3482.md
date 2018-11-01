---
title: Derleyici Hatası C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: ec0018fc1aafc7e3e0423608f4db9f78946e4597
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432649"
---
# <a name="compiler-error-c3482"></a>Derleyici Hatası C3482

'this' yalnızca statik olmayan üye işlevin içinde lambda yakalaması olarak kullanılır

Geçiremezsiniz `this` statik bir yöntem veya genel bir işlev içinde bildirilen bir lambda ifadesinin yakalama listesi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kapsayan işlevin bir statik olmayan yönteme dönüştürmek veya

- Kaldırma `this` lambda ifadesinin yakalama listeden işaretçi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3482 oluşturur:

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)