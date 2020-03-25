---
title: Derleyici Uyarısı (düzey 1) C4440
ms.date: 11/04/2016
f1_keywords:
- C4440
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
ms.openlocfilehash: dbb10a83e619af04334af268381b2286b037257a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186783"
---
# <a name="compiler-warning-level-1-c4440"></a>Derleyici Uyarısı (düzey 1) C4440

' calling_convention1 ' değerinden ' calling_convention2 ' öğesine çağırma kuralı yeniden tanımı yoksayıldı

Çağırma kuralını değiştirme girişimi yoksayıldı.

Aşağıdaki örnek C4440 oluşturur:

```cpp
// C4440.cpp
// compile with: /W1 /LD /clr
typedef void __clrcall F();
typedef F __cdecl *PFV;   // C4440
```
