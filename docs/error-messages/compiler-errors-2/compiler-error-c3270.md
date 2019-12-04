---
title: Derleyici hatası C3270
ms.date: 11/04/2016
f1_keywords:
- C3270
helpviewer_keywords:
- C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
ms.openlocfilehash: 52c4f8d320d3b6ac66e702d03346af0f84b664e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754010"
---
# <a name="compiler-error-c3270"></a>Derleyici hatası C3270

' Field ': FieldOffset özniteliği yalnızca StructLayout (açık) bağlamında kullanılabilir, bu durumda gereklidir

Bir alan, yalnızca **StructLayout (açık)** etkin olduğunda Izin verilen **FieldOffset**ile işaretlendi.

Aşağıdaki örnek C3270 oluşturur:

```cpp
// C3270_2.cpp
// compile with: /clr /c
using namespace System::Runtime::InteropServices;

[ StructLayout(LayoutKind::Sequential) ]
// try the following line instead
// [ StructLayout(LayoutKind::Explicit) ]
public value struct MYUNION
{
   [FieldOffset(0)] int a;   // C3270
   // ...
};
```
