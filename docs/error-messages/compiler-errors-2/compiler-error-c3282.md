---
title: Derleyici Hatası C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 46be1f5250c1ca787909c48646d59180d62bd899
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381689"
---
# <a name="compiler-error-c3282"></a>Derleyici Hatası C3282

genel parametre listeleri üzerinde yalnızca görüntülenebilir yönetilen veya WinRTclasses, yapılar veya işlevleri

Genel parametre listesi yanlış kullanıldı.  Daha fazla bilgi için [genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3282 oluşturur ve bu sorunun nasıl gösterir.

```
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```