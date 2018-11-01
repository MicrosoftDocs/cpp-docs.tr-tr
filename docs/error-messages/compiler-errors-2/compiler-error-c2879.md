---
title: Derleyici Hatası C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 9ac8f5e5edb1a6ed7314c5b5d125fcc9bfbe67de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677961"
---
# <a name="compiler-error-c2879"></a>Derleyici Hatası C2879

'symbol': yalnızca var olan bir ad alanı ad alanı diğer ad tanımıyla alternatif ad verilebilir

Oluşturamazsınız bir [ad alanı diğer adı](../../cpp/namespaces-cpp.md#namespace_aliases) için bir ad alanı dışındaki bir simge.

Aşağıdaki örnek, C2879 oluşturur:

```
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```