---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3271'
title: Derleyici hatası C3271
ms.date: 11/04/2016
f1_keywords:
- C3271
helpviewer_keywords:
- C3271
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
ms.openlocfilehash: 62ff98d27757aa8f339d99aa6a10d50bf7503a27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113679"
---
# <a name="compiler-error-c3271"></a>Derleyici hatası C3271

' üye ': FieldOffset özniteliği için geçersiz değer ' Value '

**FieldOffset** özniteliğine negatif bir sayı geçirildi.

Aşağıdaki örnek C3271 oluşturur:

```cpp
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
