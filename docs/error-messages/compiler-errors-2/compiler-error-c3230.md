---
title: Derleyici Hatası C3230 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3230
dev_langs:
- C++
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f74e17b1dec3aba78a38d993da81995d00c93784
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065611"
---
# <a name="compiler-error-c3230"></a>Derleyici Hatası C3230

'function': şablon türü bağımsız değişkeni için 'şablon' genel tür parametresi içeremez: 'param'

Şablon, derleme zamanında örneği oluşturulur, ancak genel türler çalışma zamanında örneği oluşturulur. Bu nedenle, genel tür son olarak bilinen, çalışma zamanında şablonu başlatılamaz çünkü şablon çağırabilirsiniz genel kod üretmek mümkün değildir.

Aşağıdaki örnek, C3230 oluşturur:

```
// C3230.cpp
// compile with: /clr /LD
template <class S>
void f(S t);

generic <class U>
ref class C {
   void f1(U x) {
      f(x);   // C3230
   }
};
```