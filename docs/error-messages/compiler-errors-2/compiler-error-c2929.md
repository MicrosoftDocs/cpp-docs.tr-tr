---
title: Derleyici Hatası C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: fe2a56f7722c70c11e980fb6ee59230ffd056c5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658815"
---
# <a name="compiler-error-c2929"></a>Derleyici Hatası C2929

'identifier': açık örnek oluşturma; açıkça zorlanamıyor ve Şablon sınıfı üyesinin örneğinin Gizle

Bir tanımlayıcı örneği oluşturulan önlenirken açıkça örneği oluşturulamıyor.

Aşağıdaki örnek, C2929 oluşturur:

```
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