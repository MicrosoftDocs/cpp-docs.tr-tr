---
title: Derleyici hatası C2995
ms.date: 11/04/2016
f1_keywords:
- C2995
helpviewer_keywords:
- C2995
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
ms.openlocfilehash: 542a527cee5ffca7551685741a9dcaac2a442fda
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761409"
---
# <a name="compiler-error-c2995"></a>Derleyici hatası C2995

' function ': işlev şablonu zaten tanımlanmış

Şablonlu bir sınıfın her üye işlevi için yalnızca bir tanım olduğundan emin olun.

Aşağıdaki örnek C2995 oluşturur:

```cpp
// C2995.cpp
// compile with: /c
template <class T>
void Test(T x){}

template <class T> void Test(T x){}   // C2995
template <class T> void Test2(T x){}   // OK
```
