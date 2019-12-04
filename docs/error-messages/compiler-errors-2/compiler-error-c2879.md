---
title: Derleyici hatası C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6c7238faf94a2493894534ae5684634b65bb4342
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736301"
---
# <a name="compiler-error-c2879"></a>Derleyici hatası C2879

' symbol ': bir ad alanı diğer ad tanımı tarafından yalnızca var olan bir ad alanına alternatif ad verilebilir

Ad alanı dışında bir simgenin ad [alanı diğer adı](../../cpp/namespaces-cpp.md#namespace_aliases) oluşturamazsınız.

Aşağıdaki örnek C2879 oluşturur:

```cpp
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```
