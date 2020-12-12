---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2603'
title: Derleyici hatası C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: e28ea581c4c1417972cddc0ce558bd518acb8889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208794"
---
# <a name="compiler-error-c2603"></a>Derleyici hatası C2603

> '*Function*': işlev içindeki oluşturucuya/yıkıcıya sahip statik nesneler çok fazla blok kapsamı

Visual Studio 2015 ' den önceki Microsoft C++ derleyicisi sürümlerinde veya [/Zc: threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) Compiler seçeneği belirtildiğinde, dışarıdan görünür bir satır içi işlevde bulunan statik nesne sayısında 31 sınırı vardır.

Bu sorunu çözmek için, Microsoft C++ derleyici araç takımının daha yeni bir sürümünü benimsemenizi veya mümkünse/Zc: threadSafeInit-Compiler seçeneğini kaldırmanız önerilir. Bu mümkün değilse, statik nesnelerinizi birleştirmeyi göz önünde bulundurun. Nesneler aynı türde ise, bu türden tek bir statik dizi kullanmayı düşünün ve gerektiğinde tek tek üyelere başvurun.

## <a name="example"></a>Örnek

Aşağıdaki kod C2603 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2603.cpp
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };
extern inline void f1() {
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;
    static C C32;   // C2603 Comment this line out to avoid error
}
```
