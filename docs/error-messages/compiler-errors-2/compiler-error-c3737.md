---
title: Derleyici Hatası C3737 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3737
dev_langs:
- C++
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99ab9394f2c475079ee226dd294cca346ec68e32
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039263"
---
# <a name="compiler-error-c3737"></a>Derleyici Hatası C3737

'temsilci': temsilcinin açık bir çağırma kuralı olamaz

Belirtemezsiniz [çağırma kuralı](../../cpp/calling-conventions.md) için bir `delegate`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3737 oluşturur:

```
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
