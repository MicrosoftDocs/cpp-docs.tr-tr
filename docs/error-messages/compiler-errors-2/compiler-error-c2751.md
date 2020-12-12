---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2751'
title: Derleyici hatası C2751
ms.date: 11/04/2016
f1_keywords:
- C2751
helpviewer_keywords:
- C2751
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
ms.openlocfilehash: 5eb41526946ee4318d8a1e96b04a527c828c914c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174461"
---
# <a name="compiler-error-c2751"></a>Derleyici hatası C2751

' Parameter ': bir işlev parametresinin adı nitelenemez

Nitelenmiş bir adı işlev parametresi olarak kullanamazsınız.

Aşağıdaki örnek C2751 oluşturur:

```cpp
// C2751.cpp
namespace std {
   template<typename T>
   class list {};
}

#define list std::list
void f(int &list){}   // C2751
```
