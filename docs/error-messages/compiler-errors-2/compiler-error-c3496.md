---
title: Derleyici hatası C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 993d391f28a59afc8926748f2e6f34ab441657dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228862"
---
# <a name="compiler-error-c3496"></a>Derleyici hatası C3496

' this ' her zaman değere göre yakalanır: ' & ' yoksayıldı

**`this`** İşaretçiyi başvuruya göre yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **`this`** İşaretçiyi değere göre yakala.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **`this`** bir lambda ifadesinin yakalama listesinde işaretçiye bir başvuru göründüğünden, C3496 oluşturur:

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

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
