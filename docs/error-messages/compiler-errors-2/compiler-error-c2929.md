---
title: Derleyici Hatası C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: fe2a56f7722c70c11e980fb6ee59230ffd056c5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385725"
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