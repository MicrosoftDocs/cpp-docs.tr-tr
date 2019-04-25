---
title: Derleyici Hatası C3618
ms.date: 11/04/2016
f1_keywords:
- C3618
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
ms.openlocfilehash: 97f2738a67ee84196a49b96301c885c28c41050b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222071"
---
# <a name="compiler-error-c3618"></a>Derleyici Hatası C3618

'function': DllImport olarak işaretli bir yöntem tanımlanamaz

Bir yöntem ile işaretlenmiş <xref:System.Runtime.InteropServices.DllImportAttribute> tanımlı belirtilen. DLL.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3618 oluşturur.

```
// C3618.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED
void Func();

void Func() {}   // C3618, remove this function definition to resolve
```