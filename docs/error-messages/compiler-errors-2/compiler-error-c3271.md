---
title: Derleyici Hatası C3271 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3271
dev_langs:
- C++
helpviewer_keywords:
- C3271
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d30a203f37e09b84a62863c26b2e0c59c270369a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091861"
---
# <a name="compiler-error-c3271"></a>Derleyici Hatası C3271

'member': FieldOffset özniteliği için ' value' değeri geçersiz

Negatif bir sayı geçildi **FieldOffset** özniteliği.

Aşağıdaki örnek, C3271 oluşturur:

```
// C3271.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
value class MyStruct1 {
   public: [FieldOffset(0)] int a;
   public: [FieldOffset(-1)] long b;   // C3271
};
```
