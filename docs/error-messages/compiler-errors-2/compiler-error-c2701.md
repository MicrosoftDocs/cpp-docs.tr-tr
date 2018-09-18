---
title: Derleyici Hatası C2701 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2701
dev_langs:
- C++
helpviewer_keywords:
- C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671381cdd6ec7a9d2ed21fe194b7a123a114632b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107852"
---
# <a name="compiler-error-c2701"></a>Derleyici Hatası C2701

'function': yerel sınıfın arkadaş işlev şablonu olamaz

Bir yerel sınıf bir şablon işlevi bir arkadaş işlevi olamaz.

Aşağıdaki örnek, C2701 oluşturur:

```
// C2701.cpp
// compile with: /c
template<typename T>   // OK
void f1(const T &);

void MyFunction() {
   class MyClass {
      template<typename T> friend void f2(const T &);   // C2701
   };
}
```