---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2032'
title: Derleyici hatası C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: cb39a539dc1e360f70cc2b217d50f3a1eabcf0f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175462"
---
# <a name="compiler-error-c2032"></a>Derleyici hatası C2032

' tanımlayıcı ': işlev ' structorunion ' yapısına/birleşime üye olamaz

Yapı veya birleşim, C++ ' da izin verilen ancak C içinde olmayan bir Member işlevine sahiptir. Hatayı gidermek için, C++ programı olarak derleyin veya üye işlevini kaldırın.

Aşağıdaki örnek C2032 oluşturur:

```c
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

Olası çözüm:

```c
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
