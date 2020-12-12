---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2624'
title: Derleyici hatası C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 4fa52e5192bd71c9fcdd3608b4161d1e5da57bdf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174682"
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
