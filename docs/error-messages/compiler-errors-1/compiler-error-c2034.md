---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2034'
title: Derleyici hatası C2034
ms.date: 11/04/2016
f1_keywords:
- C2034
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
ms.openlocfilehash: cbc3f8788e495a95b1eb5fb848322815b6f78d57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175423"
---
# <a name="compiler-error-c2034"></a>Derleyici hatası C2034

' tanımlayıcı ': bit alanının türü bit sayısı için çok küçük

Bit alanı bildirimindeki bit sayısı, taban türünün boyutunu aşıyor.

Aşağıdaki örnek C2034 oluşturur:

```cpp
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

Olası çözüm:

```cpp
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```
