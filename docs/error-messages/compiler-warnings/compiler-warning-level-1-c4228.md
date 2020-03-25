---
title: Derleyici Uyarısı (düzey 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: c216143f2b47148f73502c847175201ea9a74fee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175902"
---
# <a name="compiler-warning-level-1-c4228"></a>Derleyici Uyarısı (düzey 1) C4228

Standart olmayan uzantı kullanıldı: bildirimci listesinde virgülden sonraki niteleyiciler yoksayıldı

Değişkenleri bildirirken bir Microsoft uzantısı ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) olduğunda bir virgülden sonra **const** veya `volatile` gibi niteleyicilerin kullanılması.

## <a name="example"></a>Örnek

```cpp
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```
