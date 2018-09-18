---
title: Derleyici Hatası C2977 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2977
dev_langs:
- C++
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad1fc9acabd37ca6c1f9c71a4f8447a8def6bb62
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057866"
---
# <a name="compiler-error-c2977"></a>Derleyici Hatası C2977

'identifier': çok fazla tür bağımsız değişkenleri

Genel veya şablon çok fazla sayıda gerçek bağımsız değişkenler var. Doğru parametreleri sayısını bulmak için genel veya şablon bildirimi denetleyin.

Aşağıdaki örnek, C2977 oluşturur:

```
// C2977.cpp
// compile with: /c
template<class T, int i>
class MyClass {};

template MyClass< int , 1, 1 >;   // C2977
template MyClass< int , 1 >;   // OK
```

C2977, genel türler kullanırken da meydana gelebilir:

```
// C2977b.cpp
// compile with: /clr
// C2977 expected
generic <class T, class U>
void f(){}

generic <class T>
ref struct GC1 {};

int main() {
   // Delete the following 2 lines to resolve.
   GC1<int, char> ^ pgc1;
   f<int,int,int>();

   // OK
   GC1<int> ^ pgc1;
   f<int, int>();
}
```