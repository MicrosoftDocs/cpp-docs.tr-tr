---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3530'
title: Derleyici hatası C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 74cd9ade2805ba26c700d476c53f87ea86a3baba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315380"
---
# <a name="compiler-error-c3530"></a>Derleyici hatası C3530

' Auto ' diğer tür tanımlayıcılarla birleştirilemez

Anahtar sözcükle bir tür belirleyicisi kullanılır **`auto`** .

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Anahtar sözcüğünü kullanan bir değişken bildiriminde tür belirleyicisi kullanmayın **`auto`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek, değişken `x` **`auto`** anahtar sözcüğü ve türüyle bildirildiği **`int`** ve örnek **/Zc: Auto** ile derlendiğinden, C3530 verir.

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)
