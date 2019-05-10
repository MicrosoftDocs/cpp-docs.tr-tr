---
title: Derleyici Hatası C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: e4540180058c890a1dec9c4060f796f1f044c934
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447999"
---
# <a name="compiler-error-c2603"></a>Derleyici Hatası C2603

> '*işlevi*': İşlevde oluşturucusu/yok Edicisi olan çok fazla sayıda blok kapsamı statik nesnesi

Microsoft sürümlerinde C++ derleyici önce Visual Studio 2015 veya [/ZC: threadsafeınit](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) derleyici seçeneği belirtilmemişse, 31 statik nesneler bir dışarıdan görünür olabilir, sayısına bir sınır yoktur Satır içi işlev.

Bu sorunu çözmek için daha yeni sürümü Microsoft benimseyin öneririz C++ derleyici araç takımı, veya mümkünse, / ZC: threadsafeınit derleyici seçeneğini kaldırın. Bu mümkün değilse, statik nesnelerini birleştirme göz önünde bulundurun. Nesneleri aynı türde ise, statik tek bir dizi türü kullanımını göz önünde bulundurun ve gerektiği gibi tek tek üyeleri başvurun.

## <a name="example"></a>Örnek

Aşağıdaki kod C2603 oluşturur ve bunu çözmenin yollarından biri gösterilmektedir:

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
