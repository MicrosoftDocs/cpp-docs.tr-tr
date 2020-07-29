---
title: Derleyici hatası C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: b2d2766b11d15bdb666baa207591cc9ff279a280
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225481"
---
# <a name="compiler-error-c2464"></a>Derleyici hatası C2464

' tanımlayıcı ': bir başvuru ayırmak için ' New ' kullanılamaz

Bir başvuru tanımlayıcısı **`new`** işleçle ayrıldı. Başvurular bellek nesneleri olmadığından, **`new`** bunlara bir işaretçi döndüremez. Bir başvuru bildirmek için standart değişken bildirimi sözdizimini kullanın.

Aşağıdaki örnek C2464 oluşturur:

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
