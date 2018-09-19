---
title: Derleyici Hatası C3207 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3207
dev_langs:
- C++
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d649e67fab3e1b3198d46db34233220a97076c7c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029760"
---
# <a name="compiler-error-c3207"></a>Derleyici Hatası C3207

'function': Geçersiz şablon bağımsız değişkeni için 'arg', sınıf şablonu bekleniyor

Şablon Şablon bağımsız değişken alacağı bir şablon işlevi tanımlanır. Ancak, bir şablon türü bağımsız değişken geçirildi.

Aşağıdaki örnek, C3207 oluşturur:

```
// C3207.cpp
template <template <class T> class TT>
void f(){}

template <class T>
struct S
{
};

void f1()
{
   f<S<int> >();   // C3207
   // try the following line instead
   // f<S>();
}
```