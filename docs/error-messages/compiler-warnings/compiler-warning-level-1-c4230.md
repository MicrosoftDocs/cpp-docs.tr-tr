---
title: Derleyici Uyarısı (düzey 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: be402eed4474dd736ab237cfb5c7986741338eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163277"
---
# <a name="compiler-warning-level-1-c4230"></a>Derleyici Uyarısı (düzey 1) C4230

anakronizm kullanıldı: değiştiriciler/niteleyiciler birbirine bağlı; Niteleyici yoksayıldı

`__cdecl` gibi bir Microsoft değiştiricisinden önce bir niteleyici kullanılması, süresi geçmiş bir uygulamadır.

## <a name="example"></a>Örnek

```cpp
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```
