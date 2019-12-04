---
title: Derleyici hatası C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 3766eaa83457ba6cffaf8b1599983a065772911c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750149"
---
# <a name="compiler-error-c3530"></a>Derleyici hatası C3530

' Auto ' diğer tür tanımlayıcılarla birleştirilemez

Tür belirleyicisi `auto` anahtar sözcüğüyle birlikte kullanılır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. `auto` anahtar sözcüğünü kullanan bir değişken bildiriminde tür belirleyicisi kullanmayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3530 verir, çünkü `x` değişkeni hem `auto` anahtar sözcüğüyle hem de `int`yazın ve örnek **/Zc: Auto**ile derlenmiştir.

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

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
