---
title: Derleyici Hatası C2488
ms.date: 11/04/2016
f1_keywords:
- C2488
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
ms.openlocfilehash: 9b49d49c8a261bb3d636446f820a45699361830f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361691"
---
# <a name="compiler-error-c2488"></a>Derleyici Hatası C2488

'identifier': 'naked' yalnızca uygulanabilir üye olmayan işlev tanımlarına

[Naked](../../cpp/naked-cpp.md) öznitelik, bir işlev bildirimi için uygulandı.

Aşağıdaki örnek, C2488 oluşturur:

```
// C2488.cpp
// compile with: /c
// processor: x86
__declspec( naked ) void func();   // C2488  declaration, not definition
__declspec( naked ) void i;   // C2488  i is not a function

__declspec( naked ) void func() {}   // OK
```