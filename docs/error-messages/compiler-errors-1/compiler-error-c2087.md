---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2087'
title: Derleyici hatası C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 98e54a8df8f06230f1adca1cb6d2f23f80acff8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252044"
---
# <a name="compiler-error-c2087"></a>Derleyici hatası C2087

' tanımlayıcı ': eksik alt simge

Birden çok alt simge içeren bir dizinin tanımında bir boyut için alt simge değeri eksik.

Aşağıdaki örnek C2087 oluşturur:

```cpp
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

Olası çözüm:

```cpp
// C2087b.cpp
int main() {
   char b[4][5];
}
```
