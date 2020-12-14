---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2943'
title: Derleyici hatası C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: f85000ae554e25f2ca783b605b036abb3f04eadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249587"
---
# <a name="compiler-error-c2943"></a>Derleyici hatası C2943

' class ': tür sınıfı kimliği bir şablonun tür bağımsız değişkeni olarak yeniden tanımlandı

Genel veya şablon türü bağımsız değişkeni olarak bir sembol yerine genel veya şablon sınıfı kullanamazsınız.

Aşağıdaki örnek C2943 oluşturur:

```cpp
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```
