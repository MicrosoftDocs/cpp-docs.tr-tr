---
title: Derleyici Uyarısı (düzey 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: f5cc9e67c06443a73692ce663a2106dacff6035c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221022"
---
# <a name="compiler-warning-level-1-c4227"></a>Derleyici Uyarısı (düzey 1) C4227

anakronizm kullanıldı: başvuru üzerindeki niteleyiciler yoksayıldı

C++ başvuruları gibi niteleyicilerin kullanılması **`const`** **`volatile`** , süresi geçmiş bir uygulamadır.

## <a name="example"></a>Örnek

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```
