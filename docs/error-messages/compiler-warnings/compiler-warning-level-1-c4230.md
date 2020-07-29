---
title: Derleyici Uyarısı (düzey 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: 0b590eaef2094c3d1c3a83541e9d5e10415928f9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223219"
---
# <a name="compiler-warning-level-1-c4230"></a>Derleyici Uyarısı (düzey 1) C4230

anakronizm kullanıldı: değiştiriciler/niteleyiciler birbirine bağlı; Niteleyici yoksayıldı

Gibi bir Microsoft değiştiricisinden önce bir niteleyici kullanılması **`__cdecl`** , süresi geçmiş bir uygulamadır.

## <a name="example"></a>Örnek

```cpp
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```
