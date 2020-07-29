---
title: Derleyici hatası C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: d97722306e5c995a4921c6eb9577d623b21c9517
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216173"
---
# <a name="compiler-error-c2624"></a>Derleyici hatası C2624

yerel sınıflar ' extern ' değişkenler bildirmek için kullanılamaz

Yerel bir sınıf veya yapı değişkenleri bildirmek için kullanılamaz **`extern`** .

Aşağıdaki örnek C2624 oluşturur:

```cpp
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```
