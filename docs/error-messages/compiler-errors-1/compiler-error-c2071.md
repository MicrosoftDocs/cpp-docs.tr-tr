---
title: Derleyici hatası C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 1dc9781bc0cf1bc6c7f879cc3971828983471c6f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757754"
---
# <a name="compiler-error-c2071"></a>Derleyici hatası C2071

' tanımlayıcı ': Geçersiz depolama sınıfı

`identifier`, geçersiz bir [depolama sınıfıyla](../../c-language/c-storage-classes.md)bildirildi. Bu hata, bir tanımlayıcı için birden fazla depolama sınıfı belirtildiğinde veya tanım depolama sınıfı bildirimiyle uyumsuz olduğunda oluşabilir.

Bu sorunu gidermek için, tanımlayıcının amaçlanan depolama sınıfını anlayın — Örneğin, `static` veya `extern`— ve eşleşecek bildirimi düzeltin.

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
