---
title: Derleyici Hatası C2923 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2923
dev_langs:
- C++
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8bcf4a16681c725240f052921dfa9efb8dde8ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106169"
---
# <a name="compiler-error-c2923"></a>Derleyici Hatası C2923

'type': 'identifier' parametresi 'param' için geçerli bir şablon türü bağımsız değişkeni değil

Genel ve şablon örneği oluşturmak için gereken bir tür bağımsız değişken listesi eksik. Şablon veya genel bildirimi denetleyin.

Aşağıdaki örnek, C2923 oluşturur:

```
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

C2923, genel türler kullanırken da meydana gelebilir:

```
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```