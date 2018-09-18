---
title: Derleyici Hatası C3264 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3264
dev_langs:
- C++
helpviewer_keywords:
- C3264
ms.assetid: 94ece687-2364-4f7a-8ebb-7afd3ae9d63d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17dadf343cd342db4f18791882078cf46e5cc251
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063404"
---
# <a name="compiler-error-c3264"></a>Derleyici Hatası C3264

'class': sınıf oluşturucusu bir dönüş türü olamaz

Sınıf Oluşturucular, dönüş türleri olamaz.

Aşağıdaki örnek, C3264 oluşturur:

```
// C3264_2.cpp
// compile with: /clr

ref class X {
   public:
      static int X()   { // C3264
      }

      /* use the code below to resolve the error
      static X() {
      }
      */
};
int main() {
}
```
