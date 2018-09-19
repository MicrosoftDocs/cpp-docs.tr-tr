---
title: Derleyici Hatası C2784 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2784
dev_langs:
- C++
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed0e5dd7628031a7ad5ac66d2b691ee52dda62f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091315"
---
# <a name="compiler-error-c2784"></a>Derleyici Hatası C2784

'bildirim': 'type' için şablon bağımsız değişkeni 'türünden' anlaşılamadı

Derleyici, sağlanan işlev bağımsız değişkenleri bir şablon bağımsız değişkende belirlenemiyor.

Aşağıdaki örnek, C2784 oluşturur ve bu sorunun nasıl gösterir:

```
// C2784.cpp
template<class T> class X {};
template<class T> void f(X<T>) {}

int main() {
   X<int> x;
   f(1);   // C2784

   // To fix it, try the following line instead
   f(x);
}
```