---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4440'
title: Derleyici Uyarısı (düzey 1) C4440
ms.date: 11/04/2016
f1_keywords:
- C4440
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
ms.openlocfilehash: 9e0a126ea1461e0b98bcef5117b893ea232fe262
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311051"
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
