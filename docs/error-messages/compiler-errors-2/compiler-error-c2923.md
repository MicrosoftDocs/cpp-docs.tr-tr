---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2923'
title: Derleyici hatası C2923
ms.date: 11/04/2016
f1_keywords:
- C2923
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
ms.openlocfilehash: 7897ba68998f88f82144278e79c97d8fec9f85d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270283"
---
# <a name="compiler-error-c2923"></a>Derleyici hatası C2923

' Type ': ' Identifier ', ' param ' parametresi için geçerli bir şablon türü bağımsız değişkeni değil

Bağımsız değişken listesinde, şablonu veya genel örneği oluşturmak için gereken bir tür eksik. Şablonu veya genel bildirimi denetleyin.

Aşağıdaki örnek C2923 oluşturur:

```cpp
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

C2923, genel türler kullanılırken de oluşabilir:

```cpp
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```
