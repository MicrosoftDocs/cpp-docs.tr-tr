---
title: Derleyici Hatası C2603 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2603
dev_langs:
- C++
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a893a77fb3760f00fb7fe7b5cb3ce5b3db3346e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057686"
---
# <a name="compiler-error-c2603"></a>Derleyici Hatası C2603

> '*işlevi*': işlevde oluşturucusu/yok Edicisi olan çok fazla sayıda blok kapsamı statik nesnesi

Visual Studio 2015 önce Visual C++ Derleyici sürümlerinde veya [/ZC: threadsafeınit](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) derleyici seçeneği belirtilmemişse, 31 statik nesneler dışarıdan görünen satır içi işlev sahip olabilir, sayısına bir sınır yoktur. .

Bu sorunu çözmek için Visual C++ Derleyici araç setini daha yeni sürümü benimseyin ve mümkün olduğunda, kaldırmak için/ZC: threadsafeınit derleyici seçeneği öneririz. Bu mümkün değilse, statik nesnelerini birleştirme göz önünde bulundurun. Nesneleri aynı türde ise, statik tek bir dizi türü kullanımını göz önünde bulundurun ve gerektiği gibi tek tek üyeleri başvurun.

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
