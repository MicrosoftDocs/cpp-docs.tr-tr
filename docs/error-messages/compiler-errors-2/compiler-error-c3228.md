---
title: Derleyici Hatası C3228 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3228
dev_langs:
- C++
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1818cbae07af904a468447e16fcb95384e5dcd17
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054694"
---
# <a name="compiler-error-c3228"></a>Derleyici Hatası C3228

'function': genel tür bağımsız değişkeni için 'parametre', 'type' olamaz, valuetype veya tanıtıcı türü olmalıdır

Bir genel tür bağımsız değişkeni bir yanlış tür geçirildi.

Aşağıdaki örnek, C3228 oluşturur:

```
// C3228.cpp
// compile with: /clr
class A {};

value class B {};

generic <class T>
void Test() {}

ref class C {
public:
   generic <class T>
   static void f() {}
};

int main() {
   C::f<A>();   // C3228
   C::f<B>();   // OK

   Test<C>();   // C3228
   Test<C ^>();   // OK
}
```