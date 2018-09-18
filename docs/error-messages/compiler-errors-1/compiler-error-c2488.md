---
title: Derleyici Hatası C2488 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2488
dev_langs:
- C++
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f1bf2710acdc2a738b36ca9426ce55da9f6d769
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044347"
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