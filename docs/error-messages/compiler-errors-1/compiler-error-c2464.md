---
title: Derleyici Hatası C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: a00ac997f73175eeab08a0132128e48e8fc58feb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338902"
---
# <a name="compiler-error-c2464"></a>Derleyici Hatası C2464

'identifier': bir başvuru ayırmak için 'new' kullanılamaz

Bir başvuru tanımlayıcısı ile ayrılan `new` işleci. Başvuru olmayan bellek nesneleri, bu nedenle `new` bir işaretçi kendisine döndüremez. Standart değişken bildirimi sözdizimi, bir başvuru bildirmek için kullanın.

Aşağıdaki örnek, C2464 oluşturur:

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```