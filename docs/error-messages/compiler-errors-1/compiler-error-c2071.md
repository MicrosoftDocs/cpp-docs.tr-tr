---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2071'
title: Derleyici hatası C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: ec5a08150b322ca5ce3a973a4e65d71ed410e25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323200"
---
# <a name="compiler-error-c2071"></a>Derleyici hatası C2071

' tanımlayıcı ': Geçersiz depolama sınıfı

`identifier` geçersiz bir [depolama sınıfıyla](../../c-language/c-storage-classes.md)bildirildi. Bu hata, bir tanımlayıcı için birden fazla depolama sınıfı belirtildiğinde veya tanım depolama sınıfı bildirimiyle uyumsuz olduğunda oluşabilir.

Bu sorunu gidermek için, tanımlayıcının hedeflenen depolama sınıfını (örneğin, **`static`** veya **`extern`** ) anlayın ve eşleşecek bildirimi düzeltin.

## <a name="examples"></a>Örnekler

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

Aşağıdaki örnek C2071 oluşturur.

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
