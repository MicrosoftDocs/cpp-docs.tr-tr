---
title: Derleyici hatası C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: cd815bf90b135f65072a56911c7c4b0f054fcfec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210078"
---
# <a name="compiler-error-c2071"></a>Derleyici hatası C2071

' tanımlayıcı ': Geçersiz depolama sınıfı

`identifier`geçersiz bir [depolama sınıfıyla](../../c-language/c-storage-classes.md)bildirildi. Bu hata, bir tanımlayıcı için birden fazla depolama sınıfı belirtildiğinde veya tanım depolama sınıfı bildirimiyle uyumsuz olduğunda oluşabilir.

Bu sorunu gidermek için, tanımlayıcının hedeflenen depolama sınıfını (örneğin, **`static`** veya **`extern`** ) anlayın ve eşleşecek bildirimi düzeltin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2071 oluşturur.

```cpp
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

Aşağıdaki örnek C2071 oluşturur.

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
