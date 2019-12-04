---
title: Derleyici hatası C3618
ms.date: 11/04/2016
f1_keywords:
- C3618
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
ms.openlocfilehash: 6f0edf1addf753054fbc50a1591b5b1a37394087
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759730"
---
# <a name="compiler-error-c3618"></a>Derleyici hatası C3618

' function ': DllImport olarak işaretlenmiş bir yöntem tanımlanamaz

<xref:System.Runtime.InteropServices.DllImportAttribute> ile işaretlenmiş bir yöntem, belirtilen içinde tanımlanmıştır. Dosyasını.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3618 oluşturur.

```cpp
// C3618.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED
void Func();

void Func() {}   // C3618, remove this function definition to resolve
```
