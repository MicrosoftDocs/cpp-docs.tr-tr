---
title: Derleyici hatası C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: d20bc61df2d0bab9115768b3bc0589f11a9bcdb9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302100"
---
# <a name="compiler-error-c2032"></a>Derleyici hatası C2032

' tanımlayıcı ': işlev ' structorunion ' yapısına/birleşime üye olamaz

Yapı veya birleşim, içinde C++ izin verilen ancak C 'de izin verilen bir Member işlevine sahiptir. Hatayı gidermek için, C++ program olarak derleyin veya üye işlevini kaldırın.

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
