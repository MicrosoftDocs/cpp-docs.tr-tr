---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2879'
title: Derleyici hatası C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6060678f71bf36d0af2e94e380a046ea7916ef05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194377"
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
