---
title: Derleyici Hatası C3865 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fd5c83d922601ca4cdffe0f3772723b31e630b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090847"
---
# <a name="compiler-error-c3865"></a>Derleyici Hatası C3865

'calling_convention': yalnızca yerel üye işlevlerde kullanılabilir

Çağırma kuralı, genel bir işlev olan bir işlev veya yönetilen bir üye işlevi kullanıldı. Çağırma kuralı yalnızca bir yerel (yönetilmeyen) üye işlev üzerinde kullanılabilir.

Daha fazla bilgi için [çağırma kuralları](../../cpp/calling-conventions.md).

Aşağıdaki örnek, C3865 oluşturur:

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```