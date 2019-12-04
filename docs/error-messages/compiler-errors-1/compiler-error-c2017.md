---
title: Derleyici hatası C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: 3911ef9af2eb0fab7d0f9296ddce8a0f9b32ae0d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751059"
---
# <a name="compiler-error-c2017"></a>Derleyici hatası C2017

geçersiz kaçış sırası

\T gibi bir kaçış sırası, bir karakter veya dize sabiti dışında görünür.

Aşağıdaki örnek C2017 oluşturur:

```cpp
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017, stringize işleci kaçış dizileri içeren dizelerle kullanıldığında gerçekleşebilir.

Aşağıdaki örnek C2017 oluşturur:

```cpp
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```
