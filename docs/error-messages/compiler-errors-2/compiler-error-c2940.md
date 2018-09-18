---
title: Derleyici Hatası C2940 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2940
dev_langs:
- C++
helpviewer_keywords:
- C2940
ms.assetid: af6bf2bf-8de6-4cfd-bbf0-4c6b32a30edf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6bc44d9c8286b14e091381cecfec537fae86b55
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045998"
---
# <a name="compiler-error-c2940"></a>Derleyici Hatası C2940

'class': türü sınıf kimliği, yerel bir tür tanımı yeniden tanımlandı

Yerel bir genel veya Şablon sınıfı kullanamazsınız `typedef`.

Aşağıdaki örnek, C2940 oluşturur:

```
// C2940.cpp
template<class T>
struct TC {};
int main() {
   typedef int TC<int>;   // C2940
   typedef int TC;   // OK
}
```

C2940, genel türler kullanırken da meydana gelebilir:

```
// C2940b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   typedef int GC<int>;   // C2940
   typedef int GC;
}
```