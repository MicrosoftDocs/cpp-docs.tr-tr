---
title: Derleyici Hatası C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 95344b5ef675f566f433dfeaed9dee5c38ef77d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598282"
---
# <a name="compiler-error-c2071"></a>Derleyici Hatası C2071

'identifier': Geçersiz depolama sınıfı

`identifier` Geçersiz bir bildirildi [depolama sınıfı](../../c-language/c-storage-classes.md). Birden fazla depolama sınıfı tanımlayıcısı olarak belirtildiğinde veya tanımı depolama sınıfı bildirimle uyumsuz olduğunda bu hatayı neden olabilir.

Bu sorunu gidermek için hedeflenen depolama sınıfı tanımlayıcısının anlamak — Örneğin, `static` veya `extern`— bildirimi eşleşecek şekilde düzeltin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2071 oluşturur.

```
// C2071.cpp
// compile with: /c
struct C {
   extern int i;   // C2071
};
struct D {
   int i;   // OK, no extern on an automatic
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2071 oluşturur.

```
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```