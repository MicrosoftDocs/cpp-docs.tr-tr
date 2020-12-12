---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2929'
title: Derleyici hatası C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: b110615a05a416b6bba7256c7f59f734179677a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320393"
---
# <a name="compiler-error-c2929"></a>Derleyici hatası C2929

' tanımlayıcı ': açık örnek oluşturma; Şablon sınıfı üyenin örnek oluşturma, açıkça zorlanamıyor ve bastırılamıyor

Bir tanımlayıcıyı örneklendirmesini engellerken açık bir şekilde örnekleyemezsiniz.

Aşağıdaki örnek C2929 oluşturur:

```cpp
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```
