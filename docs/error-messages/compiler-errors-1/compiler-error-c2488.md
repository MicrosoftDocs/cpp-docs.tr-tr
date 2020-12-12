---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2488'
title: Derleyici hatası C2488
ms.date: 11/04/2016
f1_keywords:
- C2488
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
ms.openlocfilehash: bb6a36749b630c4193174314f47a150f0981b0df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305502"
---
# <a name="compiler-error-c2488"></a>Derleyici hatası C2488

' tanımlayıcı ': ' Naked ' yalnızca üye olmayan işlev tanımlarına uygulanabilir

[Naked](../../cpp/naked-cpp.md) özniteliği bir işlev bildirimine uygulandı.

Aşağıdaki örnek C2488 oluşturur:

```cpp
// C2488.cpp
// compile with: /c
// processor: x86
__declspec( naked ) void func();   // C2488  declaration, not definition
__declspec( naked ) void i;   // C2488  i is not a function

__declspec( naked ) void func() {}   // OK
```
