---
title: Derleyici Hatası C2976 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2976
dev_langs:
- C++
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82cbe896d44190c5d7e6ee098f0f5a7a27e9378
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072920"
---
# <a name="compiler-error-c2976"></a>Derleyici Hatası C2976

'identifier': çok az tür bağımsız değişkeni

Genel veya şablon bir veya daha fazla gerçek bağımsız değişkenler eksik. Doğru parametreleri sayısını bulmak için genel veya şablon bildirimi denetleyin.

Bu hata, C++ Standart Kitaplığı bileşenlerinde şablon bağımsız değişkenleri eksik tarafından kaynaklanabilir.

Aşağıdaki örnek, C2976 oluşturur:

```
// C2976.cpp
template <class T>
struct TC {
   T t;
};
int main() {
   TC<>* t;   // C2976
   TC<int>* t2;   // OK
}
```

C2976, genel türler kullanırken da meydana gelebilir:

```
// C2976b.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC<>^ g;   // C2976
   GC<int>^ g2;   // OK
}
```