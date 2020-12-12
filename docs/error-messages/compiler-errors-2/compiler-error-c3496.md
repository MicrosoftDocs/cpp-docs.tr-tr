---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3496'
title: Derleyici hatası C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: dc3160e1007b65b70ea952aeaee3c77ba8ab21e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315523"
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
