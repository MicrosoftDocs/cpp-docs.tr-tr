---
title: Derleyici hatası C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: e4952f4702d871ecf1c818b1fc7394e54a1a295f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743893"
---
# <a name="compiler-error-c2464"></a>Derleyici hatası C2464

' tanımlayıcı ': bir başvuru ayırmak için ' New ' kullanılamaz

`new` işleci ile bir başvuru tanımlayıcısı ayrıldı. Başvurular bellek nesneleri olmadığından `new` bunlara bir işaretçi döndüremez. Bir başvuru bildirmek için standart değişken bildirimi sözdizimini kullanın.

Aşağıdaki örnek C2464 oluşturur:

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
