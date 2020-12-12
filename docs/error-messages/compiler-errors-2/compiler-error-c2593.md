---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2593'
title: Derleyici hatası C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: 849cd79b1d469d957cf1bde499ce66bd54a64074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120171"
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

Bu hata, bir nesne kullanılarak kayan nokta değişkeni serileştirilmesinin nedeni olabilir `CArchive` . Derleyici `<<` işleci belirsiz olarak tanımlar. Seri hale getirebilen basit C++ türleri,,, `CArchive` ve sabit boyutlu türlerdir `BYTE` `WORD` `DWORD` `LONG` . Tüm tamsayı türlerinin serileştirme için bu türlerden birine dönüştürülmesi gerekir. Kayan nokta türleri, üye işlevi kullanılarak arşivlenmelidir `CArchive::Write()` .

Aşağıdaki örnek, bir kayan nokta değişkeninin () arşivlemek için nasıl arşivleneceği gösterilmektedir `f` `ar` :

```
ar.Write(&f, sizeof( float ));
```
