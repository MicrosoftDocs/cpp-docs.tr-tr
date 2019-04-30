---
title: Derleyici Hatası C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 9ac8f5e5edb1a6ed7314c5b5d125fcc9bfbe67de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378927"
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