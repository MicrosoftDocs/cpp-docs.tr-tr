---
title: Derleyici Hatası C2051 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2051
dev_langs:
- C++
helpviewer_keywords:
- C2051
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 034c4953669b2d1a196649cc7b8886a9629d9ca4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031008"
---
# <a name="compiler-error-c2051"></a>Derleyici Hatası C2051

CASE ifadesi sabit değil

CASE ifadesi tamsayı sabitlerini olması gerekir.

Aşağıdaki örnek, C2051 oluşturur:

```
// C2051.cpp
class X {};

int main() {
   static X x;
   int i = 0;

   switch (i) {
      case x:   // C2051 use constant expression to resolve error
         break;
      default:
         break;
   }
}
```

Olası çözüm:

```
// C2051b.cpp
class X {};

int main() {
   static X x;
   int i = 0;

   switch (i) {
      case 1:
         break;
      default:
         break;
   }
}
```