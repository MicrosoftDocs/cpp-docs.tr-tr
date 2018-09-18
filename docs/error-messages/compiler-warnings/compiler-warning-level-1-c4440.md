---
title: Derleyici Uyarısı (düzey 1) C4440 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4440
dev_langs:
- C++
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e91479ee3e6562338a18ca482c319acb0e1647ca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088338"
---
# <a name="compiler-warning-level-1-c4440"></a>Derleyici Uyarısı (düzey 1) C4440

'calling_convention1' kuralı yeniden tanımlanması yoksayıldı 'calling_convention2' için çağırma

Çağırma kuralı değiştirme girişimi yoksayıldı.

Aşağıdaki örnek, C4440 oluşturur:

```
// C4440.cpp
// compile with: /W1 /LD /clr
typedef void __clrcall F();
typedef F __cdecl *PFV;   // C4440
```