---
title: Derleyici hatası C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: 2a385e35376ddce528678980705595bfb98aca95
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759353"
---
# <a name="compiler-error-c2593"></a>Derleyici hatası C2593

' işleç tanımlayıcısı ' belirsiz

Aşırı yüklenmiş bir operatör için birden fazla olası işleç tanımlandı.

Bu hata, bir veya daha fazla gerçek parametrelerde açık bir atama kullanırsanız düzeltilebilir.

Aşağıdaki örnek C2593 oluşturur:

```cpp
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

Bu hata, bir `CArchive` nesnesi kullanılarak bir kayan nokta değişkeninin serileştirilmesinin nedeni olabilir. Derleyici `<<` işlecini belirsiz olarak tanımlar. `CArchive` seri hale C++ getirilecek basit türler `BYTE`, `WORD`, `DWORD`ve `LONG`sabit boyutlu türlerdir. Tüm tamsayı türlerinin serileştirme için bu türlerden birine dönüştürülmesi gerekir. Kayan nokta türleri `CArchive::Write()` üye işlevi kullanılarak arşivlenmelidir.

Aşağıdaki örnek, `ar`arşivlemek için bir kayan nokta değişkeninin (`f`) nasıl arşivleneceği gösterilmektedir:

```
ar.Write(&f, sizeof( float ));
```
