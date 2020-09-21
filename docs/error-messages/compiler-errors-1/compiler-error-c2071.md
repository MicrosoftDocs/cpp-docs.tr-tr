---
title: Derleyici hatası C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 7619d968379bfc35e98bd87071b75296d10c382c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743288"
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
