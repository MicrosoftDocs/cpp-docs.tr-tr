---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2971'
title: Derleyici hatası C2971
ms.date: 11/04/2016
f1_keywords:
- C2971
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
ms.openlocfilehash: 51cecf7fcf80b93231763bb183b870760820ca7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210393"
---
# <a name="compiler-error-c2971"></a>Derleyici hatası C2971

' class ': şablon parametresi ' param ': ' arg ': yerel değişken tür olmayan bir bağımsız değişken olarak kullanılamaz

Yerel bir değişkenin adını veya adresini şablon bağımsız değişkeni olarak kullanamazsınız.

Aşağıdaki örnek C2971 oluşturur:

```cpp
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```
