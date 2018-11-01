---
title: Derleyici Hatası C3270
ms.date: 11/04/2016
f1_keywords:
- C3270
helpviewer_keywords:
- C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
ms.openlocfilehash: 91656ee893f2ad7b3f0c53cb157cd9faf129e4c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575727"
---
# <a name="compiler-error-c3270"></a>Derleyici Hatası C3270

'field': FieldOffset özniteliği yalnızca StructLayout(Explicit) bağlamında kullanılabilir, bu durumda gereklidir

Bir alan işaretlenmiş **FieldOffset**, yalnızca izin verilen zaman **StructLayout(Explicit)** etkindir.

Aşağıdaki örnek, C3270 oluşturur:

```
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
