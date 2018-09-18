---
title: Derleyici Uyarısı (düzey 4) C4625 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4625
dev_langs:
- C++
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 970321370aeeea0ca4324f9a25d3ee1d8e54e15e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069111"
---
# <a name="compiler-warning-level-4-c4625"></a>Derleyici Uyarısı (düzey 4) C4625

'derived class': kopya Oluşturucusu örtük bir şekilde bir taban sınıf kopya oluşturucusuna erişilemez veya silinmiş olduğundan silindi olarak tanımlandı

Bir kopya Oluşturucusu silinmişse veya taban sınıfında ve türetilmiş bir sınıf için oluşturulmadı. Bu türdeki bir nesneyi kopyalamak için her türlü girişim, bir derleyici hatasına neden olur.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4625 oluşturur ve bu sorunun nasıl gösterir.

```
// C4625.cpp
// compile with: /W4 /c
#pragma warning(default : 4625)

struct A {
   A() {}

private:
   A(const A&) {}
};

struct C : private virtual A {};
struct B :  C {};   // C4625 no copy constructor

struct D : A {};
struct E :  D {};   // OK
```