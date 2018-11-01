---
title: Derleyici Hatası C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: c358553a36104b5c389076f5a5ce02f94f85e85a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667317"
---
# <a name="compiler-error-c2593"></a>Derleyici Hatası C2593

'''işleci identifier' belirsiz

Birden fazla olası işleci aşırı yüklenmiş bir işleç için tanımlanır.

Bir veya daha fazla gerçek parametre bir açık tür dönüştürme kullanıyorsanız bu hata sabit olamaz.

Aşağıdaki örnek, C2593 oluşturur:

```
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

Bu hata, bir kayan nokta değişkeni kullanarak seri hale getirme tarafından kaynaklanabilir bir `CArchive` nesne. Derleyici tanımlayan `<<` belirsiz olarak işleci. Yalnızca temel C++ türlerinin `CArchive` serileştirebiliyorsa sabit boyutlu türleridir `BYTE`, `WORD`, `DWORD`, ve `LONG`. Tüm tamsayı türleri bu türlerden birine seri hale getirme için dönüştürmeniz gerekir. Kayan nokta türleri gerekir arşivlenmiş kullanarak `CArchive::Write()` üye işlevi.

Aşağıdaki örnek, bir kayan nokta değişkeni arşivlemek gösterilmektedir (`f`) arşiv `ar`:

```
ar.Write(&f, sizeof( float ));
```