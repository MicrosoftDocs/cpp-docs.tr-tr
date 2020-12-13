---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2464'
title: Derleyici hatası C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: 2e30166529616809478927dbfe6ff1f1efb3002a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341847"
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
