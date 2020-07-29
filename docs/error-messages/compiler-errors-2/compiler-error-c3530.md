---
title: Derleyici hatası C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 023d7f0a5d509c4b301a9985da8ea7feb1f3d203
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228836"
---
# <a name="compiler-error-c3530"></a>Derleyici hatası C3530

' Auto ' diğer tür tanımlayıcılarla birleştirilemez

Anahtar sözcükle bir tür belirleyicisi kullanılır **`auto`** .

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Anahtar sözcüğünü kullanan bir değişken bildiriminde tür belirleyicisi kullanmayın **`auto`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek, değişken `x` **`auto`** anahtar sözcüğü ve türüyle bildirildiği **`int`** ve örnek **/Zc: Auto**ile derlendiğinden, C3530 verir.

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
