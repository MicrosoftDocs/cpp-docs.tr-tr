---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2017'
title: Derleyici hatası C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: c70bd39cb15a0eff5d209a6fc76e3dc44b990d8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220909"
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
