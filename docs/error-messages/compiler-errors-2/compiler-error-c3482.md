---
title: Derleyici Hatası C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 6ff269d719dd354932ef79946ae99a9b60490199
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173230"
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)