---
title: Derleyici Uyarısı (düzey 4) C4625
ms.date: 11/04/2016
f1_keywords:
- C4625
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
ms.openlocfilehash: edcb43bf11c073e6ce721ba999fd99d28a8df15d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220500"
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